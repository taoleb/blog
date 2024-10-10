---
layout: post
title:  "全方位超越 Sora ，Meta 最新的 AI 视频模型"
author: jane
categories: [ 人工智能 , 新闻 ]
image: assets/images/meta.jpg
tags: [summer]
---
这两天，视频生成模型领域因为 Meta Movie Gen 的发布，又炸开了锅。
行业内外感叹最多的地方，无外乎两点，一是生成效果自然逼真，还能同步生成与画面匹配的声音，很像当时 Sora 发布后引起的讨论和轰动；二是 Meta AI 的新模型自定义性很强，无论是视频画面比例，还是视频元素与细节，都能根据用户的需求进行调 整。

所以，可能会引领视频生成新变革的 Meta Movie Gen 到底有哪些细节？这些在官网和演示视频里的惊艳效果是怎么炼成的？Meta AI 的视频模型负责人 Andrew Brown 专门为 Meta Movie Gen 的理论技术做了解读：

Movie Gen 在整体质量和一致性方面显著优于 Sora。真实性和美观性考验照片写实性，Movie Gen 全面获胜。

Meta Movie Gen 是一组可以进行文本到视频生成、文本到图像生成、个性化、编辑和视频到音频生成的模型。

扩展数据、计算和模型参数非常重要，将其与流匹配相结合，并转向简单的常用 LLM 架构 (Llama)，从而实现了 SOTA 视频生成质量。

我们（Meta AI）是第一个使用 Llama arch 进行媒体生成的人。

Movie Gen 是一个 30B 参数转换器，可生成不同宽高比和同步音频的 1080p 视频，最大持续时间为 16 秒（16fps）。

我们（Meta）为 T2V 模型提供了多阶段训练方案。T2I + T2V 联合训练，导致收敛速度慢得多且质量更差。

文本到视频的评估很困难。自动化指标非常差，并且与人类评估没有很好的相关性。
视频生成的「超级个体」
Meta Movie Gen 首发当天，APPSO 在第一时间报道解读了这个最新的视频生成模型，总体来说，Movie Gen 具有四种功能：视频生成、个性化视频生成、精准编辑和音频生成。
先看最基础的视频生成 Movie Gen Video，多模态的能力使得新模型可以胜任多种不同的输入方式，用户不仅可以通过简单的文本、少许提示词生成相应的视频，还能直接把需要处理的图片放到模型里，根据文字要求，让静态的图片变成动态的视频。
提示文本：一个女孩正在海滩上奔跑，手里拿着一只风筝；她穿着牛仔短裤和一件黄色 T 恤；阳光照耀着她。

你甚至还能让 Movie Gen 帮忙重新生成或者优化一段视频。不管选择哪种输入方式，Movie Gen 目前在官网的演示视频，效果都非常好，人物表情自然，画面细节到位，也能比较准确地按照提示词或文本的要求来生成相应结果。


Andrew Brown 介绍到，在视频生成的过程中，扩展数据、计算和模型参数非常重要，将其与流匹配相结合，并转向简单的常用 LLM 架构 (Llama)，从而实现了 SOTA 视频生成质量。
而且，新模型中的 T2V、个性化和编辑模型都来自相同的培训方案。在预训练期间，Meta 首先训练 T2I，然后训练 T2V。使用该模型作为初始化，然后进行 T2V 后期训练，并训练个性化 T2V 和 V2V 编辑的能力。
图片
另外，模型的训练也按照分辨率的高低进行，先是低分辨率（256px）训练，然后是高分辨率训练（768px）。Meta AI 尝试联合训练 T2I + T2V，但这导致收敛速度慢得多且质量比之前的还要差劲。
图片
Movie Gen Video 之所以能够做到逼真的生成结果，本质上还是因为高达 30B 参数转换器模型的卓越能力，这个模型能够以每秒 16 帧的速度生成长达 16 秒的视频，而且最长能够生成 45 秒的高质量和高保真音频。
Meta 官方还在论文中透露：
这些模型可以推理物体运动、主体与物体之间的相互作用和相机运动，并且可以学习各种概念的合理运动。
这句话一共有三层意思，首先是模型本身可以几乎还原出现实世界的物理运动，以及各种「合乎常理」的物理规律，而对于用户而言，看上去「自然且逼真」就是模型技术最成功的地方。

Movie Gen Video 能够准确理解物理世界的运动规律，Meta AI 是下了大功夫的。该团队在数亿个视频和数十亿张图像上，对全新的模型进行了大量的预训练。通过不停的重复、学习、总结、推理和运用，Movie Gen Video 才有了在官网里的优异表现。
接着，模型还能主动模仿学习专业电影的运镜、画面、蒙太奇等。也就是说，通过 Movie Gen Video 生成的视频，还有了类似电影拍摄的专业性和艺术性。


不过 Andrew Brown 提到，文本到视频的评估很困难。因为自动化指标非常差，并且与人类评估没有很好的相关性。也就是说，在视频生成模型研制的早期，生成结果和人们印象中和观察中的真实物理世界差别太大，最后 Meta 还是决定这种真实性的判断，完全依赖人类的评估。
我们花费了大量精力将视频评估分解为多个正交质量和对齐轴。
结果 Movie Gen 在和 1000 个提示评估集上的模型进行比较时，在质量和一致性方面获胜或全面处于同等水平。
图片
最后，模型能在此基础上，推理和创作出接下来的内容，它就像一个专业的导演，指挥着画面里的一举一动；也像一个经验丰富的拟声师，根据视频内容或者文本提示，实时生成和画面一一对应的配乐。

烟花爆炸瞬间的音效
同步生成音频的能力，依靠得是 Movie Gen Audio。这是一个 13B 参数转换器模型，可以接受视频输入以及可选的文本提示，以实现可控性生成与视频同步的高保真音频。


和 Movie Gen Video 一样， Movie Gen Audio 也进行了「海量」练习，Meta AI 将数百万个小时的音频参考投喂到模型的训练里。经过大量的对比总结，目前模型已经掌握了声音和画面之间的对应关系，甚至还能了解不同的 bgm 会带给观众哪些不同的感受。
因此在遇到有关情绪和环境的提示词时，Movie Gen Audio 总能找到和画面完美契合的音乐。
同时，它可以生成环境声音、乐器背景音乐和拟音声音，在音频质量、视频到音频对齐和文本到音频对齐方面提供最先进的结果。
这使它们成为同类中最先进的模型。
虽然我们不敢就此和官方一样，下一个如此自信的定论，但无论是从官方的视频长度、画面质量，还是背景音乐的贴合程度，Movie Gen Video 相较于以往的视频生成模型，有了非常明显的进步。
而且，和先前的偶像实力派 Sora 相比，Movie Gen 在整体质量和一致性方面都有着比较明显的领先，Andrew Brown 毫不掩饰地说到在这场与 Sora 的比赛中：
Movie Gen 全面获胜。
视频编辑的「全能专家」
在 Movie Gen Video 和 Movie Gen Audio 的协同配合下面，Meta AI 全新的视频生成模型有了全新的能力，不过上述的进步还只是技术基础，同时具备音视频生成能力后，Meta 还继续扩展了全新模型的适用范围，使它能够支持个性化视频的生成。
个性化顾名思义，就是结合用户需求，根据要求生成指定的视频内容。
虽说先前的视频模型也能做到个性化生成结果，但这个结果总是不尽人意，要么是不能更改细节，只能重新来过，要么是在连续更改细节时，画面里的其他元素无法保持一致性，总是会因为新视频的生成而多少受到点影响。


Movie Gen Video 在官网的演示中，很好地展现了他们在这方面的优势。新模型不仅可以按照提示词/参考图像的要求，生成个性化的视频，还能在该视频的基础上，继续优化调整细节，并且保证其他的生成内容不受干扰，也就是「精细化修改」。
与需要专业技能或缺乏精确度的生成工具的传统工具不同，Movie Gen 保留了原始内容，仅针对相关像素。
在创建保留人类身份和动作的个性化视频方面，我们的模型取得了最先进的成果。
这项功能，对于很多自媒体工作室，或有视频编辑需求的人，非常有用，它可以对更改对象进行全局修改，或者细节修改。大到根据文本重新生成整个画面，小到只改变人物的发色、眼镜的样式等。比如可以通过模型来消除背景当中的无关杂物。


或者给原视频换上新的背景，不管是样式还是颜色，都能随时改变，而且还可以把白天秒变成黑夜。
另外 Movie Gen Video 还能针对很多细节做出细微的调整，在保证视频构图、画整体不变的同时，改变人物的衣服颜色、眼镜佩戴样式，主体穿着和宠物毛色等。
比如去除视频里的无关杂物、更换画面背景样式，增加视频细节，改变主体衣着颜色等方面，都是他的强项。
图片

不过这还只是一种畅想，因为 Movie Gen Video 目前只支持 1080P、16 秒、每秒 16 帧的高清长视频，或者最长 45 秒的高质量和高保真音频。这样的画面分辨率以及视频长度，对于一个有创作需求的个体或公司来说，好像都不太够用。
但这种技术的突破，使得 AI 拥有了对视频文件无级调节的编辑能力，个性化定制、精准调节，加上 Movie Gen Audio 打开了视频配音的大门，Movie Gen Video 虽然要等到明年才会和公众正式见面，但以目前官方的演示结果来看，它真有可能为视频、影视和 AI 行业注入新的动力，甚至带来一场新的变革。
包括 Movie Gen Video 在内的最新、最前沿的工具，正在试图打破这种 AI 在视频生成领域的刻板印象，虽然目前以他们的能力，这一天的到来还有很久。
对于视频生成模型来说，一开始很难直接影响，甚至触及到普通人的日常生活，直到有了某部由 AI 创作的电影，可能才会在新鲜感上，引起大众的注意。当下用 AI 做出的电影、番剧、动漫，多少都有些画面不真实、动作很违和的缺点。
图片

Meta AI 也在官网表示，随着模型技术的改善与发展，他们将会与电影制作人和创作者密切合作，整合他们的反馈。当下，无论是 Runway、Sora，还是最新的 Meta AI，都在飞速发展，起码和一年前的生成效果比较起来，可以看到肉眼可见的进步。
AI 技术对人们生活的影响，不一定会在第一时间显现出来，当大家还都在探讨 AI「有什么用」的时候，那它对于大多数人的最大意义，就是多了一个好用的工具、一个好玩儿的玩具：
无论一个人是希望在好莱坞大展身手的电影制作人，还是喜欢为观众制作视频的创作者，我们都相信每个人都应该有机会使用有助于提高创造力的工具。

<p><iframe style="width:100%;" height="315"  frameborder="0" allowfullscreen></iframe></p>