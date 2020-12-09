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

For further guidance on writing first pop app check: https://pop.readthedocs.io/en/latest/tutorial/quickstart.html


## Using namespaces

https://pop-book.readthedocs.io/en/latest/main/plugable.html#the-hub-and-the-namespace

todo: *story about referencing external functions and variables + story about
puting things into the hub*

Lets define `serialize_input()` as private function (limited only to file) and
public function `sing_that_hit()` (exposed to hub)

so this is in `./pop_star/pop_star/greatest_hits.py`
```
greatest_hits = {
    "yellow_submarine": "we are living",
    "dirty_deeds": "done dirt cheap",
    "i_shot_the_sherrif": "but I did not shoot the deputy",
    "only_you_can_cool_my_desire": "Oh oh oh, I'm on fire\nWoo ooh ooh",
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

From https://pop-book.readthedocs.io/en/latest/main/instances.html:
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


## Using the force aka incorporating CLI

todo: *story about CLI_CONF, flags etc*
https://pop-config.readthedocs.io/en/latest/topics/quickstart.html#the-config-dictionary


## Multi plugin project

https://pop-book.readthedocs.io/en/latest/main/plugable.html#app-merging
todo: *story about project that uses external plugins*


## Contracts

todo: *story about contracts and some usecases for them*
https://pop-book.readthedocs.io/en/latest/main/contracts.html



[HUBs, POPs, WTFs]: #hubs-pops-wtfs
[Luke use the pop-seed]: #luke-use-the-pop-seed
[Using namespaces]: #using-namespaces
[Sometimes Jedi must use classes anyway]: #sometimes-jedi-must-use-classes-anyway
[Using the force aka incorporating CLI]: #using-the-force-aka-incorporating-cli
[Multi plugin project]: #multi-plugin-project
[Contracts]: #contracts
