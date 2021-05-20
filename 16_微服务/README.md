# 微服务

微服务是分布式系统中最近比较流行的架构模型，也是 SOA 架构的一个进化。微服务架构并不是银弹，所以，也不要寄希望于微服务架构能够解决所有的问题。微服务架构主要解决的是如何快速地开发和部署我们的服务，这对于一个能够适应快速开发和成长的公司是非常必要的。同时我也觉得，微服务中有很多很不错的想法和理念，所以学习微服务是每一个技术人员迈向卓越的架构师的必经之路。

首先，你需要看一下，Martin Fowler 的这篇关于微服务架构的文档 - [Microservice Architecture](https://martinfowler.com/articles/microservices.html) （[中译版](https://blog.csdn.net/wurenhai/article/details/37659335)），这篇文章说明了微服务的架构与传统架构的不同之处在于，微服务的每个服务与其数据库都是独立的，可以无依赖地进行部署。你也可以看看 Martin Fowler 老人家现身说法的[视频](https://www.youtube.com/watch?v=wgdBVIX9ifA)。

另外，你还可以简单地浏览一下，各家对微服务的理解。

* [AWS 的理解 - What are Microservices?](https://aws.amazon.com/cn/microservices/)

* [Microsoft 的理解 - Microservices architecture style](https://docs.microsoft.com/en-us/azure/architecture/guide/architecture-styles/microservices)

* [Pivotal 的理解 - Microservices](https://tanzu.vmware.com/microservices)

## 微服务架构

接下来，你可以看一下 [IBM 红皮书：Microservices Best Practices for Java](https://www.redbooks.ibm.com/redbooks/pdfs/sg248357.pdf) ，这本书非常好，不但有通过把 Spring Boot 和 Dropwizard 来架建 Java 的微服务，而且还谈到了一些标准的架构模型，如服务注册、服务发现、API 网关、服务通讯、数据处理、应用安全、测试、部署、运维等，是相当不错的一本书。

当然，有一本书你也可以读一下—— [微服务设计](https://book.douban.com/subject/26772677/)。这本书全面介绍了微服务的建模、集成、测试、部署和监控，通过一个虚构的公司讲解了如何建立微服务架构。主要内容包括认识微服务在保证系统设计与组织目标统一上的重要性，学会把服务集成到已有系统中，采用递增手段拆分单块大型应用，通过持续集成部署微服务，等等。

与此相似的，也有其它的一系列文章，值得一读。

下面是 Nginx 上的一组微服务架构的系列文章。

* [Introduction to Microservices](https://www.nginx.com/blog/introduction-to-microservices/)

* [Building Microservices: Using an API Gateway](https://www.nginx.com/blog/building-microservices-using-an-api-gateway/)

* [Building Microservices: Inter-Process Communication in a Microservices Architecture](https://www.nginx.com/blog/building-microservices-inter-process-communication/)

* [Service Discovery in a Microservices Architecture](https://www.nginx.com/blog/service-discovery-in-a-microservices-architecture/)

* [Event-Driven Data Management for Microservices](https://www.nginx.com/blog/event-driven-data-management-microservices/)

* [Choosing a Microservices Deployment Strategy](https://www.nginx.com/blog/deploying-microservices/)

* [Refactoring a Monolith into Microservices](https://www.nginx.com/blog/refactoring-a-monolith-into-microservices/)

下面这是 [Auto0 Blog](https://auth0.com/blog/) 上一系列的微服务的介绍，有代码演示。

* [An Introduction to Microservices, Part 1](https://auth0.com/blog/an-introduction-to-microservices-part-1/)

* [API Gateway. An Introduction to Microservices, Part 2](https://auth0.com/blog/an-introduction-to-microservices-part-2-API-gateway/)

* [An Introduction to Microservices, Part 3: The Service Registry](https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/)

* [Intro to Microservices, Part 4: Dependencies and Data Sharing](https://auth0.com/blog/introduction-to-microservices-part-4-dependencies/)

* [API Gateway: the Microservices Superglue](https://auth0.com/blog/apigateway-microservices-superglue/)

还有 Dzone 的这个 Spring Boot 的教程。

* [Microservices With Spring Boot - Part 1 - Getting Started](https://dzone.com/articles/microservices-with-spring-boot-part-1-getting-star)

* [Microservices With Spring Boot - Part 2 - Creating a Forex Microservice](https://dzone.com/articles/microservices-with-spring-boot-part-2-creating-a-f)

* [Microservices With Spring Boot - Part 3 - Creating Currency Conversion Microservice](https://dzone.com/articles/microservices-with-spring-boot-part-3-creating-cur)

* [Microservices With Spring Boot - Part 4 - Using Ribbon for Load Balancing](https://dzone.com/articles/microservices-with-spring-boot-part-4-using-ribbon)

* [Microservices With Spring Boot - Part 5 - Using Eureka Naming Server](https://dzone.com/articles/microservices-with-spring-boot-part-5-using-eureka)

当然，如果你要玩得时髦一些的话，我推荐你使用下面的这套架构。

* 前端：[React.js](https://reactjs.org/) 或 [Vue.js](https://vuejs.org/)。

* 后端：[Go 语言](https://golang.org/) + 微服务工具集 [Go kit](https://gokit.io/) ，因为是微服务了，所以，每个服务的代码就简单了。既然简单了，也就可以用任何语言了，所以，我推荐 Go 语言。

* 通讯：[gRPC](https://grpc.io/)，这是 Google 远程调用的一个框架，它比 Restful 的调用要快 20 倍到 50 倍的样子。

* API：[Swagger](https://swagger.io/) ，Swagger 是一种 Restful API 的简单但强大的表示方式，标准的，语言无关，这种表示方式不但人可读，而且机器可读。可以作为 Restful API 的交互式文档，也可以作为 Restful API 形式化的接口描述，生成客户端和服务端的代码。今天，所有的 API 应该都通过 Swagger 来完成。

* 网关：[Envoy](https://www.envoyproxy.io/) 其包含了服务发现、负载均衡和熔断等这些特性，也是一个很有潜力的网关。当然，Kubernetes 也是很好的，而且它也是高扩展的，所以，完全可以把 Envoy 通过 Ingress 集成进 Kubernetes。这里有一个开源项目就是干这个事的 - [contour](https://github.com/projectcontour/contour)。

* 日志监控：[fluentd](https://www.fluentd.org/) + [ELK](https://www.elastic.co/cn/webinars/introduction-elk-stack) 。

* 指标监控：[Prometheus](https://prometheus.io/) 。

* 调用跟踪：[Jaeger](https://www.jaegertracing.io/docs/1.22/) 或是 [Zipkin](https://zipkin.io/)，当然，后者比较传统一些，前者比较时髦，最重要的是，其可以和 Prometheus 和 Envory 集成。

* 自动化运维：[Docker](https://www.docker.com/) + [Kubernetes](https://kubernetes.io/) 。

## 微服务和 SOA

在对微服务有了一定的认识以后，一定有很多同学分不清楚微服务和 SOA 架构，对此，你可以看一下这本电子书 - 《[Microservices vs. Service-Oriented Architecture](https://www.nginx.com/resources/library/microservices-vs-soa/)》。通过这本书，你可以学到，服务化架构的一些事实，还有基础的 SOA 和微服务的架构知识，以及两种架构的不同。这本书的作者马克·理查兹（Mark Richards）同学拥有十年以上的 SOA 和微服务架构的设计和实现的经验。

另外，还有几篇其它对比 SOA 和微服务的文章你也可以看看。

* [DZone: Microservices vs. SOA](https://dzone.com/articles/microservices-vs-soa-2)

* [DZone: Microservices vs. SOA - Is There Any Difference at All?](https://dzone.com/articles/microservices-vs-soa-is-there-any-difference-at-al)

* [Microservices, SOA, and APIs: Friends or enemies?](https://www.ibm.com/cloud/learn/microservices)

除此之外，我们还需要知道微服务和其它架构的一些不同和比较，这样我们就可以了解微服务架构的优缺点。下面几篇文章将帮助获得这些知识。

* [PaaS vs. IaaS for Microservices Architectures: Top 6 Differences](https://www.altoros.com/blog/paas-vs-iaas-for-microservices-architectures-top-6-differences/)

* [Microservices vs. Monolithic Architectures: Pros, Cons, and How Cloud Foundry (PaaS) Can Help](https://www.slideshare.net/altoros/microservices-vs-monolithic-architectures-pros-and-cons)

* [Microservices - Not A Free Lunch!](http://highscalability.com/blog/2014/4/8/microservices-not-a-free-lunch.html)

* [The Hidden Costs Of Microservices](https://www.stackbuilders.com/news/the-hidden-costs-of-microservices)

## 设计模式和最佳实践

然后，你可以看一下微服务的一些设计模式。

* [Microservice Patterns](https://microservices.io/)，微服务架构的设计模式和最佳实践。

* [Microservice Antipatterns and Pitfalls](https://www.oreilly.com/content/microservices-antipatterns-and-pitfalls/)，微服务架构的一些已知的反模式和陷阱。

* [Microservice Architecture: All The Best Practices You Need To Know](https://codingsans.com/blog/microservice-architecture-best-practices)，这是一篇长文，里面讲述了什么是微服务、微服务架构的优缺点、微服务最大的挑战和解决方案是什么、如何避免出错，以及构建微服务架构的最佳实践等多方面的内容。推荐阅读。

* [Best Practices for Building a Microservice Architecture](https://www.vinaysahni.com/best-practices-for-building-a-microservice-architecture) ，这篇文章分享了构建微服务架构的最佳实践。

* [Simplicity by Distributing Complexity](https://engineering.zalando.com/posts/2018/01/simplicity-by-distributing-complexity.html)，这是一篇讲如何使用事件驱动构建微服务架构的文章，其中有很多不错的设计上的基本原则。

## 相关资源

* [Microservices Resource Guide](https://martinfowler.com/microservices/) ，这个网页上是 Martin Fowler 为我们挑选的和微服务相关的文章、视频、书或是 podcast。

* [Awesome Microservices](https://github.com/mfornos/awesome-microservices/) ，一个各种微服务资源和相关项目的集中地。

## 小结

好了，总结一下今天的内容。我认为，微服务中有很多很不错的想法和理念，所以学习微服务是每一个技术人员迈向卓越的架构师的必经之路。在这篇文章中，我先给出了 AWS、Microsoft 和 Pivotal 对微服务的理解；然后给出了好几个系列的教程，帮你全面学习和理解微服务架构；然后通过一系列文章帮你来区分何为微服务，何为 SOA；最后给出了微服务架构的设计模式和最佳实践，以及相关资源。相信通过这一系列内容的学习，你一定会对微服务有全面、透彻的理解。

下篇文章，我们将讲述的容器化和自动化运维方面的内容。敬请期待。