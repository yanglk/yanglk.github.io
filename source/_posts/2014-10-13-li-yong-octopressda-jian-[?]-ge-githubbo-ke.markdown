---
layout: post
title: "利用Octopress搭建一个Github博客"
date: 2014-10-13 11:00:34 +0800
comments: true
categories: 
---

#利用Octopress搭建一个Github博客
![image](http://beyondvincent.com/images/2013/08/github_page_and-octopress.png)

##小引
`Octopress`是利用`Jekyll`博客引擎开发的一个博客系统，生成的静态页面能够很好的在github page上展现。号称是hacker专属的一个博客系统(`A blogging framework for hackers.`)

根据大家的反应，本文我就来介绍一下如何在苹果电脑(OS X 10.8.3)利用Octopress搭建一个Github博客。本文需要读者熟悉一些shell命令，并掌握基本的git操作。

##目录
* 1、安装Ruby
* 2、安装Octopress
* 3、配置Octopress
* 4、将博客部署到GitHub上
* 5、开始写博客
* 6、更多操作
* 7、小结

###1、安装ruby
Octopress需要Ruby环境，RVM(Ruby Version Manager)负责安装和管理Ruby的环境。所以我们先在终端输入如下命令，来安装RVM：
```
curl -L https://get.rvm.io | bash -s stable --ruby
```
接着是安装Ruby 1.9.3，在终端依次运行如下命令：
```
rvm install 1.9.3
rvm use 1.9.3
rvm rubygems latest
```
完成上面的操作之后，运行`ruby --version`应该可以看到ruby 1.9.3环境已经安装好了。
参考：[Installing Ruby With RVM](http://octopress.org/docs/setup/rvm/)

###2、安装Octopress
在安装Octopress之前，请确保你的电脑上已经安装有git了，在终端输入`git --version`，应该可以看到电脑中的git版本(我电脑上输出:`git version 1.7.12.4 (Apple Git-37`))，如果没有显示相关内容，请先安装git。
git安装之后，利用git命令将octopress从github上clone到本机，如下命令：
```
git clone git://github.com/imathis/octopress.git octopress
cd octopress    # If you use RVM, You'll be asked if you trust the .rvmrc file (say yes).
ruby --version  # Should report Ruby 1.9.3
```
接着安装相关依赖项：
```
gem install bundler
rbenv rehash    # If you use rbenv, rehash to be able to run the bundle command
bundle install
```
最后安装默认的Octopress 主题。
```
rake install
```