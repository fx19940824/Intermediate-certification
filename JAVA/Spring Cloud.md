# 微服务架构概述
## 微服务架构第一要素：业务建模
- 微服务架构设计首要的切入点为服务建模
- 服务建模推荐使用领域驱动设计（Domain Driven Design，DDD）
## 微服务架构第二要素-技术体系
1. 服务通信
    1. 网络连接模式
    2. I/O模型
    3. 服务调用方式
2. 服务治理
3. 服务路由
4. 服务容错
5. 服务网关
6. 服务配置
7. 服务安全
8. 服务监控
## 微服务架构第三要素：研发过程

# Spring Cloud概述

## Eureka组件
http://www.ityouknow.com/springcloud/2017/05/10/springcloud-eureka.html
Spring Cloud 封装了 Netflix 公司开发的 Eureka 模块来实现服务注册和发现。Eureka 采用了 C-S 的设计架构。Eureka Server 作为服务注册功能的服务器，它是服务注册中心。而系统中的其他微服务，使用 Eureka 的客户端连接到 Eureka Server，并维持心跳连接。这样系统的维护人员就可以通过 Eureka Server 来监控系统中各个微服务是否正常运行。Spring Cloud 的一些其他模块（比如Zuul）就可以通过 Eureka Server 来发现系统中的其他微服务，并执行相关的逻辑。

Eureka由两个组件组成：Eureka服务器和Eureka客户端。Eureka服务器用作服务注册服务器。Eureka客户端是一个java客户端，用来简化与服务器的交互、作为轮询负载均衡器，并提供服务的故障切换支持。Netflix在其生产环境中使用的是另外的客户端，它提供基于流量、资源利用率以及出错状态的加权负载均衡。
## Zookeeper组件
https://juejin.cn/post/6857670670726529037
Apache ZooKeeper 是一个开放源码的分布式应用程序协调组件，是 Hadoop 和 Hbase 的重要组件。它是一个为分布式应用提供一致性服务的软件，提供的功能包括：配置维护、域名服务、分布式同步、组服务等。
ZooKeeper 是一个分布式的，开放源码的分布式应用程序协调服务，是 Google 的 Chubby 一个开源的实现，是 Hadoop 和 Hbase 的重要组件。它是一个为分布式应用提供一致性服务的软件，提供的功能包括：配置维护、域名服务、分布式同步、组服务等。ZooKeeper 的目标就是封装好复杂易出错的关键服务，将简单易用的接口和性能高效、功能稳定的系统提供给用户。ZooKeeper 包含一个简单的原语集，提供 Java 和 C 的接口。ZooKeeper 代码版本中，提供了分布式独享锁、选举、队列的接口。其中分布锁和队列有 Java 和 C 两个版本，选举只有 Java 版本。
## Hystrix组件
https://fangjian0423.github.io/2017/02/19/springcloud-hystrix/
Hystrix是一个供分布式系统使用，提供延迟和容错功能，保证复杂的分布系统在面临不可避免的失败时，仍能有其弹性。

比如系统中有很多服务，当某些服务不稳定的时候，使用这些服务的用户线程将会阻塞，如果没有隔离机制，系统随时就有可能会挂掉，从而带来很大的风险。

SpringCloud使用Hystrix组件提供断路器、资源隔离与自我修复功能。下图表示服务B触发了断路器，阻止了级联失败。
## Sentinel组件
https://www.jianshu.com/p/d36f55ef2688
随着微服务的流行，服务和服务之间的稳定性变得越来越重要。Sentinel阿里中间件团队开源的，面向分布式服务架构的轻量级高可用流量控制组件，主要以流量为切入点，从流量控制、熔断降级、系统负载保护等多个维度来帮助您保护服务的稳定性。
## OpenFeign组件
https://blog.csdn.net/qq_42682745/article/details/117884170
## Config配置中心
https://www.cnblogs.com/fengzheng/p/11242128.html
## Spring Cloud Task
https://www.codenong.com/s-guide-to-spring-cloud-task-short-lived-spring-boot-microservices/
通常，预计服务将长期运行。 一个普通的Spring Boot服务包括一个嵌入式Web服务器，例如Tomcat，Jetty或Undertow。 服务被终止是因为它被有意停止或发生了诸如OOM(OutOfMemoryError)之类的运行时错误。

Spring Boot是通过这种方式构建的，但是随着范式的转变和微服务体系结构的流行，许多服务变得短暂。 由于短暂的通知服务不需要具有嵌入式服务器，因此重量过大，并且可能轻巧得多。
## Jenkins
https://blog.csdn.net/zhuyu19911016520/article/details/85270269
简单来说，大型系统拆分为多个服务后，每个小团队负责一个服务，服务的更新、发布会变得很频繁，通过工具监控代码的每次提交，持续进行自动化的构建过程，就是持续集成。
## Docker
## Kubernetes
https://cloud.tencent.com/developer/article/1424466
当我们构建微服务解决方案时，SpringCloud和Kubernetes都是最佳解决方案，因为它们为解决最常见的挑战提供组件。但是，如果我们决定选择Kubernetes作为我们的解决方案的主要容器管理器和部署平台，我们仍然可以主要通过SpringCloudKubernetes项目使用SpringCloud的有趣特性。这个相对较新的项目无疑可以与Kubernetes轻松集成Spring Boot应用程序。在开始之前，了解如何在Minikube（本地Kubernetes环境）上部署Spring Boot应用程序可能会有所帮助。