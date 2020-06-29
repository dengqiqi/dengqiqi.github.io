---
title: github-pages搭建
date:  2020-06-28 22:23:04 +0800
category: Essay
tags: 开发记录
excerpt: 记录一下github pages的搭建过程。
---

# 开始搭建我的github pages



> **创建初衷**：记录学习收获，记录成长。



## 1.如何创建

很简单。首先，你需要有一个github的账号，在github上新建一个仓库名为`xxx.github.io`，xxx为你github的用户名。这样你就已经拥有了属于你的github pages，并可以通过xxx.github.io来访问你的主页了。

当然，现在你的主页上是什么内容也没有的，要想显示内容，最暴力的方法就是在你的仓库下放置一个index.html，网站会默认去加载该文件。



## 2.引入模板

对于大多数的博主来说，自己去开发一套功能齐全的博客网站还是很耗费精力的。对此我们可以先暂时搁置下自己DIY网站的冲动，不妨先选择一个风格良好，自己喜欢的模板来快速搭建自己的pages。

我选择的主题模板如下

```shell
git clone https://github.com/showzeng/Minimalism.git
```

clone了主题下来后，我们接着要把我们刚刚建好的仓库也克隆到本地。

然后将主题仓库下除了.git目录外的所有文件都复制到你自己的仓库中。

现在，你可以在你的主页地址[查看本款主题的效果][preview]了。



## 3.本地部署

有了模板之后我们就可以去改造我们的网站了。那么问题来了，我们要如何调试和预览自己修改后的效果呢？

每次修改后提交修改到github上，这样实在很不方便。所以我们需要在本地也搭建起github pages的运行环境。

部署步骤如下：

1. 安装Ruby

   > 下载地址：
   >
   > http://www.ruby-lang.org/zh_cn/downloads/

2. 安装Bundler

   ```shell
   gem install bundler
   ```

3. 安装Jekyll

   如果你也是使用的同款主题，目录下会有一个Gemfile，替换成以下内容

   ```shell
   # 默认地址
   # source 'https://rubygems.org'
   # 使用淘宝镜像
   source 'https://gems.ruby-china.com/'
   gem 'github-pages', group: :jekyll_plugins
   ```

   然后执行：

   ```shell
   bundler install
   ```

4. 运行Jekyll

   ```
   bundle exec jekyll serve
   ```

   本款主题也提供了一些构建脚本，你也可以用以下shell命令来替换上述命令

   ```shell
   ./script/server
   ```

   如果你是window用户，可以先安装git，通过git-bash来完成上述命令

5. 部署完成
   到此你的github pages就可以在本地通过以下地址在浏览器中查看了

   > localhost:4000



## 4. 如何去写博客

未完...





[preview]: https://showzeng.github.io/