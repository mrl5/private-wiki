# My process of choosing a software license for the project

I'll operate on identifiers from https://spdx.org/licenses/

**TL;DR** I choose [`MPL-2.0`](https://choosealicense.com/licenses/mpl-2.0/) if
project is not silly, otherwise I choose
[`BSD-2`](https://choosealicense.com/licenses/bsd-2-clause/)

0. I want open source license (obviously) so I need to choose between Copyfree
   and Copyleft ones from: https://opensource.org/licenses/alphabetical. Here
   [SPDX table](https://spdx.org/licenses/) comes handy, so the list can be
   narrowed further because I want it to be both:
    - [FSF](https://www.fsf.org/about/) approved
    - [OSI](https://opensource.org/about) approved

1. When I do "silly" project for fun then I choose `BSD-2`. Linus Torvalds
   would approve my choice (see **[[bonus]]**). I prefer `BSD-x` over
   `MIT` because I understand it better (although I am aware that according to
   some sources like **[[A]]** they are the same from legal point of view).

2. When I do collaboration project or #1 is no longer considered "silly" then I
   don't find `BSD-x` suitable anymore:
    - because of Pieter Hintjens opinion mentioned in **[[B]]** (and I don't have
    another guru in this area that would convince me)
    - because there is some legal controversy around patents when `BSD-x` is
    used. I don't understand it but I recognize it based on sources like
    **[[C]]**
    - because according to some sources (like **[[C]]**) it doesn't give "sense of
    security and comfort"

3. Now then, the pretender representing Copefree world is `Apache-2.0` - mostly
   because it's popular (see **[[D]]**) and backed up by Apache Software
   Foundation. Lets pick up pretender from Copyleft world.

4. Copyleft licenses can be divided into "weak" and "strong" (see **[[E]]**). I
   don't want "strong" Copyleft because:
    - I don't mind that my software can be used as a part of other software that
    wants to have it's own license

5. I want license to be recognizable (see **[[D]]**). This leaves on the table
   "weak" Copyleft `LGPL` and `MPL-2.0` next to Copyfree `Apache-2.0`.

6. Based on **[[F]]** you can say that `LGPL` don't cover all usecases, so it had
   to be customized ... or replaced by `MPL-2.0`.

7. [They say that `7` is a magic
   number](https://en.wikipedia.org/wiki/The_Magical_Number_Seven,_Plus_or_Minus_Two)
   so it's about time to choose between `MPL-2.0` (Copyleft) and `Apache-2.0`
   (Copyfree). **I don't want `Apache-2.0`** because:
   - it's not compatible with with `GPL-2.0` (see **[[G]]**) but it's worth
     mentioning that it's with `GPL-3.0` (see **[[H]]**)

**Verdict:** I choose `MPL-2.0` if project is not silly, otherwise I choose
`BSD-2`. `MPL-2.0` seems to be a sweet spot between free software and
enterprise world



[bonus]: https://blog.svgames.pl/files/hacktoberfest2017-licences.pdf
[A]: https://zguide.zeromq.org/docs/chapter6/#Eat-Me
[B]: https://zguide.zeromq.org/docs/chapter6/#The-Importance-of-Contracts
[C]: https://fossa.com/blog/open-source-licenses-101-apache-license-2-0/
[D]: https://github.blog/2015-03-09-open-source-license-usage-on-github-com/
[E]: https://en.wikipedia.org/wiki/Copyleft#Strong_and_weak_copyleft
[F]: http://wiki.zeromq.org/area:licensing
[G]: https://www.gnu.org/licenses/license-list.en.html#apache2
[H]: https://www.apache.org/licenses/GPL-compatibility.html
