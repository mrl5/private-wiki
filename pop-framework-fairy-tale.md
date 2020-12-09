# POP framework fairy tale

A long time ago in a galaxy far, far away Unix was born ...

There is a history about Grand Master Peter H. Salus and his version of *Unix
Philosophy*:

> * Write programs that do one thing and do it well.
> * Write programs to work together.
> * Write programs to handle text streams, because that is a universal interface.


*But the hearts of men are easily corrupted ...* **O**bject **O**riented
**P**rogramming was born. *Some things that should not have been forgotten were
lost* ... *History about __Unix Philosophy__ became legend, legend became myth
...*

Until when chance came: the rise of the Web, SaaS, and Open Source

The time for **P**lugin **O**riented **P**rogramming has come. Grand Master
Thomas S Hatch said:

> * Write programs that do one thing and do it well.
> * Write programs to work together.
> * Write programs to expose interfaces that can be easily merged together.


## Table of contents
* [HUBs, POPs, WTFs]
* [Luke use the pop-seed]
* [Using namespaces]
* [Sometimes Jedi must use classes anyway]
* [Using the force aka incorporating CLI]
* [Multi plugin project]
* [Contracts]


## HUBs, POPs, WTFs

0. `pop` book: https://pop-book.readthedocs.io/en/latest/
1. `pop` tutorial: https://pop.readthedocs.io/en/latest/tutorial/quickstart.html
2. `pop-config`: https://pop-config.readthedocs.io/en/latest/topics/quickstart.html#the-config-dictionary
3. `pop` patterns: https://pop.readthedocs.io/en/latest/topics/sub_patterns.html
4. https://en.wikipedia.org/wiki/Plug-in_(computing)


## Luke use the pop-seed

POP project needs to have a proper structure. `pop-seed` does this for you ...
PROPERLY.

```
mkdir -p ~/projects/pop-test-project && $_
pop-seed pop_star
```

If your project is using other plugins run
```
pop-seed rock_star -d plugin1 plugin1337
```
More details about multi plugin architecture in [Multi plugin project]

Take a closer look at repo structure now:
```
ls -la .
ls -la pop_star
ls -la pop_star/pop_star
```

This locations are most interesting:
1. `./pop_star/conf.py`
2. `./pop_star/pop_star/init.py`
3. `./pop_star/pop_star/contracts/` covered in [Contracts]

For further guidance on writing first pop app check:
[pop quickstart](https://pop.readthedocs.io/en/latest/tutorial/quickstart.html)

Getting back to project structure. `./run.py` and `./pop_star/scripts.py` got
me confused.

1. if the `pop-star` is a standalone project then user cares only about
   `run.py` and `run.py --help` (srly)
2. if the `pop-star` is a part of [Multi plugin project] then
   `./pop_star/scripts.py` is not even in the `hub`

Let's be pragmatic now, I like `bin/` folder that was not created by
`pop-seed`. Lets have executables there.

Making a long story short, you can be a rebel and do:
```
rm -v ./pop_star/scripts.py
mkdir bin
mv -v run.py bin/
chmod +x bin/run.py
vim setup.py # to edit entry_points
```

*P.S.*

Even if your project is *One ring to rule them all, one ring to find them, One
ring to bring them all.* pls also `mkdir tests` :) Even if you don't mind
having this dir empty, it might be a nice invitation for some contributor that
want's to make sure that his changes wont be broken in the future. Well written
unit tests are a nice way for:

1. Showing developers how to use your code
2. Having contracts with the code base (borrowed that from [this Pieter
   Hintjens speach](https://www.youtube.com/watch?v=O8CbzKREAj4&t=29m05s))
3. Nice way for an CI in GitHub/GitLab

And don't go Dark Side with unit tests - 100% code coverage is impossible and
counter productive IMO (however I really like
[TDD](https://en.wikipedia.org/wiki/Test-driven_development))

```
mkdir tests/ && touch tests/.gitignore
```

## Using namespaces

[Chapter from `pop-book` about the hub and the
namespace](https://pop-book.readthedocs.io/en/latest/main/plugable.html#the-hub-and-the-namespace)

Generally speaking I see it as [a
matryoshka](https://giphy.com/gifs/girly-nest-nesting-3oEjHWPTo7c0ajPwty)!

Some example now: lets define `serialize_input()` as private function (limited
only to file) and public function `sing_that_hit()` (exposed to `hub`).

So this is in `./pop_star/pop_star/greatest_hits.py`
```
greatest_hits = {
    "yellow_submarine": "we are living",
    "dirty_deeds": "done dirt cheap",
    "i_shot_the_sherrif": "but I did not shoot the deputy",
    "only_you_can_cool_my_desire": "Oh oh oh, I'm on fire Woo ooh ooh",
    "bird": "Bird, bird, bird, b-bird's the word A-well-a, bird, bird, bird, the bird is the word",
}

def serialize_input(input):
    decoded = input.decode("utf-8")
    stripped = decoded.strip()
    lower_cased = stripped.lower()
    final = lower_cased.replace(' ', '_')
    return final

def sing_that_hit(hub, input):
    serlialized = serialize_input(input)
    print(greatest_hits[serlialized])
```

Lets use it from somewhere else
```
def how_did_it_go(hub, phrase):
    return hub.pop_star.greatest_hits.sing_that_hit(phrase)
```


## Sometimes Jedi must use classes anyway

Taken from [pop-book about
instances](https://pop-book.readthedocs.io/en/latest/main/instances.html):

> Classes should be used in Plugin Oriented Programming only when it is
> necessary to either extend an existing library, or to create a type like
> interface that is critical to an application. Classes should not be used for
> other interfaces.

Lets walk through a usecase where custom errors are needed:
```
def __init__(hub):
    global HUB
    HUB = hub


class SerializerError(TypeError):
    def __init__(self, msg):
        self.hub = HUB
        self.msg = msg
```

WOW, now we have `SerializerError` class available in `hub.pop_star` namespace.
Just remember to use classes if you REALLY need them, otherwise you will
convert to the Dark Side:

> The Dark Side of the Force is a pathway to many abilities some consider to be unnatural.
>
> Once you start down the dark path, forever will it dominate your destiny.

Well.. if you really want it:
```
def __init__(hub):
    global HUB
    HUB = hub


class Sith():
    def __init__(self):
        self.hub = HUB
        self.lightning = "something something dark side"

    def do_force_lightning(self, target):
        print("UNLIMITED POWER !!!")
        return self.lightning
```


## Using the force aka incorporating CLI

[pop-config about conf.py](https://pop-config.readthedocs.io/en/latest/topics/quickstart.html#understanding-the-conf-py)

Magic is done in several places:
1. Defining flags, args and subcommands in `./pop_star/conf.py`
  * `CLI_CONF` define flags and positional args here
  * `SUBCOMMANDS` define `git cli`-like subcommands here
2. adding magic lines in exposed CLI scripts:
```
import pop.hub


hub = pop.hub.Hub()
hub.pop.sub.add(dyne_name="pop_star")
# hub.pop_star.init.cli()
hub.pop.config.load(["pop_star"], cli="pop_star")
```
3. referring to flags and args values inside the plugin code:
```
def do_stuff(hub):
    some_arg = hub.OPT.pop_star.some_arg
    print(f"I just got {some_arg}")
```


## Multi plugin project

* todo: *story about project that uses external plugins*
* refs: https://pop-book.readthedocs.io/en/latest/main/plugable.html#app-merging


## Contracts

* [pop-book about contracts](https://pop-book.readthedocs.io/en/latest/main/contracts.html)
* [pop docs about contracts](https://pop.readthedocs.io/en/latest/topics/contracts.html)

I like this concept and the implementation. Similar to [Proxy() - JavaScript's
standard, built-in
object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy).

There is one **pop contracts gotcha** described in [GitLab
issue #95](https://gitlab.com/saltstack/pop/pop/-/issues/95)

Summing up, there are:
* `sig_<func>` (signature) that:
  * forces function implementation
  * verifies type annotations (it's not verifying the type itself but forces
   implementation to have the same type annotation)
  * looks like it does not force `async`
  * verifies `*args`, `**kwargs` and parameter names
* wrappers, that can be applied to one function or all functions in a module:
  * `pre_<func>` + global `pre`
  ```
  def pre_do_stuff_with_input_json(hub, ctx):
      input_json = ctx.args[1]
          validate(instance=input_json, schema=input_json_schema)
  ```
  * `call_<func>` + global `call`. Encountered 2 gotchas
  ```
  async def call_query_cpe_match(hub, ctx):
      quasi_cpe = ctx.args[1]
      if quasi_cpe is None:
          return []
      # gotcha 1) remember to always return
      # gotcha 2) return await
      return await ctx.func(*ctx.args, **ctx.kwargs)
  ```
  * `post_<func>` + global `post`
* a plugin can also volunteer itself to take on a specific contract



[HUBs, POPs, WTFs]: #hubs-pops-wtfs
[Luke use the pop-seed]: #luke-use-the-pop-seed
[Using namespaces]: #using-namespaces
[Sometimes Jedi must use classes anyway]: #sometimes-jedi-must-use-classes-anyway
[Using the force aka incorporating CLI]: #using-the-force-aka-incorporating-cli
[Multi plugin project]: #multi-plugin-project
[Contracts]: #contracts
