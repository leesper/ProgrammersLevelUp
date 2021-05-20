# 容器化和自动化运维

这篇文章我们来重点学习 Docker 和 Kubernetes，它们已经是分布式架构和自动化运维的必备工具了。对于这两个东西，你千万不要害怕，因为技术方面都不算复杂，只是它们的玩法和传统运维不一样，所以你不用担心，只要你花上一点时间，一定可以学好的。

## Docker

* 你可以先看一下 Docker 的官方介绍 [Docker Overview](https://docs.docker.com/get-started/overview/) 。

* 然后再去一个 Web 在线的 Playground 上体验一下， [Katacoda Docker Playground](https://www.katacoda.com/courses/docker/playground) 或者是 [Play With Docker](https://training.play-with-docker.com/) 。

* 接下来，跟着 [Learn Docker](https://github.com/dwyl/learn-docker) 这个文档中的教程自己安装一个 Docker 的环境，实操一把。

* 然后跟着 [Docker Curriculum](https://docker-curriculum.com/) 这个超详细的教程玩一下 Docker。

有了上述的一些感性体会之后，你就可以阅读 Docker 官方文档 [Docker Documentation](https://docs.docker.com/) 了，这是学习 Docker 最好的方式。

如果你想了解一下 Docker 的底层技术细节，你可以参看我的文章。

* [Docker 基础技术：Linux Namespace（上）](https://coolshell.cn/articles/17010.html)

* [Docker 基础技术：Linux Namespace（下）](https://coolshell.cn/articles/17029.html)

* [Docker 基础技术：Cgroup](https://coolshell.cn/articles/17049.html)

* [Docker 基础技术：AUFS](https://coolshell.cn/articles/17061.html)

* [Docker 基础技术：DeviceMapper](https://coolshell.cn/articles/17200.html)

还有一些不错的与 Docker 网络有关的文章你需要阅读及实践一下。

* [A container networking overview](https://jvns.ca/blog/2016/12/22/container-networking/)

* [Docker networking 101 - User defined networks](http://www.dasblinkenlichten.com/docker-networking-101-user-defined-networks/)

* [Understanding CNI (Container Networking Interface)](http://www.dasblinkenlichten.com/understanding-cni-container-networking-interface/)

* [Using CNI with Docker](http://www.dasblinkenlichten.com/using-cni-docker/)

Docker 有下面几种网络解决方案：[Calico](https://www.projectcalico.org/docker-libnetwork-is-almost-here-and-calico-is-ready/) 、[Flannel](https://github.com/flannel-io/flannel) 和 [Weave](https://github.com/weaveworks/weave) ，你需要学习一下。另外，还需要学习一下 [netshoot](https://github.com/nicolaka/netshoot) ，这是一个很不错的用来诊断 Docker 网络问题的工具集。

关于这几个容器网络解决方案的性能对比，你可以看一下下面这几篇文章或报告。

* [Battlefield: Calico, Flannel, Weave and Docker Overlay Network](http://chunqi.li/2015/11/15/Battlefield-Calico-Flannel-Weave-and-Docker-Overlay-Network/)
* [Comparison of Networking Solutions for Kubernetes](http://machinezone.github.io/research/networking-solutions-for-kubernetes/)
* [Docker Overlay Networks: Performance analysis in high-latency enviroments](https://www.delaat.net/rp/2015-2016/p50/report.pdf)

如果你对 Docker 的性能有什么问题的话，你可以看一下下面这些文章。

* [IBM Research Report: An Updated Performance Comparison of Virtual Machines and Linux Containers](https://dominoweb.draco.res.ibm.com/reports/rc25482.pdf)
* [An Introduction to Docker and Analysis of its Performance](http://paper.ijcsns.org/07_book/201703/20170327.pdf)

下面是一些和存储相关的文章。

* [Storage Concepts in Docker: Network and Cloud Storage](http://cloud-mechanic.blogspot.com/2014/10/storage-concepts-in-docker-network-and.html)
* [Storage Concepts in Docker: Persistent Storage](http://cloud-mechanic.blogspot.com/2014/10/storage-concepts-in-docker-persistent.html)
* [Storage Concepts in Docker: Shared Storage and the VOLUME directive](http://cloud-mechanic.blogspot.com/2014/10/storage-concepts-in-docker.html)

然后是跟运维相关的文章。

* [Docker Monitoring with the ELK Stack: A Step-by-Step Guide](https://logz.io/learn/docker-monitoring-elk-stack/)

最后，推荐看看 [Valuable Docker Links](http://www.nkode.io/2014/08/24/valuable-docker-links.html) ，其中收集并罗列了一系列非常不错的 Docker 文章。

### 最佳实践

下面分享一些与 Docker 相关的最佳实践。

* [Best Practices for Dockerfile](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/) ，Docker 官方文档里的 Dockerfile 的最佳实践。

* [Docker Best Practices](https://github.com/FuriKuri/docker-best-practices) ，这里收集汇总了存在于各个地方的使用 Docker 的建议和实践。

* [Container Best Practices](http://docs.projectatomic.io/container-best-practices/) ，来自 Atomic 项目，是一个介绍容器化应用程序的架构、创建和管理的协作型文档项目。

* [Eight Docker Development Patterns](http://hokstad.com/docker/patterns) ，八个 Docker 的开发模式：共享基础容器、共享同一个卷的多个开发容器、开发工具专用容器、测试环境容器、编译构建容器、防手误的安装容器、默认服务容器、胶黏容器（如英文链接不能访问，可阅读[中文版本](https://www.infoq.cn/article/2014/10/seven-docker-develop-pattern)）。

## Kubernetes

Kubernetes 是 Google 开源的容器集群管理系统，是 Google 多年大规模容器管理技术 Borg 的开源版本，也是 CNCF 最重要的项目之一，主要功能包括：

* 基于容器的应用部署、维护和滚动升级；

* 负载均衡和服务发现；

* 跨机器和跨地区的集群调度；

* 自动伸缩；

* 无状态服务和有状态服务；

* 广泛的 Volume 支持；

* 插件机制保证扩展性。

Kubernetes 发展非常迅速，已经成为容器编排领域的领导者。

首先，我推荐你阅读 Kubernetes 前世今生的一篇论文。

* [Borg, Omega, and Kubernetes](https://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/44843.pdf) ，看看 Google 这十几年来从这三个容器管理系统中得到的经验教训。

学习 Kubernetes，有两个免费的开源电子书。

* 《[Kubernetes Handbook](https://jimmysong.io/kubernetes-handbook/)》，这本书记录了作者从零开始学习和使用 Kubernetes 的心路历程，着重于经验分享和总结，同时也会有相关的概念解析。希望能够帮助你少踩坑，少走弯路，还会指引你关注 kubernetes 生态周边，如微服务构建、DevOps、大数据应用、Service Mesh、Cloud Native 等领域。
* 《[Kubernetes 指南](https://kubernetes.feisky.xyz/zh/)》，这本书旨在整理平时在开发和使用 Kubernetes 时的参考指南和实践总结，形成一个系统化的参考指南以方便查阅。

这两本电子书都不错，前者更像是一本学习教程，而且面明显广一些，还包括 Cloud Natvie、Service Mesh 以及微服务相关的东西。而后者聚焦于 Kubernetes 本身，更像一本参考书。

**另外，我这两天也读完了《Kubernetes in Action》一书，感觉写的非常好，一本很完美的教科书，抽丝剥茧，图文并茂。如果你只想读一本有关 Kubernetes 的书来学习 Kubernetes，那么我推荐你就选这本。**

但是也别忘了 Kubernetes 的官方网站：[Kubernetes.io](https://kubernetes.io/)，上面不但有[全面的文档](https://kubernetes.io/docs/home/) ，也包括一个很不错的 [官方教程](https://kubernetes.io/docs/tutorials/kubernetes-basics/) 。

此外，还有一些交互式教程，帮助你理解掌握，以及一些很不错的文章推荐你阅读。

### 一些交互式教程

* [Katacoda](https://www.katacoda.com/courses/kubernetes)

* [Kubernetes Bootcamp](https://kubernetesbootcamp.github.io/kubernetes-bootcamp/)

### 一些文章

这里还有一些不错的文档，你应该去读一下。

* [Kubernetes tips & tricks](https://opsnotice.xyz/kubernetes-tips-tricks/)

* [Achieving CI/CD with Kubernetes](http://theremotelab.com/blog/achieving-ci-cd-with-k8s/)

* [How to Set Up Scalable Jenkins on Top of a Kubernetes Cluster](https://dzone.com/articles/how-to-setup-scalable-jenkins-on-top-of-a-kubernet)

* 10 Most Common Reasons Kubernetes Deployments Fail [Part I](https://kukulinski.com/10-most-common-reasons-kubernetes-deployments-fail-part-1/) 和 [Part II](https://kukulinski.com/10-most-common-reasons-kubernetes-deployments-fail-part-2/)

* [How to Monitor Kubernetes](https://sysdig.com/blog/monitoring-kubernetes/) ，一共有 4 个篇章

* [Logging in Kubernetes with Fluentd and Elasticsearch](http://www.dasblinkenlichten.com/logging-in-kubernetes-with-fluentd-and-elasticsearch/)

* [Kubernetes Monitoring: Best Practices, Methods, and Existing Solutions](https://dzone.com/articles/kubernetes-monitoring-best-practices-methods-and-e)

### 网络相关的文章

要学习 Kubernetes，你只需要读一下，下面这个 Kubernetes 101 系列的文章。

* [Kubernetes 101 - Networking](http://www.dasblinkenlichten.com/kubernetes-101-networking/)

* [Kubernetes networking 101 - Pods](http://www.dasblinkenlichten.com/kubernetes-networking-101-pods/)

* [Kubernetes networking 101 - Services](http://www.dasblinkenlichten.com/kubernetes-networking-101-services/)

* [Kubernetes networking 101 - (Basic) External access into the cluster](http://www.dasblinkenlichten.com/kubernetes-networking-101-basic-external-access-into-the-cluster/)

* [Kubernetes Networking 101 - Ingress resources](http://www.dasblinkenlichten.com/kubernetes-networking-101-ingress-resources/)

* [Getting started with Calico on Kubernetes](http://www.dasblinkenlichten.com/getting-started-with-calico-on-kubernetes/)

### CI/CD 相关的文章

* [Automated Image Builds with Jenkins, Packer, and Kubernetes](https://cloud.google.com/architecture/automated-build-images-with-jenkins-kubernetes#kubernetes_architecture)

* [Jenkins setups for Kubernetes and Docker Workflow](http://iocanel.com/2015/09/jenkins-setups-for-kubernetes-and-docker-workflow/)

* [Lab: Build a Continuous Deployment Pipeline with Jenkins and Kubernetes](https://github.com/GoogleCloudPlatform/continuous-deployment-on-kubernetes)

### 最佳实践

* [Kubernetes Best Practices](https://medium.com/@sachin34268/kubernetes-best-practices-9b1435a4cb53) by [Sachin Arote](https://medium.com/@sachin.arote1) ，AWS 工程师总结的最佳实践。

* [Kubernetes Best Practices](https://speakerdeck.com/thesandlord/kubernetes-best-practices) by [Sandeep Dinesh](https://github.com/thesandlord) ，Google 云平台工程师总结的最佳实践。

### Docker 和 Kubernetes 资源汇总

下面是 GitHub 上和 Docker & Kubernetes 相关的 Awesome 系列。

* [Awesome Docker](https://github.com/veggiemonk/awesome-docker)。

* [Awesome Kubernetes](https://github.com/ramitsurana/awesome-kubernetes)。

虽然上面的这些系列非常全的罗列了很多资源，但是我觉得很不系统。对于系统的说明 Docker 和 Kubernetes 生态圈，我非常推荐大家看一下 [The New Stack](https://thenewstack.io/ebooks) 为 Kubernetes 出的一系列的电子书或报告。

* The New Stack eBook Series ，非常完整和详实的 Docker 和 Kubernetes 生态圈的所有东西。
  * [Book 01: The Docker Container Ecosystem](https://thenewstack.io/ebooks/docker-and-containers/the-docker-container-ecosystem/)
  * [Book 02: Applications & Microservices with Docker & Containers](https://thenewstack.io/ebooks/docker-and-containers/applications-microservices-docker-containers/)
  * [Book 03: Automation & Orchestration with Docker & Containers](https://thenewstack.io/ebooks/docker-and-containers/automation-orchestration-docker-containers/)
  * [Book 04: Network, Security & Storage with Docker & Containers](https://thenewstack.io/ebooks/docker-and-containers/networking-security-storage-docker-containers/)
  * [Book 05: Monitoring & Management with Docker & Containers](https://thenewstack.io/ebooks/docker-and-containers/monitoring-management-docker-containers/)
  * [Book 06: Use Cases for Kubernetes](https://thenewstack.io/ebooks/use-cases/use-cases-for-kubernetes/)
  * [Book 07: State of the Kubernetes Ecosystem](https://thenewstack.io/ebooks/kubernetes/state-of-kubernetes-ecosystem-second-edition-2020)
  * [Book 08: Kubernetes Deployment & Security Patterns](https://thenewstack.io/ebooks/kubernetes/kubernetes-deployment-and-security-patterns/)
  * [Book 09: CI/CD with Kubernetes](https://thenewstack.io/ebooks/kubernetes/ci-cd-with-kubernetes/)
  * [Book 10: Kubernetes solutions Directory](https://thenewstack.io/ebooks/kubernetes/kubernetes-solutions-directory/)
  * [Book 11: Guid to Cloud-Native Microservices](https://thenewstack.io/ebooks/microservices/cloud-native-microservices-2018/)

## 小结

总结一下今天的内容。Docker 和 Kubernetes 已经成为分布式架构和自动化运维方面的不可或缺的两大基本构成，是你必需要学习的。虽然它们的玩法跟传统运维不一样，但技术方面并不算复杂，只要你花上一点时间，一定会学好的。

在这篇文章中，我推荐了 Docker 和 Kubernetes 基础技术方面的学习资料，并给出了存储、运维、网络、CI/CD 等多方面的资料，同时列出了与之相关的最佳实践。相信认真学习和消化这些知识，你一定可以掌握 Docker 和 Kubernetes 两大利器。

下篇文章，我们将学习机器学习和人工智能方面的内容。敬请期待。