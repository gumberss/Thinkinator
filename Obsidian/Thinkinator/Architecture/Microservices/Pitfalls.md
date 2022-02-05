## [[Microservices]] [[Pitfalls]]

#### I want to adopt microservices

-   Please, think with your team, do you really need to adopt microservices?
-   Microservices has a lot of trade-offs and it is hard to maintain!
-   Your company must have resources to adopt it, in my point of view, microservices is a very good aproach when you have a product with very much people working on, when it's hard to merge a pull request, beacuse other developer did it first, and his pull request conflicted with yours.
-   Microservice architecture is to make a company scale its product in business, separating developers in small teams where each team work in a part of the system (bounded context) caled microservice, and all the teams **together** scale a product.
-   Think with me, you are a CTO of an startup, and you have 5 developers, you do not have much money and time and you are trying to release a minimum viable product (MVP), will you use microservices to build your product?
    -   I don't know, and I wont decide it for you, but, If I were that CTO, I wouldn't use microservices, because I have no much developers and the bootstrap of microservice is expensive, CI/CD, monitoring, centralized logs, Eventual consistency, compensate events, all of it is hard to deal with and I do not have so much money and time. So, I would start with a monolith and if the system need business scale because the MVP was viable and the company start getting customers and investor, decompose to microservices :)

#### [](https://github.com/gumberss/Thinkinator/blob/main/Microservices/2%20-%20Pitfalls.md#when-you-need-to-create)When you need to create

-   Quote 5 drawbacks of microservices and always remember that you will handle with this for the rest of the product's life
-   Don't turn every noun in your domain into a microservice (It'll make you create anemic CRUD microservices)