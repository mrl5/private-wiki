# Building APIs

## Content
- [Principles](#principles)
- [API versioning](#api-versioning)
- [API first approach](#api-first-approach)
- [API design first vs API code first](#api-design-first-vs-api-code-first)
- [Also check](#also-check)


## Principles
- [json:api] specification, recommendations, examples
- [Zalando guidelines]
- [Creating Good API Errors in REST, GraphQL and gRPC] blog post by [Phil Sturgeon]
- [RFC 7807] Problem Details for HTTP APIs
- [Caching is hard, draw me a picture] blog post by [Phil Sturgeon]

Quotes from [Automated Style Guides for REST, GraphQL and gRPC] blog post by [Phil Sturgeon]:
> Security
> - Ban HTTP Basic entirely
> - Make sure every endpoint has some sort of security (OAuth 2, API Key, but not both)
> - Every response should support application/vnd.api+json (JSON:API) not just plain-old JSON
> - ID's as integers let people crawl your API incredibly easily, switch to UUID

> Errors
> - Your 20X response seems to have errors in it, why do you hate your consumers
> - There are no URLs in your errors, how can anyone find out more information about what went wrong
> - Error format should be RFC 7807

> Versioning
> - Keep version numbers out of the URL
> - Version numbers in headers please
> - Ban all versioning and demand evolution (prepare for battle)


## API versioning
1. https://apisyouwonthate.com/blog/api-versioning-has-no-right-way
2. https://medium.com/good-api/api-change-management-2fe5bba32e9b


## API first approach
(in general [OpenAPI Specification] as a contract)

from [Understanding the API-First Approach to Building Products] by Janet
Wagner:
> An API-first approach means that for any given development project, your APIs
> are treated as "first-class citizens".

from [Zalando principles]:
> API First is one of our engineering and architecture principles. In a
> nutshell API First requires two aspects:
>  - define APIs first, before coding its implementation, using a standard specification language
>  - get early review feedback from peers and client developers

## API design first vs API code first

### Golden thoughts from [APIs you won't hate] blog
from [There's No Reason to Write OpenAPI By Hand] blog post by [Phil Sturgeon]:
> Some API developers use API descriptions to plan the interface of an API
> before building it, which is known as the "API design first" workflow. Others
> build the API then generate (or manually produce) API descriptions later,
> which is the "code-first" workflow.

from [API Design-First vs Code First] blog post by [Phil Sturgeon]:
> With API descriptions rising in popularity, the main question I hear folks
> asking about is "API Design-first" or "code-first". This is a bit of a
> misleading question because these are not two unique things, there are a few
> variants.

> **Code-First, Write Docs "When We Have Time"**
>
> **Code-First, then Annotate**
>
> **Design First, Ditch for Code First**
>
> **Design-First, Evolve with Code**

from [WeWork’s API Specification Workflow] blog post by [Phil Sturgeon]:
![workflow](https://apisyouwonthate.com/static/fd5229a63ea93feebd0635a8b3ac2bb2/a24e6/workfow.jpg)


## Also check
- https://openapi.tools/
- linter for OAS: https://www.npmjs.com/package/@stoplight/spectral-cli


[OpenAPI Specification]: https://swagger.io/specification/
[Understanding the API-First Approach to Building Products]: https://swagger.io/resources/articles/adopting-an-api-first-approach/
[Zalando principles]: https://opensource.zalando.com/restful-api-guidelines/#api-first
[APIs you won't hate]: https://apisyouwonthate.com/blog/
[There's No Reason to Write OpenAPI By Hand]: https://apisyouwonthate.com/blog/theres-no-reason-to-write-openapi-by-hand
[Phil Sturgeon]: https://apisyouwonthate.com/author/phil-sturgeon
[API Design-First vs Code First]: https://apisyouwonthate.com/blog/api-design-first-vs-code-first
[FastAPI]: https://github.com/tiangolo/fastapi
[connexion]: https://github.com/zalando/connexion
[WeWork’s API Specification Workflow]: https://apisyouwonthate.com/blog/weworks-api-specification-workflow
[tsoa]: https://github.com/lukeautry/tsoa
[fastify-swagger]: https://github.com/fastify/fastify-swagger
[json:api]: https://jsonapi.org/
[Zalando guidelines]: https://opensource.zalando.com/restful-api-guidelines/
[Caching is hard, draw me a picture]: https://apisyouwonthate.com/blog/caching-is-hard-draw-me-a-picture
[RFC 7807]: https://datatracker.ietf.org/doc/html/rfc7807
[Creating Good API Errors in REST, GraphQL and gRPC]: https://apisyouwonthate.com/blog/creating-good-api-errors-in-rest-graphql-and-grpc
[Automated Style Guides for REST, GraphQL and gRPC]: https://apisyouwonthate.com/blog/automated-style-guides-for-rest-graphql-and-grpc
