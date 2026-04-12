---
title: "FE Bits Vol.31 | axios 供应链攻击、JetStream 3.0 发布与视图过渡工具包"
link: weekly-31
description: axios 供应链攻击始末与防护建议、JetStream 3.0 跨浏览器基准测试发布、Babylon.js 9.0、CSS contain/shape()/subgrid 等新特性文章合集。
date: 2026-04-12 18:40:31
categories:
  - 周刊
updated: 2026-04-12 19:20:22
---

+++primary 关于本周刊

> 本期网址 <https://blog.cosine.ren/post/weekly-31>
> 本周刊更新时间期望是在每周天。
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe)

本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。
+++

今天是 2026 年 4 月 12 日，星期日。
这期是带着清明放假的内容的双周刊。

## 个人动态

### 游戏

写点游戏杂谈。电子 ed 有一阵子了，但是清明放假连着两天 12 个小时，推完了哀鸿全结局，当作视觉小说读完了一个故事的感觉。

是玩过前作来继续玩的，我的评价挺好的说实话。林翩翩的塑造给我感觉确实比苏怜烟惊艳，让人印象深刻。

让我评价的话，这个作品是历史向大众向的 AVG 而不是 galgame，也确实不是冲着 gal 去宣传的，所以对我来说没啥雷点，前作的各种糖也是吃饱了。

先说一些实际游玩下来的优点：

1. 音乐无可挑剔，画面 CG 量还挺大的，画风我比较喜欢。
2. 历史观上真得很棒，尽可能客观的体现了扬州十日事件里面各方的行为，人本来就是矛盾的集合体，花街柳巷青楼那几处的介绍真的很沉浸，最后通往不同结局的时候，也藏着很多历史文学彩蛋，有金圣叹、钱谦益、郑成功、柳泉居士、朱慈炯等
3. 剧情本身我觉得是很连贯的，成功的讲述了扬州十日，圆了各种伏笔。
4. 音乐和画面配合得非常好，恰到好处，看林翩翩真结局的时候给我看哭了。

缺点：
1. 女一的塑造说实话我个人感觉没有女二好，说起来这游戏其实不太能用女一女二区分，两个角色显然是故意塑造的正相反的感觉。无论哪个真结局都不能算世俗意义上的好结局，纯发刀来的，但是番外的良田满穂前作糖多少弥补了这点……个人也不喜欢渐冻症这个设定，真是败笔。
2. 你一个视觉小说怎么还有一命通关的成就（吐槽）何意味 x
3. 死结局太多了而且一大部分都是小雁子的“知宥——知宥——”，++要听 PTSD 了++{.dot}

引用知乎回答看到的一段话，让我觉得很认同，这游戏的男主确实是这样的感觉：

> 从实际来讲，男主本来就是一个很典型的精神病患者。\
> 存在他回忆中的“女主角”，是苏连雁，他爱着她记忆的全部，毕竟在回忆里，关于翩翩的一切都是黯淡的，次要的。\
> 而在现实中的“女主角”，是林翩翩，她爱着他现实中的全部，毕竟在现实里，关于连雁的一切都是想象的，虚幻的。

参考[知乎回答 1](https://www.zhihu.com/question/2023480658371028619/answer/2023846631921984553)、[知乎回答 2](https://www.zhihu.com/question/2023480658371028619/answer/2023806352355533786)

最后，附张图，表达个人心情。

等待并心怀……

![等待并心怀……](https://r2.cosine.ren/2026/04-05-dr87ym6g.jpg)

### 杂七杂八的碎碎念

- 博客迁移与更新：随着流量增长，把本博客从 Vercel 迁移至云服务器了，发布了 [astro-koharu v3.3.0](https://github.com/cosZone/astro-koharu/releases/tag/v3.3.0) 版本，修复了歌单问题。（昨晚发了 [v4.0.0](https://github.com/cosZone/astro-koharu/releases/tag/v4.0.0) 把咕咕咕已久的 umami 访问量显示之类的也加上了）

- 坐在桌前打游戏时候的左右护法（笑死）每个机箱都暖暖的，猫老喜欢了。

![](https://r2.cosine.ren/2026/04-11-79v1z9h1.jpg)
![](https://r2.cosine.ren/i/2026/04/b439571a1c78975ac8352f698268022d.webp)

- [MoePeek 新增 TTS 朗读功能](https://github.com/cosZone/MoePeek/releases/tag/v0.13.0)：为 MoePeek 新增了翻译结果/原文的 TTS 朗读功能，方便学习日语 x

![](https://r2.cosine.ren/2026/03-31-qxk8telr.jpg)

## 社区动态

- [JetStream 3.0 发布](https://browserbench.org/announcements/jetstream3/)：跨浏览器 JS/WASM 基准测试（Benchmark）时隔七年迎来大版本更新，由 Mozilla、WebKit 和 Chromium 联合开发。

- [Babylon.js 9.0 版本发布](https://blogs.windows.com/windowsdeveloper/2026/03/26/announcing-babylon-js-9-0/)：Babylon.js 发布 9.0 版本，引入集群光照、帧图系统及节点粒子编辑器等高性能渲染特性。

- [视图过渡工具包](https://www.bram.us/2026/04/02/view-transitions-toolkit/)：Bramus 发布 view-transitions-toolkit，提供一系列简化视图过渡（View Transitions）开发的实用函数和助手。

- [axios 遭遇供应链攻击](https://x.com/i/status/2038807290422370479)：npm 流行包 axios@1.14.1 被发现包含恶意依赖项，面临供应链攻击风险。
恶意负载[位置](https://socket.dev/npm/package/plain-crypto-js/files/4.2.1/setup.js)，虽然现在已经恢复很久了，但还是建议阅读 pnpm 的[这篇文章](https://pnpm.io/supply-chain-security)进行一些额外的预防，如开启 minimumReleaseAge 等，而且 pnpm 默认是禁止 postinstall 的。

- [Our response to the Axios developer tool compromise](https://openai.com/index/axios-developer-tool-compromise/)：与此同时 OpenAI 披露其 macOS 应用签名流程中使用的第三方库 Axios 遭遇供应链攻击（版本 1.14.1 含有恶意负载）。虽然目前无证据表明用户数据或源码被泄露，但出于防范，OpenAI 已撤销并更换了 macOS 代码签名证书 (Code Signing Certificate)。受影响的应用包括 ChatGPT Desktop 和 Codex 等，所有 macOS 用户需在 2026 年 5 月 8 日前完成更新，届时旧版应用将失效。 

## 文章

- [What To Know in JavaScript (2026 Edition)](https://frontendmasters.com/blog/what-to-know-in-javascript-2026-edition/)：一篇文章带你速览 2026 年 JavaScript 语言特性、框架生态、运行时及构建工具的最新演进与趋势。

- [How AI Remembers and Why It Forgets: Part 1. The Context Problem](https://www.developerway.com/posts/how-ai-remembers-and-forgets-part1)：介绍大语言模型（LLM）如何通过上下文（Context）模拟记忆，以及为何大量信息会导致“上下文腐烂”（Context Rot）现象。

- [SVG Filters Guide: Getting Started with the Basics](https://frontendmasters.com/blog/svg-filters-guide-getting-started-with-the-basics/)：一篇文章带你从逻辑和数学角度快速掌握 SVG 滤镜的基础构造与核心原理。

- [构建开源职业生涯](https://st0012.dev/zh-tw/building-a-career-with-open-source/)：一篇关于如何通过开源构建职业生涯的优质文章，并附带个人感悟。

- [深入探讨 CSS contain 属性及其性能优化](https://csswizardry.com/2026/04/what-is-css-containment-and-how-can-i-use-it/)：深入探讨 CSS contain 属性，说明如何通过隔离 DOM 子树来显著提升浏览器的渲染性能。

- [JavaScript 预加载图像的多种方法](https://macarthur.me/posts/preloading-images/)：探讨在 JavaScript 中预加载图像的多种方法及其优缺点，解决图像渲染时的延迟与闪烁问题。

- [使用 CSS shape() 函数创建复杂图形](https://css-tricks.com/complex-css-shapes-with-shape-function/)：本文介绍如何利用 CSS 新增的 shape() 函数创建复杂的波浪线、不规则图形和边框，替代传统 SVG 方案。

- [CSS 六边形头像的实现与蜂巢布局](https://www.zhangxinxu.com/wordpress/2026/04/css-pyramidal-grid/)：本文主要介绍了如何利用现代 CSS 新特性实现六边形头像效果以及高度自动化的金字塔蜂巢网格布局。

- [CSS subgrid is super good](https://dbushell.com/2026/04/02/css-subgrid-is-super-good/)：探讨如何利用 CSS Subgrid (子网格) 轻松解决 CMS 内容中常见的“全宽背景”与“居中对齐”布局难题。

- [The uphill climb of making diff lines performant](https://github.blog/engineering/architecture-optimization/the-uphill-climb-of-making-diff-lines-performant/)：GitHub 工程团队详细介绍了如何通过重构 React 架构、减少 DOM 节点及引入虚拟滚动技术，显著提升大规模 Pull Request 在渲染和交互上的性能表现。

## 趣站与工具

- [Bearnie 组件库](https://bearnie.dev/)：基于 Astro 和 Tailwind CSS 且严格遵循 WCAG 2.1 AA 标准的无障碍组件。

- [textstring](http://pushmatrix.github.io/textstring/)：一个极具创意的 demo，将代码中的 string（字符串）具象化为物理世界中可拉伸、缠绕的“细绳”。

![](https://r2.cosine.ren/2026/03-31-n7kqas5b.jpg)

- [纯 CSS 渲染 3D 版《毁灭战士》](https://nielsleenheer.com/articles/2026/css-is-doomed-rendering-doom-in-3d-with-css/)：一篇优质博文，详细介绍了如何利用现代 CSS 特性实现 3D 版《毁灭战士》的渲染，挑战 CSS 能力边界。

![](https://r2.cosine.ren/2026/04-02-iupdi8wb.jpg)

- [dany.works](https://dany.works/)：一个设计优雅的个人网站，里面的 Sunny Mode 阳光模式十分好看

![](https://r2.cosine.ren/2026/04-02-6fk8ccd5.jpg)

### Hypercube 粒子超立方体

https://codepen.io/jkantner/pen/YPGrodj

> Jon Kantner 从动态图形设计传奇人物 Dave Whyte 的 [gif](https://x.com/beesandbombs/status/1508921246238531585) 中汲取灵感，创作了这个 JavaScript 超立方体形状的粒子动画，它在 CodePen 上看起来非常合适。

![](https://r2.cosine.ren/i/2026/04/549bc3463ce6f4e0b94d8b2ac84d8473.webp)

### reorder cards 重新排列卡片

https://codepen.io/vii120/pen/WbGXVLG

> Vivi Tseng 重现了 Mollie Starr 在 Dribbble 上发布的[设计作品](https://dribbble.com/shots/8218979-Let-me-give-you-my-card)，为这个响应式拖放卡片演示增添了阳光与阴影效果。

![](https://r2.cosine.ren/i/2026/04/b610a75ee363a142ba1b2812af22ae34.webp)

### box flow system 箱流系统

https://codepen.io/Ma5a/pen/yyaXzoB

> “工厂自动化有种令人着迷的魅力，因此我想创作一些受此启发的作品。挑战在于如何让箱子之间、箱子与传送带及气动管道之间以不同方式互动。”—— 来自 Masahito Leo Takeuchi

![](https://r2.cosine.ren/i/2026/04/ec454987a1c987dfe6f32da97c9e01b5.webp)

## Refs

- [Frontend Focus #736](https://frontendfoc.us/issues/736)
- [CodePen Spark #503](https://codepen.io/spark/503)
