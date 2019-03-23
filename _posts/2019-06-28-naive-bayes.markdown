---
layout: post
title:  "朴素贝叶斯实战心得"
crawlertitle: "NaiveBayes"
summary: "MachinLearning"
date:   2019-03-23 12:09:47 +0700
categories: MachineLearning
tags: 'MachineLearning'
author: Jiazhi
---

*本学期担任了本科课程机器学习的助教工作。老师主要讲解的是机器学习实战这本书，我也下载了无耻的盗版PDF到kindle上看了一下，觉得这本书虽然不讲太深入的原理和细节，但是却注重实战，个人觉得对于有软件工程基础，但数学基础较差的我来说是个不错的启发书。同时本学期还选修了刘老师的统计机器学习课程，这门课就讲原理更多了，两者结合，在我来看居然有着不错的效果。前端时间参考机器学习实战上的代码自己也搞了一个用垃圾邮件分类的贝叶斯算法，有了一些心得总结，写在这，以免老了忘记。*

**MLE&MAP**

首先我想说说极大似然估计的一些个人理解，一开始我在理解这个概念的时候并不准确，总觉得这个概念很抽象，但是经学习之后，我得出以下体会：我认为似然的解释就是“可能性”，是事件发生“可能性”，他代表了出现这个事件的机会，但是并不是严格的概率，有很多不符合这个事件概率的性质，但是我们拥有这个可能行就可以对样本数据作出判断，这样我们的目的就达到了。关于极大似然估计和最大后验概率，从条件概率的形式出发，两者其实就差在式子上面的 p(θ), 两者的目的都是寻找最大化的参数 θ, 极大似然估计忽略了这个 p(θ)，因此它最大化的这个后验不是真正的后验，只是这个后验事件的似然，也就是可能性。而最大化后验估计没有忽略 p(θ)。

------------

另一个角度去看，前者认为参数本身是确定的，也就是均匀的，而后者认为参数也是服从一个不均匀的分布，计算时不能忽略。在上述的例子中，其实两个估计方法都用到了，对于每个词汇出现的概率我们用了极大似然的方法去估计，也就是说这个词汇服从的多项式分布参数的确定的，他都有样本数据决定，因此算出来的值是该词汇数除以总词汇数。这个寻参的过程是可以用数学的方法去表达的。其实就是一个求导数的过程，在一段连续的空间里面寻找使得表达式最大的参数。当然估计的方法也可用最大后验，就是对于参数加上一个属于自己的分布，如正太或者Beta分布。

------------

However, we can now create declarations that are bound to any block, called (unsurprisingly) *block scoping*. This means all we need is a pair of `{ .. }` to create a scope. Instead of using var, which always declares variables attached to the enclosing function (or global, if top level) scope, use `let`:

{% highlight js %}
var a = 2;

{
    let a = 3;
    console.log( a );   // 3
}

console.log( a );       // 2
{% endhighlight %}
