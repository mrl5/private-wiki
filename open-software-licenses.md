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

Why? You must be aware that primarily it affects the users of your software,
then other developers that would like to use your code or binary (e.g. as a
dependency) and last but not least potential co-authors that would like to
contribute to your codebase. It would be a disappointment if any of them would
refrain from using it because of the license.

License choice also has other legal implications, e.g. related to copyrights or
patent claims and sometimes even offers additional legal protections to
contributors.


## The process

0. I want open source license (obviously) so I need to choose between  ones from:
   https://opensource.org/licenses/alphabetical. Here [SPDX
   table](https://spdx.org/licenses/) comes handy, so the list can be narrowed
   further because I want it to be both:
    - [FSF](https://www.fsf.org/about/) approved
    - [OSI](https://opensource.org/about) approved
   It's also a good moment to distinguish between Copyfree (a.k.a. permissive)
   and Copyleft:
    - `Copyfree` (a.k.a. permissive) allows the code to be used in any way
    - `Copyleft` requires publishing changes under the same license

1. When I do "silly" project for fun then I choose `BSD-2`. Linus Torvalds
   would approve my choice (see **[[primer]]**). I prefer `BSD-x` over
   `MIT` because I understand it better (although according to some sources
   like **[[A]]** they are the same from legal point of view).
    - `BSD-2` is Copyfree (a.k.a. permissive)
    - `BSD-2` is short and understandable for a person that is not fluent in
      legal language
    - `BSD-2` is customizable -> you can have `BSD-3` or `BSD-4` just by
      adding one more clause

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
   `Apache-2.0` - mostly because it's popular (see **[[D]]**), backed up by
   [Apache Software Foundation](https://www.apache.org/) and gives better legal
   protection (see **[[C]]**).

4. Now, lets pick up pretender from Copyleft world. Copyleft licenses can be
   divided into "weak" and "strong" (see **[[E]]**). I don't want "strong"
   Copyleft (which effectively takes away `GPL` family from the pretender list)
   because:
    - I don't mind that my software can be used as a part of other software that
    wants to have it's own license
    - "weak" Copyleft gives more freedom to other developers. From legal
      perspective it gives them more possibilites to use your software

5. I want license to be recognizable (see **[[D]]**). This leaves on the table
   "weak" Copyleft `LGPL` family next to Copyfree (a.k.a.
   permissive) `Apache-2.0`. But hey, there are more "weak" Copyleft licenses,
   like:
    - `MPL-2.0` (backed up by [Mozilla](https://www.mozilla.org/) and used in
   e.g. Firefox or LibreOffice **[[J]]**)
    - `EPL-2.0` (backed up by [Eclipse foundation](https://www.eclipse.org/))

6. Based on **[[F]]** you can say that `LGPL-3.0` didn't cover all usecases for
   the libzmq project. So it had to be customized (and automatically stopped to
   be standard license)... Because of this there is `MPL-2.0` on their radar.

7. [They say that `7` is a magic
   number](https://en.wikipedia.org/wiki/The_Magical_Number_Seven,_Plus_or_Minus_Two)
   so it's about time to choose between `MPL-2.0` and `Apache-2.0`:
    - **I don't want `Apache-2.0`** because it's not compatible with `GPL-2.0`
     according to **[[G]]** (but it's worth mentioning that it's with
     `GPL-3.0`, see **[[H]]**)
    - `MPL-2.0` is compatible with `GPL` familly and also with
     `MIT`/`BSD-x`/`Apache-2.0` (see **[[I]]**)
    - `MPL-2.0` "is a simple copyleft license. The MPL's "file-level" copyleft
      is designed to encourage contributors to share modifications they make to
      your code, while still allowing them to combine your code with code under
      other licenses (open or proprietary) with minimal restrictions." (see
      **[[I]]**)
    - choosing Copyleft (in general) over Copyfree (a.k.a permissive) is **a
      (sad) lesson learned from the story of "Patrick"** described by Pieter
      Hintjens in **[[A]]**


**Verdict:** I choose `MPL-2.0` if project is not silly, otherwise I choose
`BSD-2`. `MPL-2.0` seems to be a sweet spot between free software and
enterprise world.


## Also check
* [The FreeBSD Copyright](https://www.freebsd.org/copyright/freebsd-license/)
  (a.k.a. "Simplified BSD License" a.k.a. 2-clause license)
* [Mozilla Public License Version 2.0](https://www.mozilla.org/en-US/MPL/2.0/)
* [APACHE LICENSE, VERSION 2.0](https://www.apache.org/licenses/LICENSE-2.0)
* [The 4.4BSD Copyright](https://www.freebsd.org/copyright/license/) (a.k.a.
  original "BSD License")
* [GNU General Public License family](https://www.gnu.org/licenses/licenses.html)
* [Eclipse Public License - v 2.0](https://www.eclipse.org/legal/epl-2.0/)
  (especially `4. COMMERCIAL DISTRIBUTION`)


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
* [I] - MPL 2.0 FAQ
* [J] - "Open Source Software Licenses 101: Mozilla Public License 2.0"
  `fossa.com` blogpost


[primer]: https://blog.svgames.pl/files/hacktoberfest2017-licences.pdf
[A]: https://zguide.zeromq.org/docs/chapter6/#Eat-Me
[B]: https://zguide.zeromq.org/docs/chapter6/#The-Importance-of-Contracts
[C]: https://fossa.com/blog/open-source-licenses-101-apache-license-2-0/
[D]: https://github.blog/2015-03-09-open-source-license-usage-on-github-com/
[E]: https://en.wikipedia.org/wiki/Copyleft#Strong_and_weak_copyleft
[F]: http://wiki.zeromq.org/area:licensing
[G]: https://www.gnu.org/licenses/license-list.en.html#apache2
[H]: https://www.apache.org/licenses/GPL-compatibility.html
[I]: https://www.mozilla.org/en-US/MPL/2.0/FAQ/
[J]: https://fossa.com/blog/open-source-software-licenses-101-mozilla-public-license-2-0/
