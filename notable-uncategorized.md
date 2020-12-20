# Notable materials grab-bag

* [Pieter Hintjens] - his speeches are pure gold. Love his philosophy
  - [Distribution, Scale and Flexibility with ZeroMQ](https://www.youtube.com/watch?v=yhGXJ9Jt3-A)
  - [Keynote | EuroSciPy 2015 | Pieter Hintjens](https://www.youtube.com/watch?v=O8CbzKREAj4)
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
* [API first]
  - [Zalando guidelines]
  - [Enterprise Integration Using REST]
  - [Open API tools and integrations]
  - [connexion] framework that automagically handles HTTP requests based on
    OpenAPI Specification + [Crafting Effective Microservices in Python]
    tutorial
* Kubernetes random
  - [k8s learning path]
  - [k8s with api gw]
  - [gloo-edge]
  - [gloo-mesh]



[Pieter Hintjens]: https://en.wikipedia.org/wiki/Pieter_Hintjens
[Conway's law]: https://en.wikipedia.org/wiki/Conway%27s_law

[Plugin Oriented Programming]: https://pop-book.readthedocs.io/en/latest/

[Mastering Chaos - A Netflix Guide to Microservices]: https://www.youtube.com/watch?v=CZ3wIuvmHeM
[CAP theorem]: https://en.wikipedia.org/wiki/CAP_theorem
[eventual consistency]: https://en.wikipedia.org/wiki/Eventual_consistency
[pets vs cattle]: http://cloudscaling.com/blog/cloud-computing/the-history-of-pets-vs-cattle/
[EVCache]: https://github.com/Netflix/EVCache

[API first]: https://www.oreilly.com/content/an-api-first-approach-for-cloud-native-app-development/
[Zalando guidelines]: https://opensource.zalando.com/restful-api-guidelines/#api-first
[Enterprise Integration Using REST]: https://martinfowler.com/articles/enterpriseREST.html
[Open API tools and integrations]: https://swagger.io/tools/open-source/open-source-integrations/
[connexion]: https://github.com/zalando/connexion
[Crafting Effective Microservices in Python]: https://engineering.zalando.com/posts/2016/12/crafting-effective-microservices-in-python.html

[k8s learning path]: https://developer.ibm.com/technologies/security/series/kubernetes-learning-path
[k8s with api gw]: https://learnk8s.io/kubernetes-ingress-api-gateway
[gloo-edge]: https://docs.solo.io/gloo-edge/latest/
[gloo-mesh]: https://docs.solo.io/gloo-mesh/latest/
