# k8s介绍

## Kubernetes的介绍

最早在google内部运行了很长时间，最终google将borg贡献到开源社区由cncf(Cloud Native Computing Foundation)来托管，并改名为Kubernetes，Kubernetes在希腊语中是领航员(κνβερνητης)的意思,您可以从[cncf的官方网站](https://www.cncf.io/)的毕业项目(graduated project)下找到Kubernetes。

Kubernetes 主要对于容器进行编排(orchestration)，随着Kubernetes的发展，还可以编排容器以外的轻量级的qemu虚拟机(Hyper Container)，类似于OpenStack中的Kata Container。

使用Kubernetes可以避免我们直接对container进行操作，概念就像IAAS平台中，屏蔽了我们直接对底层的虚拟机进行操作一样，只是IAAS平台编排的是虚拟机，Kubernetes编排的是container或者轻量级的qemu虚拟机，它提供了统一的持久化和非持久化的存储接口，并可以集成各种文件系统来为Pod提供存储，还提供了安全管理机制和资源管理机制等。

在国内我们称Kubernetes叫做k8s，但在国外叫做kate`s。

请在开始课程前记住一句话: It`s all about orchestration/都是编排。

## Kubernetes的生态、开源社区

**在这个章节里，我们将介绍k8s的生态，比如谁在用k8s，用的怎么样，还有我们将介绍一下开源社区和一些周边的资源和组织，最后我们将介绍一下k8s和IAAS集成的项目。**

### 生态

首先看下哪些大公司正在使用k8s，这些企业多多少少做了一些定制，所以我们除了可以说是一种解决方案也可以说是k8s的一个分支(DISTRIBUTIONS)，概念有点像Linux操作系统。

- Alibaba Cloud Container Service  

    阿里巴巴的Alibaba Cloud Container Service，提供了用户在阿里云上运行容器的功能，很好的支持k8s作为容器的编排工具。

- Amazon Elastic Container Service for k8s (ESK)  

    AWS的容器服务ESK，用户可以在aws云服务上快速运行k8s并且不需要安装任何组件，你的容器会被AWS的k8s集群来编排，当前ESK还是预览版(Preview)，当然也可以选择成熟ECS(Amazon Elastic Container Service)

- Azure Container Service/ AKS  

    微软的CAAS服务，在微软的Azure Platform上部署容器并编排。

- Google Kubernetes Engine  

    在Google Cloud Platform上运行容器，您可以通过管理经google强化过的k8s来编排你的容器。

- Openshift Origin  

    红帽社区版的k8s项目，底层封装了k8s，提升了用户使用体验等等。

- Red Hat OpenShift Online  

    红帽的公有云容器服务，你可以通过管理经红帽强化过的OpenShift来编排你的容器。

- Red Hat OpenShift Dedicated  

    在公有云上部署OpenShift大规模集群，比如在AWS和GCP上。

- Tectonic (CoreOS)  

    企业级的k8s产品，利用coreos操作系统在企业内部署基于容器编排的私有云的产品，它使用的是100% k8s社区源码。

### 社区

- 团体 -- 所有开源项目的活跃程度很大部分取决于它在社区的活跃度，首先k8s社区每个月都会有很多会议和活动，您可以查看社区的[会议日程](https://kubernetes.io/community/),社区里还有很多兴趣小组Special Interest Groups(SIGS)，除了兴趣小组以外，还有工作组Working Groups，您可以从这里看到[组员和他们来自于什么公司](https://github.com/kubernetes/community/blob/master/sig-list.md)

- 源码 -- 如果同学想要接触k8s源码，你可以从GitHub上获取，当然如果你想要能运行的话，需要有[go语言的环境](https://github.com/kubernetes)

- 开发--开发分为多种

- API调用开发 -- k8s是基于API的开发模式，所有请求通过授权以后都可以访问k8s资源，所以你想要做外接程序去读取k8s的数据，需要先学习API调用开发。

- k8s组件开发 -- 通过完善或者新增k8s的组件，如api server等来为k8s做贡献，开始前你需要会go语言。

- 微服务开发 -- 在底层运行的容器中开发你自己的应用。

- 幸运的是，不管以上哪种开发，你都可以从GitHub上学习到[如何开始](https://github.com/kubernetes/community/tree/master/contributors/devel)

### 周边资源

- [K8s官方网站](https://kubernetes.io/) -- [https://kubernetes.io/](https://kubernetes.io/)
- [Devstate](https://k8s.devstats.cncf.io/d/12/dashboards?refresh=15m&orgId=1) -- 统计k8s项目在GitHub上的活跃度
- [KubeCon](https://events.linuxfoundation.cn/events/kubecon-cloudnativecon-china-2018/) -- cncf下的一个组织，专门组织专业机构参加cncf会议，开会讨论新方向等。
- [Stack overflow](https://stackoverflow.com) -- 一个提关于k8s问题的网站。
- [The New Stack](https://thenewstack.io) -- 专门做云计算新闻的网站，大家可以在这里看到各种云项目的动态和电子书。
- [Slack](https://slack.com) – 一个非常有意思的在线问题的平台。

## Kubernetes之外的选择

### Docker swam

Docker swam是Docker默认自带的容器编排工具。[Docker swam文档](https://docs.Docker.com/engine/swarm/)

