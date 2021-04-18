---
layout: post

title: "重构到什么时候可以停止了？"
date: 2020-06-08
categories: [eXtreme Programming]
tags: [REFACTORING-QUESTION-100]
column: REFACTORING-QUESTION-100
sub-tag: "Basic Concept"

author: "袁慎建"

brief: "
百问重构系列问答。
"

---

* content
{:toc}

---

重构会优化代码内部结构，也就是让代码设计变得更好。所以要回答这个问题？也就要搞清楚，什么设计是恰到好处的？

什么样的设计是恰到好处，这又是一个仁者见仁智者见智的事情，而且一旦你较真起来，很容易进入自嗨模式，一去不愿返，陷入过度设计的深渊。如今的软件，真不担心你设计不足，就担心你过度设计。这就跟现在很多“富贵”病类似，不是营养不足，而是营养过剩造成。

经常一讨论起什么是好的设计，很容易发生“打架斗殴”事故。所以有人干脆就提倡，自个知道就好了，所谓 “道可道，非常道”，然后淡定自若地去写自己的代码。这么一来，那些高手好像大部分人能够接近恰如其分的设计，但他们的经验始终在脑海里。对于那些新手，就有点苦不堪言了。不好好想，会被说成头脑简单，想多了呢，又会被嘲讽：吃多了撑着。到底如何是好？

那什么是好的设计，不用高谈阔论，搬出整洁架构、企业架构模式来画框框，这些离落地太远。也先不谈SOLID、GRASP、设计模式等这些抽象的东西，这些对新手压力太大，虽然这些都是新手基本功修炼里的必修课程。

从很简单的命名问题起步，你的变量、方法、类、层次等命名。当一个了解了业务的新人看你的代码，他需要深入各种细节，需要你做额外的解释吗？如果几乎不需要了，你差不多能做好90%的设计了。提到命名是关乎Clean Code的最基础的一点，但它绝不只是新手去关注的，连Martin Fowler这样的大师级人物也对命名予以高度关注。他2009年在自己的博客 [TwoHardThings](https://martinfowler.com/bliki/TwoHardThings.html) 中表示很赞同Phil Karlton这个哥们所说的 -- **计算机科学中，最难的两件事是：命名和缓存失效**。关于命名，有一个神奇的网站推荐给你：[Codelf](https://unbug.github.io/codelf/)



再往前走一点，如果非要说个能帮助思考和行动的框架，Kent Beck提出来的[简单设计](https://www.jianshu.com/p/d6252d3dd6e8)是我推荐的一个，按照那几条原则，吃透优先级顺序，配合TDD的编码方式，就能解决5%的设计问题了。最后剩下的5%，可能是没法解决或者不值得去解决的问题。

重构是程序员应该持续进行的活动，是一项值得根植于意识形态的东西。要说有停止，也只是阶段性的停止 -- 此时此刻，你觉得当下的代码足够简洁，满足简单设计四原则，请你继续前进。

理想很丰满，现实很骨感，说得再多，不如多去写几行代码，去看几本有用的书，推荐几本起步的书：

1. [编写可读代码的艺术](https://book.douban.com/subject/10797189/)
2. [代码整洁之道](https://book.douban.com/subject/4199741/)