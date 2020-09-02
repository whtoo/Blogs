---
title: VScode下的Go插件配置
date: 2020-09-01 15:50:33
tags:
---
## 1. 必要资源说明

|插件地址|插件名称|
|---|---|
|github.com/mdempsky/gocode     |     gocode|
|github.com/uudashr/gopkgs/cmd/gopkgs    |gopkgs|
|github.com/ramya-rao-a/go-outline      |go-outline|
|github.com/acroca/go-symbols          |go-symbols|
|golang.org/x/tools/cmd/guru          |guru|
|golang.org/x/tools/cmd/gorename      |gorename|
|github.com/derekparker/delve/cmd/dlv |      dlv|
|github.com/stamblerre/gocode  |        gocode-gomod|
|github.com/rogpeppe/godef    |    godef|
|github.com/ianthehat/godef  |        godef-gomod|
|github.com/sqs/goreturns   |goreturns|
|golang.org/x/lint/golint   |       golint|

## 2. ~~脚本自动化实现~~

1. ~~__思路说明__~~

    - ~~首先，我们将插件和他们的安装包名建立一个map。~~

    - ~~其次，我们对这个map做一个遍历。~~

    - ~~将买一个`MapEntry<path,pluginName>的key`（即path）做`split`操作，然后根据分片后的数组建立目录结构。~~

    - ~~在每一个路径分片数组的末尾执行`git clone`操作~~

    - ~~接着，在成功后进行跳回顶层目录（`$(GOPATH)`)。~~

    - ~~此时，执行`go install pluginName`~~

    - ~~重复上面的过程直到遍历完毕，跟着再次跳回顶层目录（`$(GOPATH)`)。~~

2. ~~__实现脚本__(`Python3`)~~
    
    ~~{% include_code lang:python install_plugin.py %}~~

## 3. 代理实现（`正解`）下文引自[`格物`](https://shockerli.net/post/go-get-golang-org-x-solution/#goproxy-%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F)

### __`GOPROXY 环境变量`__

终于到了本文的终极大杀器 —— `GOPROXY。`

我们知道从 `Go 1.11` 版本开始，官方支持了 `go module` 包依赖管理工具。

其实还新增了 `GOPROXY 环境变量`。如果设置了该变量，下载源代码时将会通过这个环境变量设置的代理地址，而不再是以前的直接从代码库下载。这无疑对我等无法科学上网的开发良民来说是最大的福音。

更可喜的是，`goproxy.io` 这个开源项目帮我们实现好了我们想要的。该项目允许开发者一键构建自己的 `GOPROXY` 代理服务。同时，也提供了公用的[代理服务] (https://goproxy.io)，我们只需设置该环境变量即可正常下载被墙的源码包了：

`export GOPROXY=https://goproxy.io`

不过，需要依赖于 `go module` 功能。可通过 `export GO111MODULE=on` 开启 MODULE。

如果项目不在 `GOPATH` 中，则无法使用 `go get ...`，但可以使用 `go mod ... `相关命令。

也可以通过置空这个环境变量来关闭，`export GOPROXY=`。

对于 `Windows` 用户，可以在 `PowerShell` 中设置：

`$env:GOPROXY = "https://goproxy.io"`

最后，我们当然推荐使用 `GOPROXY` 这个环境变量的解决方式，前提是 `Go version >= 1.11`。

最后的最后，七牛也出了个国内代理 goproxy.cn 方便国内用户更快的访问不能访问的包，真是良心。

### 参考资料
+ [goproxy.io for Go modules](https://mp.weixin.qq.com/s/COethtOaiygsYev-kkCc4A)
+ [goproxy.io](https://goproxy.io/)
+ [goproxy.cn](https://goproxy.cn)
+ [格物](https://shockerli.net/post/go-get-golang-org-x-solution/#goproxy-%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F)
