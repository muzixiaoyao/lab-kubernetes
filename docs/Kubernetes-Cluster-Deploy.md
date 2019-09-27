# kubernetes cluster 部署

在这一章教程中, 我们将会安装k8s的master节点, 并且添加一个工作节点(work node).  

## 部署工具kubeadm介绍

像很多开源工具一样, 部署大规模集群的时候, 一个一个节点手动部署将会浪费很多的时间, 还要面临认为的失误等问题, 所以一个好的部署工具室必不可少的, `kubeadm`是社区里一个非常热门的部署工具项目, 也是很多多节点部署k8s场景下的第一选择, 当然除了kubeadm意外还有非常适合all in one的部署工具`minikube`. 课程当中我们不会讲minikube的使用, 对此工具感兴趣的同学可以自行学习.  

## 网络组件的选择flannel/calico

在安装之前我们首先要选型, 如网络模块, 社区中提供了集中解决方案, 但是`flannel`无法做到Pod与Pod之间通信的安全隔离(Network Policies), 试想如果把k8s做成CAAS公有云(container as a service), 那么问题就来了, 两个用户的Pod之间如果能够相互访问, 就有了不安全的因素. 在本课程当中我们使用`Calico`作为网络组件, 除了Calico以外还有需要多项目支持网络安全策略比如:Romana/Cilium/Kube-route/WeaveNet等.  

## 实验-安装master节点

我们要使用`CentOS 7.x`来安装k8s的master节点, 并且它是一台虚拟机, 我们使用kvm(kernel-base virtual machine)作为虚拟机监控器(hypervisor).  

---

> 北京授课的同学需要登录远程课程环境

北京的同学, 需要在主机电脑上安装`vnc viewer`, 单击[此处](https://www.realvnc.com/en/connect/download/viewer/windows/)下载并安装vnc viewer

完成安装后双击vnc viewer来打开它, 并输入授课讲师分配给大家的IP地址然后按回车键, 注意这里的端口5901m, 根据vnc连接数量会改变, 一般都在5901/5902/5903之间变化, 如果发现5901无法连接, 请尝试其他端口号.  

![k8s_cludep_vnc01](../img/k8s_cludep_vnc01.png)

在弹出密码的位置输入trystack

![k8s_cludep_vnc02](../img/k8s_cludep_vnc02.png)

---
