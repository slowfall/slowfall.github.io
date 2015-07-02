---
layout: post
title: "使用jekyll在github上搭建博客"
description: "使用jekyll在github上搭建博客"
category: web
tags: [jekyll, github, ruby, rake, mac]
---
一直很少写博客，感觉还是要记下一些东西，所以想搭建一个自己的博客。看了一些其他人的博客，发现可以在github上搭建博客，好像很厉害的样子，于是决定试一试。

## 1.创建自动生成的页面
通过GitHub Help文档中的 [Creating Pages with the automatic generator](https://help.github.com/articles/creating-pages-with-the-automatic-generator/) 创建、生成页面；创建之后的GitHub repository结构大致是这样的：

<img src="/image/20150702121259.png"/>

现在你可以通过username.github.io （username是你在github上的用户名）访问刚刚生成的页面了。

## 2.将页面的主题修改为jekyll-bootstrap
让我们来换一个主题，先clone自己页面的repository，删除其中的文件；再clone jekyll-bootstrap，将其中的文件全部拷贝到自己的repository中即可（username是你在github上的用户名）：
{% highlight bash %}
git clone https://github.com/username/username.github.io
cd username.github.io
rm -rf *
cd ..
git clone https://github.com/plusjade/jekyll-bootstrap
cd jekyll-bootstrap
cp -rf * ../username.github.io
cd ../username.github.io
git add -A
git commit -m "change theme to jekyll-bootstrap"
git push
{% endhighlight %}

然后等待10分钟左右再访问username.github.io，就可以看到效果了：

<img src="/image/20150702125929.png"/>

## 3.安装jekyll，建立本地预览
现在访问你自己的github网址就可以看到页面是什么样子了，不过我们也不会每次修改了页面就提交到github上面看是什么样子吧，所以安装jekyll本地预览效果。

###3.1安装ruby
如果不想折腾，使用[Windows下安装Ruby on Rails最简单的方法](http://rubyer.me/blog/1509/)安装ruby和devkit等，一条龙服务。

如果想折腾，先下载ruby和DevKit，[下载地址](http://rubyinstaller.org/downloads/) （注意两者对应的版本）。
安装ruby，并为ruby安装目录下bin设置环境变量（PATH）；然后安装DevKit，参考[windows下安装DevKit](http://rubyer.me/blog/134/)。

###3.2安装jekyll
如果没有安装DevKit，直接安装jekyll会出错；

	gem update -install (更新gem)
	gem install jekyll 

###3.3预览
安装成功之后，进入页面repository目录，使用jekyll预览：

	cd username.github.io
	jekyll s

然后访问 http://localhost:4000 就可以看到效果了。

##4.markdown编辑器
windows环境可以使用[MarkdownPad](http://markdownpad.com/)编辑预览。


{% include JB/setup %}
