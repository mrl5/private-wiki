# Notable materials grab-bag

* [Pieter Hintjens] - his speeches are pure gold. Love his philosophy
  - [Distribution, Scale and Flexibility with ZeroMQ](https://www.youtube.com/watch?v=yhGXJ9Jt3-A)
  - [Homepage](http://hintjens.com/)
  - keywords:
    - encouraging failure + learning from failure = pattern for learning
    - collaboration instead of hierarchy (low formality)
    - [Conway's law]
    - decentralization
    - asynchronicity
    - lazy execution of prioritized events
    - distributed development = scalability
    - delivering value - every code change is linked to a tangible problem
    - short term visibility of tasks / task queues
* [Plugin Oriented Programming]
  - anti monolithic design
  - `Write programs that do one thing and do it well`
  - `Write programs to work together`
  - `Write programs to expose interfaces that can be easily merged together`
* [Mastering Chaos - A Netflix Guide to Microservices]
  - cool insights on monolithic patterns in distributed infra
  - keywords:
    - cascading failure
    - fault injection testing
    - identifying critical microservices in ecosystem
    - bare bone REST vs client libraries
    - [CAP theorem]; [eventual consistency]
    - multi region strategy
    - stateless service ([pets vs cattle])
    - cache patterns and anti patterns ([EVCache] + solutions)
    - "production ready" checklist
    - polyglot & containers (the paved road vs off-road) -> cost of variance
    - velocity with confidence
    - [Conway's law] -> solution's first, team second


[Pieter Hintjens]: https://en.wikipedia.org/wiki/Pieter_Hintjens
[Conway's law]: https://en.wikipedia.org/wiki/Conway%27s_law

[Plugin Oriented Programming]: https://pop-book.readthedocs.io/en/latest/

[Mastering Chaos - A Netflix Guide to Microservices]: https://www.youtube.com/watch?v=CZ3wIuvmHeM
[CAP theorem]: https://en.wikipedia.org/wiki/CAP_theorem
[eventual consistency]: https://en.wikipedia.org/wiki/Eventual_consistency
[pets vs cattle]: http://cloudscaling.com/blog/cloud-computing/the-history-of-pets-vs-cattle/
[EVCache]: https://github.com/Netflix/EVCache
