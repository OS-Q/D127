---
title: "如何把 Openwrt 软路由刷入 N1 真香盒子中"
subtitle: ""
date: 2020-07-27T17:37:31+08:00
lastmod: 2020-07-27T17:37:31+08:00
draft: false
author: ""
authorLink: ""
description: ""

tags: [N1,openwrt]
categories: [Linux]

hiddenFromHomePage: false
hiddenFromSearch: false

featuredImage: ""
featuredImagePreview: ""

toc:
  enable: true
math:
  enable: false
lightgallery: false
license: ""
---

<!--more-->

## 购买途径

拼多多上有白色版本、黑色版本（最便宜）、米色版本，有拆封刷机的，也要号称原装未拆封的（基本不存在的）。不用纠结拆没拆封，买所谓的全新的就是了。

## 刷机

### 降级

将购入的 N1 盒子插上 HDMI 线，接电视机或显示器，可以看到当前系统的版本，如果版本号高于 2.19 则需要先降级再刷机。

参考大佬的方式，很简单大佬讲的很清楚，地址：https://www.right.com.cn/FORUM/thread-340279-1-1.html 

在降级之前建议先安装 USB_Burning_Tool 这个工具，别人推荐的。

降级步骤：

1. N1 盒子连接网络，无线或者有线均可，需要保证和降级需要的电脑在同一局域网
2. N1 盒子连接显示器，记录下来 N1 盒子的 ip
3. 鼠标连续点击 N1 盒子版本号位置4下，打开盒子的 adb 服务
4. 打开降级工具，按提示操作即可。注意的是选择降级回车确认后，需要等待一会才能看到成功提示
5. 降级完毕后，关闭降级工具窗口，显示器看到版本号没有改变，实际上已经降级成功

### 刷入openwrt 

选择 flippy 大佬的版本，地址：https://www.right.com.cn/forum/thread-981406-1-1.html

1. 首先将固件下载解压，用 U 盘镜像文件写入工具（推荐使用 [rufus](https://rufus.ie/) ），把img文件写入 U 盘
2. 公对公USB线连接电脑N1
3. 然后将 U 盘插入 N1 盒子靠近 HDMI 的 USB 接口，使用官方系统降级工具选项 3 可以进入 U 盘启动
4. 成功 U 盘启动后，即进入了 openwrt 系统，如果仅想在 U 盘中体验使用，此时就可以登陆 openwrt 页面管理使用了
5. 可选步骤。可以将 openwrt 系统刷入 N1 盒子的内置存储 emmc 中，具体命令请查看 flippy 的帖子

### 切换系统

#### openwrt -> 原版

参考 https://www.right.com.cn/forum/thread-413863-1-1.html ：

1. 先把 USB 对公线链接到电脑 USB 口与 N1 的第二个口（靠 HDMI 口），N1 不要通电
2. 打开 USB_Burning_Tool，导入固件 webpad 的 2.2 线刷包，验证通过后，出现开始字样
3. 勾选擦除 FLASH，不要勾选擦除 bootloader，USB_Burning_Tool 点击开始运行刷机，3 秒钟内速度让 N1 通电
4. USB_Burning_Tool 开始正常识别 N1 线刷模式，刷机开始
5. 烧录完成后，拔电重启，N1 恢复了原来的样子，可以正常 adb 连接，进入线刷，重新刷其他系统