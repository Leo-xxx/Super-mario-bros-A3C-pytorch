## 一条命通关，这个AI算法玩超级马里奥操作秀翻天丨视频+开源代码

原创： 关注前沿科技 [量子位](javascript:void(0);) *昨天*

##### 郭一璞 发自 北四环  量子位 报道 | 公众号 QbitAI

把超级马里奥玩成下面这样，算什么水平？

能流畅的行走在妖魔鬼怪之间

![img](https://mmbiz.qpic.cn/mmbiz_gif/YicUhk5aAGtCHXTgnnpIAHEHHtiaCPlOsiaFRntWicjWDkkCMIeFuFMHUXNlrgNbJ65TkojaajrNicqwrWOxRL92bXg/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

能掐准食人花出现的时机

![img](https://mmbiz.qpic.cn/mmbiz_gif/YicUhk5aAGtCHXTgnnpIAHEHHtiaCPlOsia5uUWj3j2HCib2W22gRB0QeTvyKWEQnIB9SBX54mRic0lq83AOCgax35Q/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

能灵巧的躲过烧火棍

![img](https://mmbiz.qpic.cn/mmbiz_gif/YicUhk5aAGtCHXTgnnpIAHEHHtiaCPlOsiafMVSU82XiaVuiapVYqEvbRAq0MxckZt0qrbPTvWeXQWAz4ftue3C6sBA/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

能克服各种变态的地形

![img](https://mmbiz.qpic.cn/mmbiz_gif/YicUhk5aAGtCHXTgnnpIAHEHHtiaCPlOsiaribtbTyzlmXiaFpuYEZ34VxATMwCFT3yJWuTZKdZ4ChuXiapps47yKz1g/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

从1-1到7-1，只要一条命，就能全部通过，而且操作几乎没有迟疑，如行云流水一般。

不信的可以看完整视频：



别人玩得这么溜，你是不是只能被小乌龟、喷子弹的小怪物、上上下下的地形虐？

不过，这个玩游戏的不是人，是一只通过深度强化学习算法实现的AI。

## 异步优势演员评论家算法

这个算法已经开源，是2016年的论文《Asynchronous Methods for Deep Reinforcement Learning》中提到的算法的实现。

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtCHXTgnnpIAHEHHtiaCPlOsiaPjJk93ko49Dw0Ph9cvZaYF7hLDGhQJyA0Up2SAkFLg3WOo22HycSJg/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**异步一步Q-Learning**：每个线程与自己的环境副本交互，在每一步中计算，用共享的渐变目标网络Q-Learning损失的梯度，就像DQN训练模型一样。

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtCHXTgnnpIAHEHHtiaCPlOsiaDeqRzIicC99lqMApicCdqKibbQ7WicdPEnVoIQicGjx2iaOKJpJN4lPtZRHA/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**异步多步Q-Learning**：在正视图中通过明确的计算多步返回来运行，因为基于动量的方法反向传播来训练神经网络时，用正视图更容易一些。

![img](https://mmbiz.qpic.cn/mmbiz_png/YicUhk5aAGtCHXTgnnpIAHEHHtiaCPlOsiaic3iaoOQdxWA3O964h24MlHTWK0V3F5kDSs20T4carHGuhe2bylcDIsw/640?wx_fmt=png&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

**异步优势演员评论家算法**：这是超级马里奥AI的核心。智能体中的两个部分，分别扮演演员和评论家，负责创造和监督。

和前面的异步多步Q-Learning一样，演员和评论家在正视图中运行，用相同的多步返回组合来更新策略和价值函数。

演员就像一个小孩子一样，会探索世界，做各种事情。

评论家则类似于前面小演员的爸爸妈妈，负责监督演员的举动，赞扬他做的好的地方，批评他做的不好的地方，告诉自己孩子：你和其他演员（别人家的孩子）差在哪儿了。

因此，演员希望一直能获得爸妈的赞扬，获得积极的反馈，就会根据爸妈的赞扬和批评不断修正自己的行为。

而对于**异步优势演员评论家算法**而言，则是为小演员提供了一所“学校”。如果小演员只在家里学习，可能学到的东西更片面，而且学习速度也比较慢。在异步优势演员评论家算法这所学校里，有“老师”和“同学”能让演员更快的学习，学到正确的知识。

## 游戏达人Viet Nguyen

最后，公布这个算法实现的是GitHub用户Viet Nguyen。

![img](https://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtCHXTgnnpIAHEHHtiaCPlOsiaIPJ57OEibKpIpYEJIyzmMjDeemKErakujpccDJ1Rg8b37edeQUCzfdQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

他是一名AI和机器人方向的硕士，毕业于慕尼黑工业大学，主要研究自然语言处理和计算机视觉。

现在，他是德国手游公司Popcore的一名数据科学家。除了超级马里奥，他还研究过用Deep-Q-Learning训练AI玩Flappy Bird。

![img](https://mmbiz.qpic.cn/mmbiz_gif/YicUhk5aAGtCHXTgnnpIAHEHHtiaCPlOsiauTnfibJZAWMfUGSb9vpTic6tF9HT5cuPe7qeSXT2zgAo6aEp4FSoT1Kg/640?wx_fmt=gif&tp=webp&wxfrom=5&wx_lazy=1)

## 传送门

最后，这个项目已经开源了，发布者公布了代码和模型，针对超级马里奥的每一关都单独训练了模型，在RTX 2080上大概一关费了6~10个小时。

开源代码
https://github.com/vietnguyen91/Super-mario-bros-A3C-pytorch

论文原文
**Asynchronous Methods for Deep Reinforcement Learning**
Volodymyr Mnih, Adrià Puigdomènech Badia, Mehdi Mirza, Alex Graves, Timothy P. Lillicrap, Tim Harley, David Silver, Koray Kavukcuoglu
https://arxiv.org/abs/1602.01783

— **完** —

**小程序|全类别AI学习教程**

[![img](https://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtDpADEKp9rvicB48XgA8ueVdwNbXM1wibYx0ic2pYicwu3UCU5BM6fpDvbH8c4e9JV3uGvYaWAhvGiaTVQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)](https://mp.weixin.qq.com/s?__biz=MzIzNjc1NzUzMw==&mid=2247522241&idx=2&sn=0066e6143f30bca5a2a7896856f58783&chksm=e8d020b3dfa7a9a5e5aa11dd941e996bb35ed03b137621833efeec262a6f14909bb7692fcfda&mpshare=1&scene=1&srcid=&key=0aa21025b9197e7fb298e34686d305866bbc7d0a376e0a583d8c926fd6bf38db47e6be753d8cc11af5e6f39a2fb63d5ffb7ef3bcc8f8b1cfe7f47078f5edec86e9430b8d0199b9c2939522224248a303&ascene=1&uin=MjMzNDA2ODYyNQ%3D%3D&devicetype=Windows+10&version=62060833&lang=zh_CN&pass_ticket=%2BtDZ2Al0VM5wjz5XAzAxV1jJFwepKB91N4744YqAfvwEIleHxJyeJlLibQdxfrJN)

**AI社群|与优秀的人交流**



![img](https://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtDcZyEBVM81oW4VRoNAibJWw1qt2Fxv2MINM4SsViaaOsD7exDSlDnoBKicLIXhuZlgPEPrne0p3NqNg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

![img](https://mmbiz.qpic.cn/mmbiz_jpg/YicUhk5aAGtCQYLj62wpY5xicKlLfDCpKV2aTXlvJODSNPV9Q3zHNEu7UibkwluIwr0TN705vZawerScqBhC67HDQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)



**量子位** QbitAI · 头条号签约作者





վ'ᴗ' ի 追踪AI技术和产品新动态



喜欢就点「在看」吧 !











微信扫一扫
关注该公众号