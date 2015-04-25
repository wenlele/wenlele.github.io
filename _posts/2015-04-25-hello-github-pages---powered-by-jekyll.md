---
layout: post
title: "Hello Github Pages, powered by Jekyll"
description: "Hello world page"
category: shared
tags: [experience]
---
{% include JB/setup %}

## 关于Github Pages

	“Websites for you and your projects” - https://pages.github.com/
	
从官方的定位看，GitHub Pages是让用户搭建个人及项目主页的解决方案。这个解决方案特别通用，GitHub Pages只是把请求重定向到用户提供静态网页内容，所有很多人将其作为搭建个人博客的一种选择。


## 基于[Jekyll/bootstarp](http://jekyllbootstrap.com/usage/jekyll-quick-start.html)快速搭建Github pages

基本按下面两篇分享做的（其实两篇差不多），自己之前没怎么用过github, ruby/python皆小白，最后花了半个晚上搞定。

	http://www.mceiba.com/develop/jekyll-introduction.html
	http://blog.fens.me/jekyll-bootstarp-github/

### 搭建过程的一些问题和解决方法

- **安装Ruby DevKit**
	官网上并没有说明如何在windows下安装，作为ruby小白很无助。感觉无私的网友以及搜索引擎，我找到了安装的方法 http://rubyer.me/blog/134/。

- **安装Python setuptools**
	参考的分享文章没讲得这么具体，而官网的写的在powershell command（如下）需要先把python的安装路径加入环境变量的path里，
	
		(Invoke-WebRequest https://bootstrap.pypa.io/ez_setup.py).Content | python -

	或者在python的安装目录下运行
	
		(Invoke-WebRequest https://bootstrap.pypa.io/ez_setup.py).Content | .\python.exe -

- **gem install Jekyll或其他gem**
	用`gem install`，有时会遇到一下错误：

		ERROR:  While executing gem ... (Gem::RemoteFetcher::FetchError)
		Errno::ECONNRESET: An existing connection was forcibly closed by the remote host. - SSL_connect (https://api.rubygems.org/gems/awesome_print-1.6.1.gem)

	发现在console里，default的gem source "https://rubygems.org/" ping不通。但在浏览器上可以。有些gem可以在rubygems.org里下到本地用gem install安装，但有些如Jekyll依赖其他一些gem就无法方便地下到本地安装。
	继续求助搜索引擎，有篇文章说rubygems.org在国内不稳定（你懂的），但可以用一个镜像（http://ruby.taobao.org/
）替代用原来的gem source。的确靠谱。

		c:\Ruby22-x64>gem sources --remove https://rubygems.org/
		https://rubygems.org/ removed from sources
		c:\Ruby22-x64>gem sources -a https://ruby.taobao.org/
		https://ruby.taobao.org/ added to sources

	其实个人觉得是gem在console的config问题导致的，毕竟rubygems.org在浏览器上可用且有些gem能直接install。但自己懒得深究，便不往下研究了。
	同样遇到这个问题且有兴趣去深入研究的可以看 https://github.com/rubygems/rubygems/issues/515。

	
### 其他人用Jekyll搭建的网站

可以参考
	
	https://github.com/jekyll/jekyll/wiki/Sites

	
	
## 一些感受
很早以前便想搭建一个个人博客，这次算是了结过去一个目标。不过如果拿Github Pages做频繁发布内容的个人博客，个人觉得还是麻烦了些。它更适合做个人、项目主页。
目前也没有进一步发布更多内容的动力，也许以后会拿它改成个人主页，或者同时分享一些特别技术类的个人文章。