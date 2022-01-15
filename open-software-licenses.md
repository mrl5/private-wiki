# My process of choosing a software license for the project

I'll operate on identifiers from https://spdx.org/licenses/

**TL;DR** I choose [`MPL-2.0`](https://choosealicense.com/licenses/mpl-2.0/) if
project is not "silly", otherwise I choose
[`BSD-2`](https://choosealicense.com/licenses/bsd-2-clause/)

If this document is too complex for you, here is a very good primer that I
recommend: https://blog.svgames.pl/files/hacktoberfest2017-licences.pdf


## DISCLAIMER

The "verdict" is personal opinion that I try to back up with references I find
reliable. Also the decisions that lead to final choice don't need to be the
same for every project.

Why? You must be aware that primarily it affects the users of your software but
also people willing to become co-authors. It would be a disappointment that
people don't want to contribute to your project because of the license. License
choice also has other legal implications, e.g. related to copyrights and terms
under which your code (or binary) can be reused in different projects.


## The process

0. I want open source license (obviously) so I need to choose between Copyfree
   (a.k.a permissive) and Copyleft ones from:
   https://opensource.org/licenses/alphabetical. Here [SPDX
   table](https://spdx.org/licenses/) comes handy, so the list can be narrowed
   further because I want it to be both:
    - [FSF](https://www.fsf.org/about/) approved
    - [OSI](https://opensource.org/about) approved

1. When I do "silly" project for fun then I choose `BSD-2`. Linus Torvalds
   would approve my choice (see **[[primer]]**). I prefer `BSD-x` over
   `MIT` because I understand it better (although according to some sources
   like **[[A]]** they are the same from legal point of view).

2. When I do collaboration project or #1 is no longer considered "silly" then I
   don't find `BSD-x` suitable anymore:
    - because of Pieter Hintjens opinion mentioned in **[[B]]** (and I don't have
    another guru in this area that would convince me)
    - because there is some legal controversy around patents when `BSD-x` is
    used. I don't understand it but I recognize it based on sources like
    **[[C]]**. This is important from both author and contributor point of
    view
    - because according to some sources (like **[[C]]**) it doesn't give "sense of
    security and comfort" for the users

3. Now then, the pretender representing Copyfree (a.k.a. permissive) world is
   `Apache-2.0` - mostly because it's popular (see **[[D]]**) and backed up by
   [Apache Software Foundation](https://www.apache.org/). Now, lets pick up
   pretender from Copyleft world.

4. Copyleft licenses can be divided into "weak" and "strong" (see **[[E]]**). I
   don't want "strong" Copyleft (which effectively takes away `GPL` family
   from the pretender list) because:
    - I don't mind that my software can be used as a part of other software that
    wants to have it's own license

5. I want license to be recognizable (see **[[D]]**). This leaves on the table
   "weak" Copyleft `LGPL` family and `MPL-2.0` next to Copyfree (a.k.a.
   permissive) `Apache-2.0`.
    - Why even bother with `MPL-2.0` since it has very little share in
      mentioned statistics? It's still [Mozilla](https://www.mozilla.org/)
      that's behind it, which makes it recognizable

6. Based on **[[F]]** you can say that `LGPL-3.0` didn't cover all usecases for
   the libzmq project. So it had to be customized ... and replaced later by
   `MPL-2.0`.

7. [They say that `7` is a magic
   number](https://en.wikipedia.org/wiki/The_Magical_Number_Seven,_Plus_or_Minus_Two)
   so it's about time to choose between `MPL-2.0` (Copyleft) and `Apache-2.0`
   (Copyfree a.k.a. permissive). **I don't want `Apache-2.0`** because:
   - it's not compatible with with `GPL-2.0` according to **[[G]]** (but it's
     worth mentioning that it's with `GPL-3.0` - see **[[H]]**)


**Verdict:** I choose `MPL-2.0` if project is not silly, otherwise I choose
`BSD-2`. `MPL-2.0` seems to be a sweet spot between free software and
enterprise world.


## Also check
* [MPL 2.0 FAQ](https://www.mozilla.org/en-US/MPL/2.0/FAQ/)
* [Mozilla Public License Version 2.0](https://www.mozilla.org/en-US/MPL/2.0/)
* [The FreeBSD Copyright](https://www.freebsd.org/copyright/freebsd-license/)
  (a.k.a. "Simplified BSD License" a.k.a. 2-clause license)
* [The 4.4BSD Copyright](https://www.freebsd.org/copyright/license/) (a.k.a.
  original "BSD License") - here is [the original one from Regents of the
  University of
  California]((ftp://ftp.cs.berkeley.edu/pub/4bsd/README.Impt.License.Change))
* [GNU General Public License family](https://www.gnu.org/licenses/licenses.html)
* [APACHE LICENSE, VERSION 2.0](https://www.apache.org/licenses/LICENSE-2.0)


## References
* [primer] - "Copyleft and Copyfree - a short overview of popular licences" by
  Artur Iwicki
* [A] - Chapter 6, Section "Eat Me" from "ØMQ - The Guide" book by Pieter
  Hintjens
* [B] - Chapter 6, Section "The Importance of Contracts " from "ØMQ - The
  Guide" book by Pieter Hintjens
* [C] - "Open Source Licenses 101: Apache License 2.0" `fossa.com` blogpost
* [D] - "Open source license usage on GitHub.com" from GitHub blog
* [E] - "Copyleft" Wikipedia article
* [F] - "ØMQ Licensing"
* [G] - "Various Licenses and Comments about Them" from `gnu.org`
* [H] - Apache Software Foundation comment on GPL compatibility


[primer]: https://blog.svgames.pl/files/hacktoberfest2017-licences.pdf
[A]: https://zguide.zeromq.org/docs/chapter6/#Eat-Me
[B]: https://zguide.zeromq.org/docs/chapter6/#The-Importance-of-Contracts
[C]: https://fossa.com/blog/open-source-licenses-101-apache-license-2-0/
[D]: https://github.blog/2015-03-09-open-source-license-usage-on-github-com/
[E]: https://en.wikipedia.org/wiki/Copyleft#Strong_and_weak_copyleft
[F]: http://wiki.zeromq.org/area:licensing
[G]: https://www.gnu.org/licenses/license-list.en.html#apache2
[H]: https://www.apache.org/licenses/GPL-compatibility.html
