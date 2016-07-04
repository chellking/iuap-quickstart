# iUAP Design 快速开发（中文版）

v 0.01

{{file.mtime}}    <!-- toc -->

开发平台提供完整的开发工具，帮助业务开发人员快速搭建开发环境，熟悉iUAP平台的开发方式，简单快速的进入软件开发与使用各iUAP企业应用的组件库。开发基于Maven推荐标准工程管理，可以很容易的实现前后端开发分离及自动化构建；

本文档旨在介绍如何利用平台提供的DevTool工具包，快速的熟悉开发过程。具体的前端开发和后端技术组件的使用，请参看[iUAP官网](http://iuap.yonyou.com)的其它帮助文档和手册。

该项目用于编写开发向导的工作，并确保项目的可持续性，特别做如下规划：

* 所有编写工作转到 [Github](https://www.github.com) 来协同，可以通过 Github Pull Request 来完成评审。
* 所有翻译结果用 [GitBook](http://www.gitbook.com) 来展示，并方便转换为如下格式（pdf, mobi, epub, html 等）。
* 所有编写后的文档格式统一为 GitBook 支持的 [Markdown 格式](http://help.gitbook.com/format/markdown.html)。
* 在翻译新文章时，请先把英文原文转为 Markdown 格式并存到 `en/` 下，之后再翻译为中文存到 `zh-cn/`。
* 目录结构尽量遵循 `Documentation/` 的原有方式。

## 简介

-   代码仓库：<https://github.com/chellking/iuap-quickstart>
-   在线阅读：<https://www.gitbook.com/book/chellking/iuap/details>
-   项目首页：<http://iuap.yonyou.com>

## 参与翻译

请参考[译者须知](doc/README.md)。

### 安装

以 Ubuntu 为例：

    $ sudo aptitude install -y retext git nodejs npm
    $ sudo ln -fs /usr/bin/nodejs /usr/bin/node
    $ sudo aptitude install -y calibre fonts-arphic-gbsn00lp
    $ sudo npm install gitbook-cli -g

### 下载

    $ git clone https://git.gitbook.com/chellking/iuap.git
    $ cd iuap/

### 编译

    $ gitbook build  // 编译成网页
    $ gitbook pdf    // 编译成 pdf

### 纠错

欢迎大家指出不足，如有任何疑问，请邮件联系 chexz@yonyou.com (at yonyou dot com) 或者直接修复并提交 Pull Request。

### 版权

本书采用 GPL v2 协议发布。

### 关注我们

-   [新浪微博](http://weibo.com/tinylaborg)

   [<img src="pic/tinylab-sina.jpg" width="150"/>](http://weibo.com/tinylaborg)

-   微信公众号

   <img src="pic/tinylab-weixin.jpg" width="150"/>


### 贡献者
<hr> 
