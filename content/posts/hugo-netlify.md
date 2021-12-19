---
title: " 测试博客系统"
date: 2021-11-12T14:49:17+08:00
description: "主要包括使用图标呈现"
draft: false
tags: [Qitas,GithubPages,Even]
categories: [blog]
toc:
  enable: true
  auto: false
code:
  copy: true
math:
  enable: true
mapbox:
  accessToken: ""
share:
  enable: true
comment:
  enable: true
---

<!--more-->
>**本文同步更新至 [Youtube ](https://youtu.be/ZAi4a1fyBWI) 和 [BiliBili ](https://www.bilibili.com/video/av84216011/)**


<h3 id="test">测试图片</h3>
<p>图片为阅读数据类容。</p>
<p><img
        class="lazyload"
        src="/svg/loading.min.svg"
        data-src="images/B92.jpg"
        data-sizes="auto"
        alt="images/B92.jpg"
        title="阅读内容" /></p>


## 部署到Github Pages

请参照 [用 Hugo 配合 GithubActions 自动构建我的博客]({{< ref "Hugo-Github-Actions.md" >}})

## 设置Even主题子模块化

在网站根目录下输入添加主题子模块的命令：

```
git submodule add https://github.com/zhaoqiangcn/hugo-theme-even.git themes/even
```

如果在网站根目录下出现 *.gitmodules* 文件，且内容跟我的类似，则表示成功：

```
[submodule "themes/even"]
	path = themes/even
	url = https://github.com/zhaoqiangcn/hugo-theme-even.git
```

然后 进入主题文件夹 *git push* 到远程仓库即可。

## 部署


跟官网宣传的一样，部署 Hugo 网站到 Netlify 非常简单，跟着导航操作即可。

经过部署后已经可以通过 Netlify 分配的域名来访问网站了

## 自定义域名

对于想对网站使用**主域名**而言，自定义域名很简单：

1. 找到 *Domain settings* 选项卡，点击进入域名设置
2. 在 *Custom domains* 一项下点击 *Add domain alias* 来添加自定义域名
3. 在弹出来的输入框输出主域名即可
4. 在域名商处添加如下的 DNS 记录，等待 DNS 刷新，看到主域名处出现 *NETLIFY DNS* 的墨绿色标志即代表成功

```
dns1.p01.nsone.net
dns2.p01.nsone.net
dns3.p01.nsone.net
dns4.p01.nsone.net
```

## 开启 HTTPS

在 *HTTPS* 选项卡下的 *SSL/TLS certificate* 选项开启即可。

