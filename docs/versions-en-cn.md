# Version History
# 版本历史

## Previous Versions
## 以前的版本

- [Version 3](https://github.com/bmadcode/BMad-Method/tree/V3)
- [Version 2](https://github.com/bmadcode/BMad-Method/tree/V2)
- [Version 1](https://github.com/bmadcode/BMad-Method/tree/V1)

## Current Version: V4 - Alpha
## 当前版本：V4 - Alpha

Guiding Principles of V4:

V4 的指导原则：

- Simple to understand, install and start using

  易于理解、安装和开始使用
- Support Greenfield and Brownfield Scenarios

  支持绿地和棕地场景
- Greater configurability and more scenarios for usage - but kept out of the main package to maintain simplicity

  更高的可配置性和更多的使用场景 - 但为了保持简单性而未包含在主包中
- Helpers for installers and web builders that will work with any OS and IDE easily

  为安装程序和 Web 构建器提供助手，可轻松与任何操作系统和 IDE 配合使用
- Align all agents to be the same for IDE and Web, without losing the power of the web versions, or the leanness of the files in the IDE to reduce context

  使 IDE 和 Web 的所有代理保持一致，而不会失去 Web 版本的强大功能，或 IDE 中文件的精简性以减少上下文
- Further improvements to the two most important agents - the SM and DEV

  对两个最重要的代理——SM 和 DEV——进行进一步改进

## V3

With the customizability of V2, there were still some issues. A PM could only easily do one thing, create a PRD. And maintaining the consistency between Web and IDE agents was a pain.

尽管 V2 具有可定制性，但仍存在一些问题。项目经理（PM）只能轻松地做一件事，即创建产品需求文档（PRD）。而且，在 Web 和 IDE 代理之间保持一致性是一件痛苦的事情。

V3 didn't fix the disconnect, but it did make it easier to maintain them all in a single folder, but there were only two official ide agents - all the rest were really made and optimized for the web.

V3 没有解决脱节的问题，但它确实使在单个文件夹中维护所有内容变得更容易，但只有两个官方的 IDE 代理——其余的都是为 Web 制作和优化的。

V3's biggest impact was a full explosion of customizability. Tasks, Personas, Agent Configurations, Doc Templates, data payloads.

V3 最大的影响是可定制性的全面爆发。任务、角色、代理配置、文档模板、数据有效负载。

BUT - the BIGGEST change was the realization that we were barely scratching the surface of what could be loaded into Gemini Gems and still have very long chats. The BMad AGENT arose, and with a single V3 release - the future of the BMad Method was changed forever.

但是——最大的变化是意识到我们仅仅触及了可以加载到 Gemini Gems 中并仍然进行非常长时间聊天的内容的表面。BMad 代理应运而生，随着 V3 的一次发布——BMad 方法的未来被永远改变了。

Now, instead of configuring 4+ web agents, all needing many files uploaded to create them, a single Agent called BMad, with a whole team, and the ability to switch and maintain personas evolved. Now you could in the same chat thread, talk to the whole team, or anyone on the team. No more exporting and reimporting docs to different chats - all of the sudden, you could finish the PRD, and ask Josh to pass it off to the Architect, and that was it, the architect just had it and we moved on! And all of that with just 7 total files to upload, delivering all power.

现在，不再需要配置 4 个以上的 Web 代理，所有这些代理都需要上传许多文件来创建它们，一个名为 BMad 的单一代理，拥有整个团队，并且能够切换和维护角色。现在，您可以在同一个聊天线程中与整个团队或团队中的任何人交谈。不再需要将文档导出和重新导入到不同的聊天中——突然之间，您可以完成 PRD，并要求 Josh 将其交给架构师，就这样，架构师就拥有了它，我们继续前进！而所有这一切只需上传总共 7 个文件，即可提供所有功能。

But V3 had a major flaw - with massive configuration comes massive complexity - and in some ways, V3 started to get away from core principles - power through simplicity. The core system needs to do one thing well and be solid, and not stretch too thing with every possible thing.

但 V3 有一个主要缺陷——巨大的配置带来了巨大的复杂性——在某些方面，V3 开始偏离核心原则——通过简单实现强大。核心系统需要做好一件事并保持稳固，而不是用所有可能的事情来过度扩展。

Also - while the dev is amazing and better in V3 than all the past, along with the SM - the dev started over documenting every step and really started to bloat stories with their own notes. And the SM was forgetting to add details to stories, or embellishing information. This was fixed somewhat in V3.1 - but the dev is still over explaining everything it does, instead of just capturing the changes to the story.

此外——虽然 V3 中的开发人员（dev）和 Scrum Master（SM）比过去都更出色——但开发人员开始过度记录每一步，并真正开始用自己的笔记来臃肿故事。而 SM 则忘记向故事中添加细节，或者粉饰信息。这在 V3.1 中有所修复——但开发人员仍然过度解释他所做的一切，而不是仅仅捕获对故事的更改。

## V2

After V1 proved that the BMad method was solid and repeatable, 2 key ideas emerged. Separation of concerns, and building for the web made easier. By separating out templates - it was now much easier for the PRD fields to be customized, or the architecture.

在 V1 证明 BMad 方法是可靠且可重复的之后，出现了两个关键思想。关注点分离，以及让为 Web 构建变得更容易。通过分离出模板——现在定制 PRD 字段或架构变得容易得多。

And the introduction that really supercharged everything in my opinion, the web versions! There were 4 hard coded web variants hand crafted - and we saw that we could, dirt cheap, work with agents for hours in the massive context of Gemini - from a PRD generating PM, through to an architect and even an analyst that could help us do extensive market research and brain storming.

在我看来，真正让一切都变得超级强大的介绍是 Web 版本！有 4 个手工制作的硬编码 Web 变体——我们看到，我们可以以极低的成本，在 Gemini 的巨大上下文中与代理工作数小时——从生成 PRD 的项目经理，到架构师，甚至是可以帮助我们进行广泛市场研究和头脑风暴的分析师。

What I never expected is the names would stick, and people would keep the sample names I made that I thought people would configure. But now 4 version is, people refer to Mary, and John, and Bob! And when I randomly changed the names, I got A LOT of feedback! These have become trusted allies people are relying on, including for me!

我从未想到的是，这些名字会保留下来，人们会保留我制作的我以为人们会配置的示例名称。但现在已经是第 4 个版本了，人们仍然会提到 Mary、John 和 Bob！当我随机更改名字时，我收到了很多反馈！这些已经成为人们（包括我）所依赖的值得信赖的盟友！

## V1

Believe it or not (well you can view the link), V1 was a simple 7 file system! 7 Core agents working in harmony to help build a pretty specific type of application. But it showed its power and adaptability.

信不信由你（好吧，你可以查看链接），V1 是一个简单的 7 文件系统！7 个核心代理协同工作，帮助构建一种非常特定类型的应用程序。但它展示了其力量和适应性。

Meant to be a simple Tech Demo showing how custom agents with agile personas can help streamline your project, and create rails for your dev agents that to that point had gone unmatched - while also putting a focus on the planning phases - the project sparked the imagination of many, and a seed of a potential was realized.

旨在作为一个简单的技术演示，展示具有敏捷角色的自定义代理如何帮助简化您的项目，并为您的开发代理创建迄今为止无与伦比的轨道——同时还关注规划阶段——该项目激发了许多人的想象力，并实现了潜力的种子。
