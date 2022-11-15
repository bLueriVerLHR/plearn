> 各类工具知识

# 常用的工具网站

- 推荐的搜索引擎
  - [谷歌](https://www.google.com)
  - [必应](https://www.bing.com)
- 推荐的学习网站
  - [维基百科](https://www.wikipedia.org/)
  - [Arch wiki](https://wiki.archlinux.org/)
  - [Ubuntu wiki](https://wiki.ubuntu.com/)
  - [Stack Overflow](https://stackoverflow.com/)
  - [B 站](https://www.bilibili.com/)
  - [知乎](https://www.zhihu.com/)
- 慎重参考的网站
  - [百度](https://www.baidu.com/)
  - [CSDN](https://www.csdn.net/)
  - [博客园](https://www.cnblogs.com/)
  - [简书](https://www.jianshu.com/)
  - [掘金](https://juejin.cn/)

# 搜索技巧

## Google

谷歌高级搜索网址：<https://www.google.com/advanced_search>

对于谷歌搜索引擎，可以参阅如下文档：

<https://www.wtmdigital.com/wp-content/uploads/2014/10/google-advanced-search-operators.pdf>

<https://static.semrush.com/blog/uploads/files/39/12/39121580a18160d3587274faed6323e2.pdf>

<https://ahrefs.com/blog/google-advanced-search-operators/>

注意，其他网站都会向 `google` 进行学习，所以搜索方法会很类似。

## GitHub

查阅如下网站：

<https://docs.github.com/en/search-github/getting-started-with-searching-on-github/about-searching-on-github>

<https://docs.github.com/en/search-github/getting-started-with-searching-on-github/understanding-the-search-syntax>

## 其余

大多数都有总结在这里：

<https://github.com/cipher387/Advanced-search-operators-list>

# 基础知识

## 计算机网络

咱们既然叫做网络部，那么首先要弄清楚的肯定首先是网络，鉴于时间肯定是有限的，那么肯定是优先掌握关键部分：

- OSI网络分层/五层网络架构
  - 简述：OSI分层将整个网络分成七层，但实际情况根本没人用（笑），五层网络架构是408的考点，比较实际。
  - 要求：大致了解和分辨多个层
- http协议（应用层协议）
  - 简述：对于该协议深入了解能解决很多基本问题，重点要理解 **为什么http是无状态的**
  - 深入了解协议格式和请求方式
- DNS协议（了解域名）
  - 简述：通常在我们访问一个网站的时候，我们输入的是一个域名而非ip地址，而将域名转化为ip地址，正是DNS协议所完成的。如果你对DNS协议有充分的了解，那么你便能对GFW的主要手段之一——DNS污染形成自己的理解。
  - 要求：深入了解多级域名，DNS服务器的递归查询。
- *IP协议（网络层协议）
  - 简述:在我们不深入底层的情况下，ip近似于我们在网络上的唯一标识符，至少在同一个网段内，两个不同的主机不会拥有相同的ip地址，对于不同的ip往往有不同的含义（比如192.168.x.x会是一种常见的私有地址）。
  - 要求：了解公有地址，私有地址，广播地址的格式，了解ipv4和ipv6的差别，对子网掩码和CIDR子网划分有大致了解。
  - > 对有限ip地址数量如何满足世界需求有困惑的可以了解NAT（网络地址转换）
- *端口号
- *DHCP协议（了解ip的分配过程）
  - 简述：ip地址并不是凭空而来的，在你接入网络后，你的路由器（网关）会将你的主机（这通常是MAC地址）和某个ip绑定。类比你平时上网的过程，当你使用wifi连接校园网时，连接成功后，你的主机其实便已经成功获得了某个内网ip。
  - 要求：对接入网络的整个过程有一个大致的了解。

## 计算机组成原理&操作系统
这两门的内容十分相关且较多重合，故放在一起讲。

## 数据结构
这一块的内容对于我们网络部来说反而不是那么重要，但考试可是重点。

## 编程语言
很多新手在入门阶段一开始接触的就是语言的学习，如何快速入门，降低学习坡度，这也是一门学问。对于入门，还是建议新人看视频，当熟练到一定境界后，直接看文档就会快很多。
以下为语言介绍

- Python
  - 简述：python是一门易入门，好上手的语言，但其速度因为要通过python解释器，所以比c这一类语言的速度相对较慢。又因为python它本身是一种弱语言（写码一时爽，debug火葬场），其CPython解释器又有全局线程锁（做不到真正的并发执行），所以大家一般不喜欢用它写大型合作项目。虽然如此，python做到了代码风格的清晰和简洁，所以现在也被广泛应用（比如机器学习）
  - 相关教程
  - 新手入门建议直接看B站
  - 官方教程[https://docs.python.org/3/tutorial]
  - 要求：
  - 掌握Python数据类型（如list和tuple）
  - 基本语句（if,for,open)
  - 基本环境搭建和调包（人总不能连别人的作业都不会抄）

- JavaScript/Nodejs
  - 新手入门的时候常常会误认为js是java的一种，其实这两个语言可差太多了,这里抄一段wiki的解释。<blockquote>ECMAScript是由网景的布兰登·艾克开发的一种脚本语言的标准化规范；最初命名为Mocha，后来改名为LiveScript，最后重命名为JavaScript。1995年12月，升阳与网景联合发表了JavaScript。1996年11月，网景公司将JavaScript提交给欧洲计算机制造商协会进行标准化。</blockquote>由此可见，es或许是更规范的称呼。一开始，js主要用于简单地控制浏览器，但后来由于种种原因（或许是前端觉得，js这么好，为啥我不能用这玩意写后端！），大家也希望服务端也可以跑js代码。于是nodejs就出现了。

- Go
  - 查阅如下资料：<https://golang-china.github.io/gopl-zh/>

- Rust
  - 查阅如下资料：<https://kaisery.github.io/trpl-zh-cn/>

- Java
  - 资料很多不一一列举

- C/CPP
  - 用于网络开发比较难学，看自己能力。

# 可以学习的技术

前端

- JQuery
- BootStrap
- Vue
- React

后端

- MVC/MVVM
- Linux 基础
- Flask (Python Backend Framework)
- Express (Nodejs Backend Framework)
- Nginx