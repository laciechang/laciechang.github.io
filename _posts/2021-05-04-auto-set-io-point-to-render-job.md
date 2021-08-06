---
title: 【达芬奇jio本系列】自动设定IO点添加渲染任务
author: 张来吃
date: 2021-05-30 00:35:00 +0800
categories: [达芬奇jio本系列]
tags: [python, 达芬奇]
math: true
mermaid: true
# image:
#   src: https://cdn.jsdelivr.net/gh/cotes2020/chirpy-images/commons/devices-mockup.png
---

*阅读以下内容之前请先确认*

*您已经了解本文所述的工作流程可能给您带来的影响*

# “我们又遇到一个新的问题”

达芬奇中 individual clip 的渲染方式虽然可以满足绝大多数交付要求，但总是会遇到一些 `特殊情况`，例如需要满足诸如

`渲染逐个镜头 带上例如变速、合成等效果`

这样的交付方式。过去可能需要将他们例如挨个做好复合片段，才可以使用 individual clip 模式添加渲染任务；要么就只能一个个手动设定IO点。

通常情况下确实并不建议这类方法来交付，暂且不说这一需求本身的合理性，这样的方式作为某种交付方法可能还会给大家带来某些不必要的麻烦。

但考虑到总有*不得已*的情况，因此我就写了这么一个工具来帮助大家。

![202105302302112021-05-30-23-02-12](https://raw.githubusercontent.com/laciechang/img/master/spotlight_img/202105302302112021-05-30-23-02-12.png)

# “那我要怎么用呢”



工具干的事其实很简单，即【代替人工，把特定镜头逐一设定IO点，并添加渲染任务】



要使用这个工具的前提是：

有一个统一的基于`single clip`模式的渲染设定，并存为渲染预设

为所需的片段设定某种片段颜色，告诉工具，哪些片段需要按照这一方法进行输出



在做好以上准备后，就可以打开工具开始一键添加渲染任务了



界面中提供的选项很简单



- 渲染目的文件夹

![图片2021-05-30-23-03-54](https://raw.githubusercontent.com/laciechang/img/master/spotlight_img/%E5%9B%BE%E7%89%872021-05-30-23-03-54.png)

- 指定的片段颜色

![图片2021-05-30-23-04-08](https://raw.githubusercontent.com/laciechang/img/master/spotlight_img/%E5%9B%BE%E7%89%872021-05-30-23-04-08.png)

- 指定用到的渲染预设

![图片2021-05-30-23-04-16](https://raw.githubusercontent.com/laciechang/img/master/spotlight_img/%E5%9B%BE%E7%89%872021-05-30-23-04-16.png)

- 指定特定的轨道

![图片2021-05-30-23-04-27](https://raw.githubusercontent.com/laciechang/img/master/spotlight_img/%E5%9B%BE%E7%89%872021-05-30-23-04-27.png)

考虑到片段颜色还有别的很多用途，因此请确保当前是以某个特定轨道上的特定颜色的片段作为判断基础；不是这个轨道的片段就会忽略

一个进阶的玩法是，将任意素材放到V1轨上，并根据IO点需求设定好片段的位置和指定的颜色，将V1轨道隐藏（隐藏后即可识别，同时也不会渲染到画面里）之后，即可批量添加

![图片2021-05-30-23-05-40](https://raw.githubusercontent.com/laciechang/img/master/spotlight_img/%E5%9B%BE%E7%89%872021-05-30-23-05-40.png)

最后点击 `Run` 就可以开始渲染了



# “所以哪里可以买到呢”



[点击此处前往Github页面下载吧](https://github.com/laciechang/resolve_batch_io_point)

如果你乐于💰支持我们一杯咖啡☕️

请访问我的🍞[面包多页面](https://mianbaoduo.com/o/bread/YZiWk59r)🍞，还可获得【达芬奇开发交流群】入口一枚

![图片2021-05-30-23-03-42](https://raw.githubusercontent.com/laciechang/img/master/spotlight_img/%E5%9B%BE%E7%89%872021-05-30-23-03-42.png)




# “等下”
# “我是个新手啊 这玩意直接下载就能用了？”



并不是……至少先装一个Python 3.6吧，鉴于这东西已经官宣过时了，这里给大家放一个[下载链接](https://www.python.org/downloads/mac-osx/)吧，左侧选对应系统的Installer下载双击安装即可

![图片2021-05-30-23-03-32](https://raw.githubusercontent.com/laciechang/img/master/spotlight_img/%E5%9B%BE%E7%89%872021-05-30-23-03-32.png)