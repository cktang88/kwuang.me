---
title: The evolution of GraphQL frameworks in the past few years
description: This post describes the evolution of the GraphQL ecosystem in the past few years as I've seen it.
date: 2020-07-12
tags:
- graphql
- programming
- webdev
layout: layouts/post.njk

---
[GraphQL](https://graphql.org/) started in Facebook in 2012 as a way to more easily query data with less boilerplate. It allows simply ask for the exact fields you want, and have one query that queries many models at once, among other things. In 2015, Facebook decided to make it open source, and the GraphQL organization took over ownership of the [specification](https://spec.graphql.org/) and JavaScript reference implementation ([GraphQL.js](https://github.com/graphql/graphql-js)).

[Graphcool](https://www.graph.cool/), founded in 2016, was one of the earliest companies to develop frameworks and systems that accelerated and made possible wider adoption of GraphQL in applications.

In 2016, Facebook created their own client library called [Relay Classic](https://relay.dev/). They [released Relay Modern](https://engineering.fb.com/data-infrastructure/relay-modern-simpler-faster-more-extensible/) in April 2017 which was more extensible, easier to use, and more performant. Relay is now in [v10](https://github.com/facebook/relay/releases/tag/v10.0.0). 



Apollo is another major player. 

Apollo-server v1 was [announced](https://www.apollographql.com/blog/apollo-server-1-0-a-graphql-server-for-all-node-js-frameworks-2b37d3342f7c/) in July 2017. 

In October 2017, Apollo also [released](https://www.apollographql.com/blog/graphql-tools-2-0-with-schema-stitching-8944064904a5/) [graphql-tools](https://github.com/ardatan/graphql-tools) v2.0 with schema stitching, a handy feature that enabled building up larger schemas from multiple smaller ones.

[Apollo-server 2.0](https://www.apollographql.com/blog/apollo-server-2-0-30c9bbb4ab5e/) was released in July 2018. Compared to the first version of Apollo-server, it focused on improving developer experience, including best development patterns for common uses, and further abstractions.

Apollo-server v2 seems to have taken a lot of inspiration from Graphql-yoga, so much so that [graphql yoga has effectively been deprecated](https://github.com/prisma-labs/graphql-yoga/issues/449#issuecomment-430540661).



[Apollo-client] reached [v1](https://github.com/apollographql/apollo-client/releases/tag/v1.0.0) on March 30, 2017. Apollo-client [v2](https://www.apollographql.com/blog/apollo-client-2-0-5c8d0affcec7/) (released October 2017) was rewritten to be much more modular, and moved to using observables instead of promises. It also introduced [Apollo-link](https://github.com/apollographql/apollo-link) as a client-side network layer. Simultaneously, [Apollo-engine](https://www.apollographql.com/blog/apollo-engine-and-graphql-error-tracking-e7dd3ce8b99d/) was released, enabling monitoring and visualizing the health and errors of applications.

In January 2018, Graphcool [released a new library](https://www.prisma.io/blog/introducing-prisma-1ff423fd629e) called Prisma, a GraphQL layer over the database.

On May 15, 2018, Graphcool [rebranded as Prisma](https://www.prisma.io/blog/prisma-raises-4-5m-to-build-the-graphql-data-layer-for-all-databases-663484df0f60).



[GraphiQL](https://github.com/graphql/graphiql) is the reference implementation of the GraphQL IDE.

Prisma's GraphQL Playground then joined forces with GraphiQL, so that Playground 2.0 would be integrated.



[express-graphql](https://github.com/graphql/express-graphql) is one of the oldest GraphQL server frameworks for JavaScript. Because it is used as an Express middleware, it presents very little disruption to current systems already using a REST API, or those who are already familiar with GraphQL.

Graphcool also introduced [graphql-yoga](https://github.com/prisma-labs/graphql-yoga) which sought to eliminate the boilerplate and manual work in configuring `apollo-server` and  `express-graphql`.

[yoga2](https://github.com/prisma-labs/yoga2) hasn't been actively maintained for over a year now, since Nexus is now the [recommended](https://www.prisma.io/docs/understand-prisma/prisma-in-your-stack) way to use Prisma as a client-facing GraphQL API layer.

[Dotan Simha](https://github.com/dotansimha) created [graphql-code-generator](https://graphql-code-generator.com/) which autogenerates code.

[graphqlgen](https://github.com/prisma-labs/graphqlgen#deprecation-note) was [deprecated](https://github.com/prisma-labs/graphqlgen/pull/484) in favor of `graphql-code-generator` in August 2019.

[TypeGraphQL](https://typegraphql.com/) is yet another framework. TypeGraphQL has an [integration](https://github.com/MichalLytek/type-graphql/issues/476) with Prisma.

[Apollo Federation](https://www.apollographql.com/docs/apollo-server/federation/introduction/) is an infrastructure-level technology. It allows microservices to individually implement separate schemas, and uses a "gateway" to present a unified API to the client.

[Prisma 2.0](https://www.prisma.io/) was released in Jan 21, 2020, after a rename: Photon.js became Prisma Client, and Lift became Prisma Migrate.



Even Amazon has jumped in with [AWS Appsync](https://aws.amazon.com/appsync/) in November 2017, offering real-time data sync between web and mobile applications, as a fully-managed hosted GraphQL solution.



[Nexus](https://nexus.js.org/) was originally created by [Tim Griesser](https://github.com/tgriesser). On February 5, 2020, the original nexus [transitioned](https://github.com/graphql-nexus/schema/issues/373) to becoming `@nexus/schema`. And the Nexus package itself became a framework on top of `@nexus/schema` and moved to a new site, https://nexusjs.org/. This aligned with a new line of thinking around how to best develop GraphQL software, a shift from [schema-first](https://blog.logrocket.com/code-first-vs-schema-first-development-graphql/) to [code-first](https://www.prisma.io/blog/introducing-graphql-nexus-code-first-graphql-server-development-ll6s1yy5cxl5/). 

Apollo-client is now on [v3.0](https://github.com/apollographql/apollo-client/releases/tag/v3.0.0) which focused the library on caching.



[Apollo-boost](https://www.npmjs.com/package/apollo-boost) which advertises to be _"The fastest, easiest way to get started with Apollo Client!"_  contains `react-apollo`, `apollo-client`, `apollo-link`, the in-memory cache, and more, is a fast way to get started with Apollo-client.



[Apollo-explorer](https://www.apollographql.com/blog/introducing-the-apollo-explorer/) was introduced on June 30, 2020. Apollo-explorer was [renamed](https://www.apollographql.com/blog/graph-manager-is-now-studio/) from Apollo Graph Manager, which was introduced last year.



On the other hand, there are software that seek to be a batteries-included GraphQL API layer over an existing database, with little or no configuration or coding involved, such as [Hasura](https://hasura.io/) and [Postgraphile](https://www.graphile.org/postgraphile/), both of which are open-source.



[Blitz.js](https://github.com/blitz-js/blitz) aims to entirely remove the concept of an API, enabled by full server-side rendering and templating with Next.js.

[Redwood.js](https://redwoodjs.com/) aims to be a fully serverless platform.

GraphQL tooling is still in its youth, and the future looks pretty exciting.