---
layout: post
title: Jekyll + Gitpage 踩坑记录
subtitle: Gitpage搭建个人网页
author: Lethe
categories: jekyll
banner:
  #video: https://vjs.zencdn.net/v/oceans.mp4
  loop: true
  #volume: 0.8
  #start_at: 8.5
  image: /img/post-Page-bg.jpg
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold "
  subheading_style: "color: gold"
tags: jekyll theme yat Gitpage
sidebar: []
---

## STEP 1 建立Github仓库

* 自己建立仓库

  首先在[Github](http://github.com)上建立自己的仓库。
  其中，仓库名有固定的格式：*username.github.io* 如果想要以username.github.io作为网站的名称，就要用github账户的用户名作为username。
  比如， 我的账户名是*ABC*，那我创建的仓库名就是*ABC.github.io*
  如果使用其他名字(如CDE)来创建的话，就是子站点的名称，那你的网站名就会是 *ABC.github.io/CDE*

* Fork 别人的模板
  与上述内容相似，注意username的选择。

## STEP 2 开启Github Pages

  进入仓库的Setting界面，在左侧栏找到 *Pages* ，在 *Build and deployment* 下找到 *Branch* 并选择 **master** 和 **/(root)**

  这个操作可以让你以目前仓库master分支下的代码部署Page，如果想以别的分支的代码来建立就将 **master** 切换为指定分支

## STEP 3 Jekyll快速指南
  Jekyll的目录结构如下：
  * _layouts : 存放页面的模板，在.md和.html等文件中可以引用模板
  * _sass : 存放样式表
  * _ posts : 存放博客文章，以.md文件为主
  * _includes : 存放可复用的html文件
  * assets : 存放原生的资源文件，例如js, css, image(博客中引用的图片可以放在这里) 
  * _config.yaml : 全局配置文件
  * 其他自定义目录和文件

  详细目录结构请参考Jekyll官网[Jekyll](https://jekyllrb.com/docs/structure)

## STEP 4 拉取仓库代码到本地
  * 安装Gitbash
  * 新建文件夹，并使用Gitbash将Github仓库中的文件拉取到本地
  * win+R 打开cmd界面，cd 进入到刚才新建的文件夹里

## STEP 5 本地配置Jekyll环境
  * 安装 Ruby
    在计算机上安装Ruby，进入官网[Ruby](https://www.ruby-lang.org/zh_cn/)下载并安装

  * 安装 RubyGems
    RubyGems是Ruby的包管理器，用于安装和管理Ruby库和应用程序。一般情况下，RubyGems和Ruby会一起安装。
