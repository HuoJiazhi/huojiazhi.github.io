---
layout: post
title:  "NLP学习整理"
crawlertitle: "NLP学习整理""
summary: "NLP学习整理"
date:   2019-04-07 12:09:47 +0700
categories: 'MachineLearning'
tags: 'MachineLearning'
author: Jiazhi
---
*补上一篇关于NLP的巨作，Attention is All You Need,也是我个人读的关于NLP的第一篇论文，但是读起来的时候并不轻松，因为之前并没有很多关于NlP的知识，所以之后又强补了一些关于NLP的知识，也在下面写下了一些心得*

**RNN**
说到NLP怎么能不说RNN呢，因为我们在做语言信息处理的时候，如果使用传统的CNN或者其他模型方法是不具有记忆力的，但是我们平常在交谈或者看文章的过程中，输入我们大脑的信息是序列化的，我们不可能看到这个单词却忘了上一个，所以我们就需要一个能够记住以前的输入并可以对后面的输入产生记忆影响的模型，这时候RNN就出现了。RNN叫做循环神经网络。借用知乎上一个大神的图片，RNN模型可以简单地表示成如下形式。HMM（Hidden Markov Model，隐马尔可夫模型）和CRF（Conditional Random Field，条件随机场）也可以用于序列化的数据挖掘学习。
[![railroad]({{ site.images | relative_url }}/rnn.jpg)]({{ site.images | relative_url }}/rnn.jpg)
这里的x输入就是可以理解成每一个单词，h是我们的隐藏层状态，h<sub>0</sub>一般初始化成0。h的形成由输入和上一层的h共同决定：h<sub>2</sub>=ReLu(Ux<sub>2</sub>+Wh<sub>1</sub>+b)，这里用的U,W和b都是整个网络共享的。网络可以输出y，输出可以有很多种情况：
1. n个输入对应相同数目的n个输出。y<sub>1</sub>=Softmax(Vh<sub>1</sub>+c)；例子：输入为字符，输出为下一个字符的概
2. n个输入对应一个输出。y = Softmax(Vh<sub>4</sub>+c)
3. n个输入对应m个输出。
这里的第三种情况也是我们应用最多的情况，这种结构又叫Encoder-Decoder模型，也可以叫做Seq2Seq模型。首先我们会将数据编码成一个上下文向量c，然后再将他输入到Decoder中，Decoder也是一个RNN模型，然后再利用这个Decoder进行输出y<sub>0</sub>...y<sub>n</sub>。这个情况的应用有很多，例如机器翻译，文本摘要，语音识别和阅读理解等等。
[![railroad]({{ site.images | relative_url }}/rnn-de.jpg)]({{ site.images | relative_url }}/rnn-de.jpg)
除此以外还会有其他的一些变形，如双向RNN和深层双向RNN等。
[![railroad]({{ site.images | relative_url }}/shuangxiangrnn.jpg)]({{ site.images | relative_url }}/shuangxiangrnn.jpg)
[![railroad]({{ site.images | relative_url }}/shencengshuangxiangrnn.jpg)]({{ site.images | relative_url }}/shencengshuangxiangrnn.jpg)
------------
**LSTM**
LSTM整体的结构跟上述的RNN是一样的，但是不同的是LSTM的内部结构和RNN的不一样。RNN中会出现一些问题，RNN往往在面对长语句的时候，由于神经网络层数太深会出现梯度消失或者爆炸等问题，而LSTM可以用于解决该问题。传统的RNN里面的隐藏单元可能是一个ReLu或者是tanh操作，但是LSTM中会有4层结构:3个sigmoid层，形成了三扇门：遗忘门，输入们，输出门，1个tanh层产生更新值的候选项C<sub>t</sub>。如下所示：
[![railroad]({{ site.images | relative_url }}/chuangtongrnn.jpg)]({{ site.images | relative_url }}/chuangtongrnn.jpg)
[![railroad]({{ site.images | relative_url }}/lstm.jpg)]({{ site.images | relative_url }}/lstm.jpg)
