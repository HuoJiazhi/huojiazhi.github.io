---
layout: post
title:  "ikbc-C104机械键盘加灯"
crawlertitle: "ikbc-C104机械键盘加灯"
summary: "键盘改造"
date:   2019-03-29 15:15:47 +0700
categories: DIY
tags: 'DIY'
author: Jiazhi
---

*最近清洁键盘的时候，无意中发现cherry的轴里面都带有灯位，突然奇想，给键盘加个灯。本来想搞个RGB的，但是想到可能会造成很大的光污染，还是暂时装个白色试试水。RGB就留到后面再搞。*

**原料**

1. 电烙铁：加灯肯定需要电烙铁，因为需要高温将锡铁融化，再将灯粘上去。（淘宝随便搜）
2. LED灯（发光二极管）：既然要加灯肯定需要灯珠啦，颜色随便选，我选了白色。
3. 其他配件：电烙铁支架，因为电烙铁很烫，最好搞个支架放一下以免造成意外。
4. 如果键盘PCB本身不带用锡，需要自己加上锡去连接灯珠和PCB。我的旧版ikbc，是有的，新版的听说没有了。
下图很色轴体上面的那两点就是连接灯珠的锡
[![railroad]({{ site.images | relative_url }}/pcb.jpg)]({{ site.images | relative_url }}/pcb.jpg)

**步骤**

1. 拆。把外壳拆除，每一个键盘的拆解过程都不一样，这把ikbcC104不要扭螺丝，直接大力出奇迹把外壳卸了就好。拆完会看到pcb版，留意拆除的时候要轻轻的把连接pcb版的线拔出。
2. 修剪灯珠，因为这个pcb带有锡，把灯柱修剪到一定长度然后插入会更加方便地安装，不需要用吸锡器将锡吸走。长度如下：
[![railroad]({{ site.images | relative_url }}/dengzhu.jpg)]({{ site.images | relative_url }}/dengzhu.jpg)
3. 将灯珠插上轴体上的灯柱位，然后用电烙铁加热后面的锡，然后沾稳了就OK。
[![railroad]({{ site.images | relative_url }}/zhuangguocheng.jpg)]({{ site.images | relative_url }}/zhuangguocheng.jpg)

------------
**成果**

目前还没有研究有哪几种灯效，好像只可以调整灯光亮度fn+上下左右，然后fn+各种数字调整灯光闪烁频率，可惜好像没我最喜欢的点击亮光的模式。
[![railroad]({{ site.images | relative_url }}/chengguo.jpg)]({{ site.images | relative_url }}/chengguo.jpg)
