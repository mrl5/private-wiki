# Notable materials grab-bag

## Content
- [Pieter Hintjens philosophy](#pieter-hintjens-philosophy)
- [Plugin Oriented Programming](#plugin-oriented-programming)
- [Netflix Guide to Microservices](#netflix-guide-to-microservices)
- [Command-query Separation](#command-query-separation)
- [Patterns of Effective Teams](#patterns-of-effective-teams)
- [API first](#api-first)
- [Kubernetes random](#kubernetes-random)


## Pieter Hintjens philosophy
[Pieter Hintjens](https://en.wikipedia.org/wiki/Pieter_Hintjens) - his speeches
are pure gold. Love his philosophy
- [Distribution, Scale and Flexibility with ZeroMQ](https://www.youtube.com/watch?v=yhGXJ9Jt3-A)
- [Keynote | EuroSciPy 2015 | Pieter Hintjens](https://www.youtube.com/watch?v=O8CbzKREAj4)
- [Homepage](http://hintjens.com/)
- [Social Architecture - Building On-line Communities](https://hintjens.gitbooks.io/social-architecture/content/)
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
  - [Actor model](https://en.wikipedia.org/wiki/Actor_model)


## Plugin Oriented Programming
[Plugin Oriented Programming book](https://pop-book.readthedocs.io/en/latest/)
- anti monolithic design
- `Write programs that do one thing and do it well`
- `Write programs to work together`
- `Write programs to expose interfaces that can be easily merged together`


## Netflix Guide to Microservices
[Mastering Chaos - A Netflix Guide to
Microservices](https://www.youtube.com/watch?v=CZ3wIuvmHeM)
- cool insights on monolithic patterns in distributed infra
- keywords:
  - cascading failure
  - fault injection testing
  - identifying critical microservices in ecosystem
  - bare bone REST vs client libraries
  - [CAP theorem](https://en.wikipedia.org/wiki/CAP_theorem); [eventual consistency](https://en.wikipedia.org/wiki/Eventual_consistency)
  - multi region strategy
  - stateless service ([pets vs cattle](http://cloudscaling.com/blog/cloud-computing/the-history-of-pets-vs-cattle/))
  - cache patterns and anti patterns ([EVCache](https://github.com/Netflix/EVCache) + solutions)
  - "production ready" checklist
  - polyglot & containers (the paved road vs off-road) -> cost of variance
  - velocity with confidence
  - [Conway's law] -> solution's first, team second


## Command-query Separation
[7 Reasons why your microservices should use Event Sourcing & CQRS - Hugh
McKee](https://www.youtube.com/watch?v=wBvH7foXXUY)
- System of loosely coupled services
  1. independently deployable
  2. owns its schema
  3. API only access to data
- 7 Reasons why to use Event Sourcing & CQRS:
  1. smooth transition from DDD & event storming to implementation
  2. reduce service coupling
  3. break the read vs write performance bottleneck
  4. elevate the concurrency barrier
  5. simplify and harden messaging
  6. eliminate service coupling
  7. graduate from IT nursery


## Patterns of Effective Teams
[GOTO 2017 • Patterns of Effective Teams • Dan
North](https://www.youtube.com/watch?v=lvs7VEsQzKY)


## API first
- [building apis prvate wiki](apis.md)
- [Enterprise Integration Using REST](https://martinfowler.com/articles/enterpriseREST.html)


## Kubernetes random
- [k8s learning path](https://developer.ibm.com/technologies/security/series/kubernetes-learning-path)
- [k8s with api gw](https://learnk8s.io/kubernetes-ingress-api-gateway)
- [Traefik](https://doc.traefik.io/traefik/)
- [gloo-edge](https://docs.solo.io/gloo-edge/latest/)
- [gloo-mesh](https://docs.solo.io/gloo-mesh/latest/)




[Conway's law]: https://en.wikipedia.org/wiki/Conway%27s_law
