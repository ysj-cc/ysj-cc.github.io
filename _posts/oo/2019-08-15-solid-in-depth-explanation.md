---
layout: post

title: "面向对象设计SOLID创业经"
date: 2019-08-15
categories: [OOD]
tag: [OO]

author: "袁慎建"
published: true

brief: "
做了这么多年的面向对象编程还是写出违背SOLID原则的代码，对这些原则不敏感，看过一遍又一遍，还是会忘记，经常在Code Review中被怼，如何是好？难到SOLID原则本身就有错？难道我不应该涉水OOD？
<br/><br/>
编程和培训经验告诉我，原则一般都比较抽象，理解起来不是那么友好。别说是刚接触OO的程序员，有过一定经验的人也不一定能吃透这几个原则。想要提高对OO原则的敏感度，第一步，我们要弄清楚这五大原则到底在讲什么。本文，袁Sir的创业历程将为你揭晓SOLID，一起来看看它到底有多坚固（SOLID）。

"

---

* content
{:toc}


做了这么多年的面向对象编程还是写出违背SOLID原则的代码，对这些原则不敏感，看过一遍又一遍，还是会忘记，经常在Code Review中被怼，如何是好？

- 难到SOLID原则本身就有错？
- 难道我不应该涉水OOD？



既然是对SOLID原则不敏感，我们来先看看SOLID的组成：

- **S**ingle Responsibility Principle，单一职责原则
- **O**pen Close Principle，开闭原则
- **L**iskov Substitution Principle，里氏替换原则
- **I**nterface Segregation Principle，接口隔离原则
- **D**ependency Inversion Principle，依赖倒置原则

编程和培训经验告诉我，原则一般都比较抽象，理解起来不是那么友好。别说是刚接触OO的程序员，有过一定经验的人也不一定能吃透这几个原则。要提高对OO原则的敏感度，第一步，我们要弄清楚这五大原则到底在讲什么。接下来，袁Sir的创业历程将为你揭晓SOLID，一起来看看它到底有多坚固（SOLID）。


---


## ISP：设计小而精美的工具箱，提高顾客体验

己所不欲勿施于人！接口隔离原则诠释着一个与人相处另一个道理：*投其所好*


```
袁Sir创业初期经营了一家五金器具共享租用店，遇到两类顾客，A顾客需要剪刀、锤子、扳手、电锯，B顾客需要锤子、扳手、水果刀、梅花刀。袁Sir为了图省事，把这个六把工具同时装在一个工具箱里，每次都把装有6把工具的工具箱给A或B租用。

经过几次来回借还，袁Sir收到顾客的抱怨，为什么呢？因为袁Sir这么做增加了A和B的负担，首先多了两把工具，扛来抗去的累得多，其次他们拿回去之后会发现："咦，这两个是啥，我没要这个呀？莫非是增值服务？但我要用来来做啥呢？" 结果A从未用过水果刀和梅花刀，但A还要保管好这两工具，增加了保管的成本。同理，B顾客也会面临同样的问题。为了提高顾客的体验，袁Sir把这两类顾客的工具单独用两个更小的工具箱装好，分别提供给A和B，并得到了两类顾客的一致好评。
```

接口隔离原则对我们的行为做了约束，不应该是我们自身为了图一时的方便，塞给用户一些他本需要的东西，而应该是用户要什么，我们就给他什么。

***在代码设计上，尽量不要将一个大而全的接口扔给调用者使用，而是将每个调用者关注的接口进行隔离，封装打包后分别提供给他们。***


---

## LSP：让客户坚信徒弟能代替师傅干活
里氏替换原则则重申了一句古言：*有其父，必有其子*。同样也适用于*有其师，必有其徒*。

```
袁Sir勤勤恳恳经营的五金租用店2年，挣了一大把辛苦钱，正好赶上房地产兴起的年头，家装市场跟着兴起，他果断买下一家知名的家具厂，并跟一家私人工匠所展开了合作。

SJ是工匠所的一名木匠学徒，从师3年有余，书架、衣柜、餐桌，门、窗这些家具已经能够到跟他的师傅如出一辙了。

袁Sir每次合作都是直接跟SJ的师傅对接，而在实际执行过程中，师傅有时候因体力跟不上，就交给SJ去做，好在每次生产出来的家具都能够让袁Sir满意。几次合作下来，袁Sir便相信：徒弟继承了师傅的手艺，师傅能做的这些家具，徒弟也一定能做得一模一样。

2017年，房地产彻底疯了，袁Sir一次性采购订单多出了以往2倍。为了如期交付，SJ的师弟小Y也参与进来。不幸的是，个性十足的小Y打造衣柜和门窗的方式跟师傅的风格差别很大，设计出来的家具让袁Sir一脸懵逼，始料不及的三丈大火烧尽后，袁Sir果断地中断了跟这家工匠会所的合作...
```

***在代码设计中，里氏替换原则对子类进行了约束，子类不应该去重写父类的具体功能。对调用者来说，能够调用父类的地方，一定调用其子类，并且预期结果是一致的。***

换句话说，子类不应该去修改父类已有的功能（在Java中，体现为子类重写了父类中非抽象的方法）。

所以，如果你的继承体系中出现来这种不一致的现象，很可能是你的抽象不够恰当。需要进一步去思考如果去做一个更合理的抽象。关于代码示例，请在文末点击阅读我的文章 *让里氏替换原则为你效力[1]*


---

## DIP：清晰良好的合作协议，让彼此更加信任
依赖倒置原则其实揭露了一个工作中非常重要协作准则：部门之间通过约定好的协议来合作，而不关心对方内部由谁做协议所规定的事项。

```
经过上一次不愉快的合作，袁Sir虽然少挣了一笔钱，还生了一肚子气。但台风来，猪想飞你也挡不住。在房地产彻底疯了的这几年里，袁Sir又捞了好几大桶金。有了钱能做什么呢？当然把公司做大，再挣更多的钱呀。

袁Sir秉着 '麻雀虽小，五脏不能不全' 的原则，成立了财务部、法务部、行政部、人事部、市场部、销售部，由于期初业务量没有大到招架不住，这些部门都是光杆司令，而且人事、行政、财务、法务四个部门是由小蔡掌管（袁Sir也流露出了资本家的面貌）。

袁Sir想核对一个报销单，就直接找财务部的小蔡办了，想举办一场隆重年会还得找小蔡，想了解上个月的销售业绩，他去找了销售部的老肖，当然找的最多的还是市场部老史。

经过大半年的快速发展，每个部门从光杆司令变成了群狼作战。袁Sir仍然按照之前的方式办事，但遇到了烦恼 -- 前天报销单还是小蔡在处理，昨天变成了小吴，今天又换成了小任。当然，其他部门也产生了相同的现象。苦思冥想，袁Sir出了一招：部门的负责人制定一个固定的服务列表，比如财务部小蔡提供服务列表：
1. 核对报销单
2. 处理报销
3. 发工资
4. 招聘新同事
5. 评审绩效
6. 举办年会
7. 营业执照审核

袁Sir此时要处理报销、发工资，只用联系小蔡就好，当然小蔡交给谁去做，袁Sir压根不知道，也不需要知道。当然其他部门跟财务部合作也轻松了很多。此后袁Sir对所有部门都进行了整改。

此时袁Sir终于才体会到当老板的一丁点美好了。
```

依赖倒置原则说的是，你本来认识的是一个提供某项服务并且具体做事的人，为了解放自己和他人，你只用认识一个提供服务清单的接口人，而谁去做具体的事情你不用关心。

***在代码设计中，调用者应该依赖一个抽象的服务接口，而不是去依赖一个具体的服务实现，这样就把依赖的关系倒置过来。***


---

## SRP：各司其职，工作效率会大大提升
单一职责原则告诉我们一个重要的处世态度 -- *勿贪多，贪多你将可能踏入欲望的深渊，重者万劫不复。*


```
袁Sir起初让小蔡统管了人事、行政、财务、法务四个部门，业务扩张后也只是给小蔡多招了10来个人。小蔡大脑里就不得不绷紧四根弦，他要给部门各个同事合理分配任务，确保公司能够正常开展日常活动、人员考核培养、工资发放等工作，当然还有一些诸如工商督查、账务审核、信息安全审核等敏感的活动。

暂且不说小蔡有多累，关键是有一次捅了个篓子，差点没葬送公司前程。

一天，工商局来了几个人审核公司的营业资质，就在小蔡跟工商局负责人交涉的过程中，其他管理账目的两位同事因为一项数据没法对齐的数据起了点小争执，全然忘记还有工商局调查人员在，口角中抖了一些账目相关的敏感事情，好在小蔡反应快，及时进行了制止，当然也做了一些额外的安抚工作，把这事给糊弄过去。

这事传到袁Sir耳中，加上小蔡多次跟袁Sir反馈业务太杂，不但累且容易出篓子，袁Sir这才把几个部门进行了拆分，人事部交给了小任，行政部交给了小邢，法务由老发掌管。

经过几个月的验证，让袁Sir欣喜的是，运营成本不但没有增加，员工的工作状态也比之前大有改善。

从此，财务部门小蔡提供的服务列表：
1. 核对报销单
2. 处理报销
3. 发工资

人事部门小任提供的服务列表：
1. 招聘新员工
2. 员工绩效考核
3. 员工培养

行政部小邢提供的服务列表是：
1. 举办年会
2. 接待来宾

法务部提供的服务列表是：
1. 审核营业执照
2. 审核信息安全


周五晚上10点，袁Sir走出办公室大门，哼着小曲自言自语道：还得专门的人干专门的事呀，勿贪多，贪多必失...
```

分离关注点是提高效率的一个很好的途径，如果你同时需要兼顾多项关系不大的工作，你的注意力经常在不同的上下文切换，会降低工作效率，企业为你付出的成本就会增加，更糟糕的是可能会出现一些意外的灾难。

***在代码设计上，让一个类只处理一组相关的事情，控制了它的变化方向，后期也能更好的定位。如果引发变化的因素很多，会导致类的职责过多，难以维护，上帝类就是这么形成的。***



---


## OCP：引入中间人读书大使，解放自己
开闭原则诠释着一个互联网产品用户体验的真谛：*把用户当"傻瓜"，知道的越少，用起来越简单，用户越舒服。*


```
用了这几大理念去经营公司后，袁Sir的公司已经步入正轨。他开始思考公司文化建设方面的事情。

袁Sir一直对读书非常重视，他想在公司把读书运动搞起来，每周搞一次分享大会。起初他提议由行政部和人事部来牵头搞，两个部门轮流来，自己直接分别跟两个部门负责此事的负责人对接。

两个月过去了，公司的读书氛围得到大大提升，书架遍布公司各个角落，水果时间也从八卦转向了读书心得的分享。

欣慰之余，袁Sir也感觉有点力不从心。经常出现这种现象：有时候去他找人事部的小史商量工作，却被告知这周轮到行政部的小郑了，而去找小郑的时候，被告知市场部也是组织者之一了，这周轮到市场部了。

袁Sir因为业务繁忙，加上翻来覆去的对接工作，搞得心累，但他又很重视这件事情。琢磨良久，他决定给自己招一个读书会大使，每周要开展读书运动大会前，他直接跟读书大使对接，大使后续再去协调对应的部门开展工作。

经过这么一整改，袁Sir得到了解放，再也不用关心这周该由哪个部门组织，下次会有什么新的部门加入进来。

看着读书运动在公司里遍地开花，袁Sir心想着年底了要给读书最多，分享最多的同事多发12个月的年终奖...

```

开闭原则提倡对修改关闭，对扩展开放。仍然从用户视角出发，用户只用按照统一的方式去享用你的服务，后期如果你的服务有变更或扩展，对用户来说是透明的，不应该去修改用户的使用方式。

***在代码设计上，你应该为你的服务调用者提供一个他需要的抽象、高层次的接口，后期你的服务有新的种类，你只需要新增一个实现该抽象、高层次接口具体服务，而不需要修改调用者的使用方式。***


---

## 面向对象设计回忆

从袁Sir的创业故事中可以看出来，袁Sir在不同阶段之所以面临各种不同的痛点，原因无非两点：

1. 关注的事情太多
2. 关注事情的细节

创业初期，袁Sir这么做问题不大，但公司不但在发展壮大（如同软件的演变），袁Sir就需要琢磨出新的方案，而这些方案的核心观念无非两个：

1. 分离关注点，各司其职
2. 引入一个中间人

在面向对象软件设计中，*关注点分离* 和 *各司其职*，其实体现的就是软件设计的精髓 -- *高内聚，低耦合*，*引入一个中间人* 则跟 *面向抽象编程* 有异曲同工之处。

在面向对象设计领域，恰当的*封装* 能够让你的类、模块更加*内聚*，*继承* 除了让你的程序更好的复用，同时能够隐藏你的子类实现细节，结合*面向抽象编程*，让你的用户更少的去关注细节，通过*多态* 的特征来促成*低耦合* 目标，

---
 
## 总结：从用户视角出发需要大量的练习
在前文中，我多次提到用户视角，我想强调的是：

> 掌握了再多的技巧（设计原则、设计模式等），一旦忘记了初衷，失去了目标，代码写得再漂亮、再健壮也体现不出应有的价值。一切应该从用户视角出发，编写出*简洁可用* 的代码足以。

在用户视角的大前提下，我们再来看SOLID原则，它其实是在帮助指导我们设计出*高内聚，低耦合* 的软件，降低软件后期的维护成本。遗憾的是，原则往往不能高效地指导我们写代码，还需要结合大量的实践编码练习。

那么如何开始呢？

我在我的敏捷工程实践训练营中经常会告诉学员："了解了SOLID设计原则的原理之后，你要做的是忘掉他们，然后拾起两把接地气的武器来写代码 -- TDD && 简单设计。"


---

## 参考阅读
1. [让里氏替换原则为你效力]({{ site.url }}{{ '/make-lsp-working-for-you/' }})
2. [解析简单设计原则]({{ site.url }}{{ '/analyse-principle-of-simple-design/' }})
3. [聊聊面向对象设计中的Is-A]({{ site.url }}{{ '/talking-about-is-a-in-ood/' }})
4. [写了这么多年代码，你真的了解SOLID吗？](https://insights.thoughtworks.cn/do-you-really-know-solid/)











