# 其他相关内容

## Catalog

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

- [其他相关内容](#%e5%85%b6%e4%bb%96%e7%9b%b8%e5%85%b3%e5%86%85%e5%ae%b9)
  - [Catalog](#catalog)
  - [Helm](#helm)
  - [Custom Resource](#custom-resource)

<!-- /code_chunk_output -->

## Helm

有点像 apt 和 yum，只不过 helm 在 k8s 中部署应用，限于国家防火墙，Helm 在国内如果不翻墙的话，使用会非常不顺，我们可以查看这里来了解更多关于 Helm 的信息：[https://github.com/kubernetes/helm](https://github.com/kubernetes/helm) 。

## Custom Resource

简称 CR，我们用 kubectl 命令看到的数据库都是存在 etcd 数据库当中的，但是他们这些字段的定义都是预先设定好的，比如 Pod、namespace 等，除了这些内置的数据模型以外，用户完全可以通过 CR 来定义自己的数据模型，然后往里面写入数据并自动存入到 etcd 中，同学们可以访问这里来了解更多关于 CR 的信息：[https://kubernetes.io/docs/concepts/api-extension/custom-resources/](https://github.com/kubernetes/helm) 。
