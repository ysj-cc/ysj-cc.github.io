---
layout: post

title: "我的简单设计价值观"
date: 2018-07-19
categories: [eXtreme Programming]
tags: [Simple Design]

author: "袁慎建"

brief: "
简单和复杂多用于形容事物或人的属性或状态，容易和困难一般形容达到某种目标的过程。所以就有了“人活简单点真难啊！”、“系统一不小心就复杂化，非常难以维护！”等感慨。这些感慨流露出一种愿望 -- 保持简单。

<br/><br/>
作为有代码洁癖的程序员，我平时在工作中一直尝试对简单设计的理解和运用，本文中我结合了平时的敏捷工作来思考简单设计背后的价值观。
"

---

* content
{:toc}

---

## 保持简单
> 简单是一个成年人司空见惯的词，我们大部分人却觉得纯真的孩子才是简单的

很多时候，我们习惯把`简单`跟`容易`理解为是一个意思，比如：这个问题好简单（复杂），另一层含义是：解决这个问题很容易（困难）？这个时候简单跟容易是一个意思。再比如说：我真羡慕她能过如此简单的生活。另一层含义是什么呢？我们先来看一张图：

![]({{ site.url }}{{ site.img_path }}{{ '/xp/simple-vs-complicated.jpg' }})

简单和复杂多用于形容事物或人的属性或状态，容易和困难一般形容达到某种目标的过程。所以就有了`人活简单点真难啊！`、`系统一不小心就复杂化，非常难以维护！`等感慨。这些感慨流露出一种愿望 -- *保持简单*。对于人来说，保持简单可能意味着人情世故的简单、工作关系的简单、生活状态的简单。对于软件系统来说，则意味着系统设计的简单、部署运维的简单等等。

---

## 三重境界
> 看山是山，看水是水；看山不是山，看水不是是水；看山是山，看水是水。

`保持简单`的确不是一件容易的事情。禅宗提出的人生三境界中也诠释了这个理：*人从简单开始，以复杂贯穿了大部分甚至整个人生，最后返璞归真*。

对应到一个需求简单的软件系统中，系统的设计一开始处于简单的状态。然而软件开发的核心问题是复杂多变的业务需求，随着时间的推移，软件系统可能呈现出以下三个状态：

![]({{ site.url }}{{ site.img_path }}{{ '/xp/system-three-status.jpg' }})

没有人希望系统处于第三个状态，所有人都期望能从第二个状态回到第一个状态。映射到禅宗的人生三境界，系统的三境界应该是：

1. 清晰 -- 单一化
2. 复杂 -- 层级化
3. 清晰 -- 模块化

![]({{ site.url }}{{ site.img_path }}{{ '/xp/system-three-phases.jpg' }})

在面临复杂多变的业务需求，如何设计一个恰好简单够用的系统？如何保持系统的高响应力？我们一直都没有停止对最佳实践的探索，我们始终为这些目标奋斗，只为了引导系统经历禅宗三境界。软件开发的所有问题最终都能归结到人身上，那么驱动我们不断前进的力量是什么？

*我的答案之一是：对简单设计、高响应力价值的认可，对简单设计价值观的深层次内化。*

---

## 普适价值观
提到价值观，大家可能有一种感觉：望着这些高大上的价值观词汇，感觉缺点什么，却总又说不上来。比如Scrum的价值观：`专注`、`开放`、`承诺`、`勇气`、`尊重`。再比如极限编程（XP）的价值观：`沟通`、`简单`、`反馈`、`勇气`、`尊重`。尤其是刚开始接触这些知识体系的新人，每个词都能看懂，就是不知道它们是如何去指导Scrum和XP。

我亲身经历了Scrum和XP的实践之后，再回过头来看，才深刻体会到，Scrum和XP的那些实践其实跟它们的价值观都非常吻合。同样，我能够在日常开发以及培训和练习中去落地简单设计，这背后驱使我不断前进的是已经内化的价值观：

- 洁癖
- 专注
- 懒惰
- 勇气
- 反馈

### 洁癖
洁癖多数场所被我们用来形容一个人在生活上不容易相处，因为非常讲究个人卫生而适合一个人独自生活。我也经常在Code Review中听到同事开玩笑说我有代码洁癖，比如对命名太较真了。一开始我会有所妥协，毕竟软件开发是一个团队来完成的，如果因为我的严格而让其他人不舒适，不利于团队协作。可是时间总会告诉我，那些贴有`不用心`、`不认真`或者`不严格`标签的小魔头在后面出来制造各种噪音，比如命名看不懂、结构不一致、架构臃肿等等。

做程序员这几年，洁癖已经深刻影响着我的编码和设计风格，小到变量命名、代码注释、文档管理，大到系统技术架构和部署架构，我都会时刻保持警惕，尽我所能去消除噪音污染。在没有其他更重要的原因（比如客户交付压力，即便有，也应该尽力去消除）前提下，我都会尝试让团队采纳我的洁癖。

洁癖更侧重于团队个体成员，对于我们个体，可以通过不断强化自己的整洁代码、整洁架构的意识来保持代码洁癖和架构洁癖，并尝试在实践中去运用它们。而对于团队，我提供一条指导原则：
*任何有助于提升系统质量的洁癖都不应该被忽视，团队应该尽全力接纳并落实*。


### 专注
在Scrum中，专注强调的是`所有人都专注于Sprint工作和Scrum团队的目标`，大家都为同一个目标努力。对于简单设计，我们要专注在哪里呢？我给大家分享我经历过三个典型的场景：

1. 一上来匆匆忙忙编写业务代码，没有Tasking，没有测试，没有设计，业务Scope逐步偏离或扩大
2. 在编码阶段，听到声音：“你这个设计太土气了，都没用设计模式”，于是琢磨着怎么去套设计模式
3. 在系统架构设计阶段，有人说：“什么年代了，你还不拆出几个微服务”，于是尝试拍脑袋拆出一个分布式单体

上述三个场景根本原因是不能很好地专注于自己要实现的真实业务价值，要么缺乏思考和设计，要么受外界影响，本末倒置。你可能会质问：我们不应该多做设计来兼容后期可能出现的情况吗？为未来做设计，难免会掺入猜测，不但增加系统的复杂度，还可能浪费成本。

我们应该专注于当下的真实业务价值，让系统保持简单，再借助一些实践来响应未来的变化。

### 懒惰
> 懒惰是一个优秀的程序员必备的特质，因为Ta勤于思考如何才能懒惰。

`懒惰`听起来是一个负面的词，几千年的文化价值观在告诉我们要做一个勤奋努力的人。而到软件开发领域它却成了一个靓丽的标签了，我们一起看看程序员的懒惰：

1. 需求变更，我懒得动太多代码。怎么办？隔离变化，分离关注点
2. 重复的手工集成和测试，我懒得做这个事情。怎么办？搭建自动化流水线
3. 用户鉴权分散在各个服务中，我懒得修改所有的服务。怎么办？引入API Gateway
4. 每次项目上新人，搭建环境总找我，我懒得跟他们一次一次地讲。怎么办？编写自动化脚本和文档指

如果每次面对相同的问题，不得不花精力去处理，在这种毫无挑战的重复性工作中我们很容易犯错，所以如果你懒得去做这些事情，懒惰会驱使着你去思考一种自动化的方式，从而取代一遍遍的重复的操作，解放人力，并且你还会思考如何运用KISS(Keep it Simple and Stupid)原则来落实自动化方案。

CV(`Ctrl + C` + `Ctrl + V`)程序员也很懒惰，但他们更偏向思想上的懒惰。我所提到的懒惰以勤快地思考为前提，思考如何能够变得懒惰。

### 反馈
反馈是敏捷和XP的核心价值观，我们通过沟通来获取反馈、通过编写单元测试来快速获得代码的反馈、通过自动化流水线来获得代码库健康状态的反馈、通过AB测试来获取用户的反馈等等，这些都是在强调反馈的重要性。我曾用一句话来概括敏捷：*通过高效地团队协作来获取快速的反馈。*

即便在一条笔直的高速公路上开车，我们也没法保证车一直沿直线前进，我们要时刻保持警惕，通过线条、护栏、其他车辆等物体来获取反馈并调整方向盘来纠正车身方向。对于设计，我们无法保证一开始的方向会一直是正确的，在前进的路上通过各种不同的渠道来获取反馈，从而改进自己的设计，闭门造车最终很可能落下败笔之名。

### 勇气
抛开其他单独谈勇气意义不大，我们常说*无畏之人如魔鬼*，一个心中毫无畏惧的人，不受任何伦理道德和法律的束缚，便同野人无异。正因如此，我所说的勇气是结合特定场景的。

在Scrum和XP中，我们要有勇气去做正确的事情，有勇气处理棘手的问题，有勇气去做出承诺，有勇气去坚持自己的原则，有勇气拒绝损害工作的事情，有勇气去暴露自己的不足并寻求帮助，有勇气去提供有建设性的意见，有勇气去揭露违背价值观的现象。在简单设计中，这些勇气都是我们应该具备的。同时，我们还具备勇气去做一个洁癖、懒惰的程序员。

关于勇气，我提供一条参考原则：
*只要你所做的事情是符合价值观，你都应该无所畏惧，勇往直前。*

---

## 写在最后
简单设计在XP中的定位是一项实践，它本身有一套自己的指导原则。通过在客户交付、公司内训、客户培训中不断思考和运用简单设计，在我意识中潜移默化地积累了一套指导我去落实简单设计的价值观，而这些价值观大多跟我现在所经历的敏捷工作方式有密切关联。

做任何事情，背后总有一套价值观在指导我们。当我们开始接受一项实践并愿意努力落实它的时候，意味着我们已经开始认可它，它背后的价值观得到了我们的认同。起初你不用太在意它，只管认真落实你认可的实践，在实战中去思考总结。好好享受过程，做一个快乐的程序员。








