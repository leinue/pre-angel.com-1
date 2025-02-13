---
title: "如何打造一个高效的分布式研发团队"
author: yang-xie
categories: news
tags:
  - steamory
  - team
image: assets/2019/09-efficient-distributed-rd-team/20190906111119.png
---

开发者群体是个与其他工种不同的群体，他们热爱创造，工作是为了满足自己的创造欲，是完全自驱的；而优秀的开发者，完全不受地理位置限制。

这就是我们要建设分布式研发团队的原因 —— **一个多样化的团队是更好的团队。**

我们成功建设了一个分布在中国五个省市的高效研发团队，我们构建的产品，服务全球七个国家和地区的用户。当来自各个地区，拥有不同背景的人联合起来后，极大的拓展了我们的力量。本篇文章将总结我们在建设一个分布式研发团队时所面临的问题和解决方案。

分布式研发团队相比坐在一个办公室里的团队，存在着更多问题，比如工作时间不重叠、团队融合和激励，但实践来看，最需要解决的是以下三个问题：

1. 协作问题；
2. 项目管理问题；
3. 价值观和文化的传递问题；

## 协作问题

当你和同事坐在同一间办公室时，吼一嗓子就能得到回应。但在一个分布式团队中，经常会出现消息未读、电话没人接的情况，分布式协作是一个自由的环境，这种情况是允许出现的。当然，这种事情并不说明项目会得到延期，因为某个模块的开发者会在其他时间完成该做的事情。但这样的情况往往会使得不到回应的人抓狂，软件系统变复杂后，模块之间往往相互关联，如果没有得到及时回应有可能会导致工程出现问题。

沟通上的另一个问题是团队之间可能没有见过，不过这在开发者群体中不是什么大问题，开发者已经习惯了在 Github 上向陌生人提 Issues 或者帮助陌生人修复 BUG。

**从实践中来看，协作主要包含两点：沟通和信息同步**。为了保证高效的分布式协作，我们制定了以下基本的协作原则：

1. 由一个人来起草月计划，其他人一起做修改和补充，周计划围绕月计划进行；
2. 每周一上午一次视频周会，同步上周的进展和本周的计划；
3. 每个人以去中心化的方式（非项目组织者统一指挥）制定自己的计划，每个计划必须激进（猛跳能够到的目标）和有明确的 Deadline；
4. 产品开发允许延期和变动，若有延期或变动，在群内同步原因和后续计划，做到每件事必有 Deadline；
5. 内部测试不追求完美，若有可预览的进展，及时在群内同步并请大家测试（我们没有专门的 QA，遵循的原则是由非模块开发者来进行测试）；
6. 使用高效的工具做即时推送，对信息进行最大限度的同步；

这需要给每个人一点时间来适应，一旦适应好之后，协作效率会和和同事在一间办公室一样甚至更高。

## 项目管理问题

分布式协作另一个大的问题是项目管理，我们由开发者自己决定每月每周每天要做什么，并按计划进行，这一点基本上没有什么问题，**参与分布式协作的人必须是能够自我管理的人**。出问题的环节也不在这里，而是需求质量。

我们出现过至少两次需求不合理导致返工的问题，这对开发者本人和项目本身都是很大的损耗，每当出现这种情况时，团队便会出现抱怨的声音。这类问题往往有如下几种场景：

1. 产品经理在提需求时没有想清楚，开发者 review 时也没有思考完全，做了一半后发现技术上是不符合逻辑的；
2. 开发者在写方案时没有将方案对齐到具体的参数、返回结果和报错信息，同时也没有其他人及时留意到这个问题，导致实际使用时需要进行二次修改；

这个问题的解决方案也很简单粗暴，就是由每一个干系人仔细讨论，因此我们制定了一个流程：

1. 模块负责人在可以在线编写和协作的文档中起草方案；
2. 相关干系人在文档中评论，提出问题和疑惑，将解决方案对齐；
3. 所有疑问和边缘条件都解决后，我们将所有需求细化到任务管理工具上并开始开发；

这个流程虽然看上去多了些扯皮的工作，但是能显著提高需求质量。

项目管理上另外一个很重要的点是使用**「高效的生产力工具」**。你可能会想「生产力工具」本来就是高效的，前面再加个「高效」，是不是重复了。其实不然，生产力工具很多，选择最好用的工具将事半功倍 ——**工欲善其事，必先利其器。**

我们核心只使用了两款工具：

1. Tower —— 用来做具体的项目执行；
2. Lark 飞书 —— 用来做即时沟通、文档协作和 ChatOps；

除了这两款，还有邮箱用来和海外用户交流、Git 用来管理代码，不过这属于基础工具了。

工具链保持简洁很重要。**前段时间，我们在 Tower、倍洽、企业微信、Notion、石墨和 Google Docs** 之间到处切换，直到有一天团队再也受不了，我们争执了一番后将即时沟通、文档协作和 ChatOps 换到了 Lark 上，Tower 不变依然用来做项目执行。我们本有换掉 Tower 的打算，不过鉴于更换成本，我们还是选择了留在 Tower 上，想换掉 Tower 的原因是 Tower 不提供 API 让我们能在群聊内即时将任务同步到看板中，它只能单向推送，这不符合 ChatOps 的设计理念，有时也会耽误我们的生产效率，因为我们还要在网页和聊天窗口中切换。

Lark 的 Notice Bot 很有用，我们的 ChatOps 都是依赖 Lark 的 Notice Bot，我们在内部打造了一个「推送」的世界。

![git](/assets/2019/09-efficient-distributed-rd-team/20190906111548.png)
Git 消息推送

![resp](/assets/2019/09-efficient-distributed-rd-team/20190906111626.png)
响应时间过长或服务不可用推送

![users](/assets/2019/09-efficient-distributed-rd-team/20190906111711.png)
用户反馈推送

![wxapp](/assets/2019/09-efficient-distributed-rd-team/20190906111745.png)
小程序反馈推送

![sdk](/assets/2019/09-efficient-distributed-rd-team/20190906111828.png)
SDK 需求推送

这些都属于一个研发团队中比较基础的操作，但当你处于一个分布式协作团队中时，因为看不到彼此在干什么，因此当所有信息即时推送、即时同步时，会让团队每个人都有安全感。我们的研发团队是一个紧密型小组，我们紧密合作，构建并交付解决方案。这种推送让分散的小组对他们正在构建的东西、什么能提高效率有清晰的认识，并具有主人翁精神，这让它非常适合于团队的分布式性质。

## 价值观和文化的传递问题

最后一个问题是价值观和文化的传递问题，这是最难的问题。无论是沟通问题还是项目管理问题都能用流程和工具来解决，而价值观光和文化只靠这些是不够的。

首先说一下我们团队的组建过程，早期的开发者是大学同学，后来有从用户转化过来的开发者，我们的用户爱我们的产品，从用户变成了这款产品的创造者和维护者。此外，所有不涉及商业核心的代码，我们都是开源的，由此也吸引了一批开发者为我们维护各语言的 SDK。

当然，我们还是要依靠一些现代工具。

首先是视频会议，我们使用的 Lark 会同步每个人的日历（我们希望每个人都能将自己的日程信息化，这样会非常便于管理），这样会议协调会很容易，同时我们保证每次会议大家都能露脸，这让每个人都能见到其他人的神情、动作，虽然隔着屏幕，也比看着聊天框里的文字和表情要亲近一些。

除了这样的工具外，就是每天的具体细节。尊重和信任是对人最大的激励、鼓励每个人分享的团队文化才是正向的。同时还要鼓励每个人把自己的能力贡献给项目和组织，并获得事业上的发展。鼓励每个人互帮互助，没有等级，团队的工程师可以直接开喷领导者（我不是说开喷是好事，而是允许这种情况发生）。

这些都是通过线上交流获得的，线下活动也是必不可少的。比如每个月邀请大家聚到一起娱乐、一起喝酒、一起打游戏、每个节日互送礼物。

总之，让大家成功，让项目成功，是构建组织文化和价值观的根本目标。

### 相关阅读

1. [Authing 是什么以及为什么需要 Authing](https://authing.cn/blog//Authing%E6%98%AF%E4%BB%80%E4%B9%88%E4%BB%A5%E5%8F%8A%E4%B8%BA%E4%BB%80%E4%B9%88%E9%9C%80%E8%A6%81Authing.html)
2. [Authing 知识库](https://learn.authing.cn/authing/)
