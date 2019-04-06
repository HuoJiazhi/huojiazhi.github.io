---
layout: post
title:  "Attention is all you need"
crawlertitle: "Attention is All You Need"
summary: "论文研读"
date:   2019-04-06 12:09:47 +0700
categories: 'MachineLearning'
tags: 'MachineLearning'
author: Jiazhi
---
*续上上篇关于NLP的学习整理，这里我整理了Attention is All You Need这篇论文中提出的一些关于NLP的新颖做法*

**Attention**

Attention其实就可以解释为注意力，我们在阅读理解或者在听别人说话的时候都会将注意力放在一定的位置，这样有利于我们更好地理解整个句子的意思。在之前NLP中，RNN和LSTM都对于长句子有很大的缺点，因为当他们处理文本时候，他们会将隐藏层的状态合成一个整体C，这个C会对更近的单词记忆更深，而对远的单词有点失忆，同时例如我们在做翻译的时候，对于其中一个词的翻译肯定是跟对应的英语单词关系更大，这时候就不是每一个隐藏变量h对输出的结果造成的影响都是一样的了，所以科学家们就引入了Attention机制。

第一种比较常用的Attention机制

http://www.cnblogs.com/robert-dlut/p/5952032.html 这个blog介绍得很好

第二种是论文中提出的Self-Attention机制

https://www.cnblogs.com/robert-dlut/p/8638283.html 还是同一个博主的介绍
