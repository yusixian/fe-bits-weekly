---
title: FE Bits Vol.23 | jQuery 4 发布，Chrome 新增垂直标签页功能，Astro 被 Cloudflare 收购
link: weekly-23
description: 本期周刊：jQuery 4.0.0 时隔十年正式发布，带来全面现代化改进；Chrome 145 终于实验性支持垂直标签页；Astro 团队加入 Cloudflare，继续专注框架核心开发；Vercel 发布 React 最佳实践规则集，助力 AI 编写更优代码；另有 V8 性能实测、Markdown 演化史与「告别 Scroll Fade」等精彩阅读推荐。
lang: cn
date: 2026-01-18 21:50:00
categories:
  - 周刊
---

> 本期网址 https://blog.cosine.ren/post/weekly-23 \
> 本周刊更新时间期望是在每周天。 \
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。\
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。\
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe) \
> 本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。

今天是 2025 年 1 月 18 日，星期天。

Moe Copy AI 发了 [v0.2.1](https://github.com/yusixian/moe-copy-ai/releases/tag/0.2.1) 和 [v0.2.2](https://github.com/yusixian/moe-copy-ai/releases/tag/0.2.2)，做了国际化，将悬浮球的功能抽取至侧边栏单页抓取 tab 了，内容提取下也加了 AI 总结按钮。

感谢 [@XueHua-s](https://github.com/XueHua-s) 贡献的 htmlToMarkdown 重构为使用 unifined 改进～（[#19](https://github.com/yusixian/moe-copy-ai/pull/19)）

然后是 astro-koharu 主题，将周刊功能泛化为了多系列，featuredSeries 支持数组与自定义 slug，动态生成系列页面并替代固定 `/weekly` 了，现在可以新增以下如图所示的系列文章了。

![](https://r2.cosine.ren/i/2026/01/9caacaeaa2c22fc74e2aeb5b95513350.webp)
![](https://r2.cosine.ren/i/2026/01/1e44232d7b78a496bd12c54320442b6c.webp)

并且评论组件现在支持切换三种评论组件了（waline / remark42 / giscus）

开心！Waline 做评论真是又好看又好用啊

![](https://r2.cosine.ren/i/2026/01/0fcd4666e5e8a0b2abb0ee517bf26166.webp)

这周都在肝项目，所以周刊短短的！

## 社区动态

- [jQuery 4.0.0](https://blog.jquery.com/2026/01/17/jquery-4-0-0/)：时隔近十年，jQuery 发布了 4.0.0 正式版，带来了大量现代化改进，包括移除对旧版浏览器（IE 10 及更早版本）的支持、引入新特性以及优化内部实现。
- [Chrome 145 adds Experimental Support for Vertical Tabs](https://www.bram.us/2026/01/16/chrome-145-adds-experimental-support-for-vertical-tabs/)：Chrome 145 实验性支持垂直标签页。（天呐 2026 了 Chrome 终于把垂直标签页学过来了太感动了）
- [隆重推出：React 最佳实践](https://vercel.com/blog/introducing-react-best-practices)：Vercel 团队将 _“十余年 React 和 Next.js 优化经验”_ 提炼成了[一套 Markdown 文件](https://github.com/vercel-labs/agent-skills/tree/main/skills/react-best-practices/rules)， 旨在供 Claude Code 等代码助手使用，当然您也可以自行阅读。其目标是帮助这些助手编写更优质的 React 代码，而无需过多指导。
  - 可以通过 `npx add-skill vercel-labs/agent-skills` 直接安装
- [The Astro Technology Company joins Cloudflare | Astro](https://astro.build/blog/joining-cloudflare/)：Astro 框架背后的公司 The Astro Technology Company 宣布加入 Cloudflare，以获取更多资源并专注于框架核心开发，承诺保持开源和平台中立。（真好，我很喜欢 astro 写网站的感觉）
  - 并且 [Astro 回顾了过去一年](https://astro.build/blog/year-in-review-2025/)，展望了 2025 年的更新、变化和新增功能吗，并且[发布了 Astro 6 的 beta 版本。](https://astro.build/blog/astro-6-beta/)

- ["You should never build a CMS" | Sanity](https://www.sanity.io/blog/you-should-never-build-a-cms?ref=ww-rss)：Sanity 回应 Cursor 将 CMS 迁移至 Markdown 的热议，分享了许多使用 CMS 的理由。

## 文章与社区动态

- [Why I hate WebKit, a (non) love letter](https://gethopp.app/blog/hate-webkit)：非常好文章推一下，Tauri WebKit 坑点大全，珍爱生命远离 WebKit！这个标题和 url 真是直抒胸臆。

- [JavaScript 的 for-of 循环实际上很快 (V8)](https://waspdev.com/articles/2026-01-01/javascript-for-of-loops-are-actually-fast)：探讨现代 V8 引擎中 `for-of` 循环的性能表现，打破了开发者社区中关于其性能显著弱于传统循环的固有印象。作者建议现在除非是处理极端海量数据且对每一毫秒都敏感的场景，否则应优先使用语义更佳的 `for-of` 循环。

- [GUIDs - How I messed up my RSS feed](https://theorangeone.net/posts/rss-guids/)：这篇文章讲述了作者如何因在 RSS feed 中添加 UTM 参数导致所有文章被重复添加，并介绍了 GUID 字段来解决此类问题的经验。

- [记 LobeHub 的性能和 DX 优化](https://innei.in/posts/tech/lobehub-performance-dx-optimization)：作者分享了入职 LobeHub 一个月以来在性能和开发体验（DX）方面进行的优化工作。

- [《简明 TypeScript 手册》](https://github.com/gibbok/typescript-book) 是一本简短精炼的 TypeScript 指南，免费开放阅读。

- [How to Steal Any React Component](https://fant.io/react/)
  网页做的还挺有趣的，介绍如何使用 React 的内部数据结构（通过 [Fiber](https://github.com/acdlite/react-fiber-architecture)）和 LLM 来重建生产 React 应用程序中的组件，而无需原始源代码。

- [How Markdown took over the world](https://www.anildash.com/2026/01/09/how-markdown-took-over-the-world/)：回顾 Markdown 的诞生历程及其如何从一个小众博客工具演变为统治现代互联网和 AI 交互的通用文本标准。

- [Death to Scroll Fade!](https://dbushell.com/2026/01/09/death-to-scroll-fade/) 批判网页设计中过度使用“滚动渐入”（Scroll Fade）效果的弊端，呼吁回归简洁高效的用户体验。

- [useOptimistic Won't Save You](https://www.columkelly.com/blog/use-optimistic)：深入探讨 React 19 的 useOptimistic 钩子，说明其必须结合 Transition 和 Action 状态管理才能真正处理复杂的竞态条件。
  作者最后建议，这些复杂的底层 API 更多是为框架开发者设计的，普通开发者应倾向于使用成熟框架提供的抽象。

- [如何衡量和优化 React 性能](https://www.debugbear.com/blog/measuring-react-app-performance)：全面介绍了衡量和优化 React 应用性能的工具与技术，重点讲解了 React 19.2 的新特性以及各类运行时和构建时的优化策略。

- [停止将所有内容都变成数组（并减少工作量）](https://allthingssmitty.com/2026/01/12/stop-turning-everything-into-arrays-and-do-less-work-instead/)：介绍如何利用 JavaScript 原生的迭代器辅助函数（Iterator helpers）实现延迟计算，从而优化处理大数据集时的性能和内存占用。

## 新特性

- [Bytes I can delete after all this time](https://remysharp.com/2026/01/13/bytes-i-can-delete-after-all-this-time)
  由于 CSS 和 JS 的进步，越来越多的技术我们不再需要了，Remy Sharp 分享了一份我们可以抛弃的技术清单。

1. CSS 布局与样式增强
   - 使用 `text-underline-offset` 属性轻松控制文本下划线的距离，无需再用复杂的伪元素模拟。
   - 在 Flexbox 布局中直接使用 `gap` 属性，告别过去需要通过处理 `margin` (外边距) 来设置间距的繁琐操作。
   - 采用原生 CSS 嵌套 (Nesting) 和在选择器内嵌套媒体查询 (Media Queries)，使样式结构更清晰且无需预处理器。
   - 利用 `clamp(min, variable, max)` 实现流体响应式尺寸，简化了复杂的断点计算。
   - 使用 `content: open-quote` 结合 `q` 标签实现根据语言自动适配的本地化引号。

2. JavaScript 语法与交互优化
   - 采用可选的 `catch` 绑定 (Optional catch binding)，在不需要错误对象时直接写 `catch { ... }`，避免定义未使用的变量。
   - 指针事件 (Pointer Events) 的普及使得开发者可以用一套逻辑替代旧有的 `click` (点击) 和 `touch` (触摸) 事件的混合逻辑。
   - 弃用旧的性能黑科技，如使用 `~~` 或 `| 0` 取整，现代引擎下 `Math.floor()` 的可读性更高且性能不再是瓶颈。

3. 资源优化与现代格式
   - AVIF 图像格式已获得全面支持，相比 JPEG 可轻松实现 50% 以上的体积缩减。
   - 提供了使用命令行工具 `avifenc` 批量转换图片的实用脚本示例。

然后是两篇锚点定位，都是自动连线：

- [Connecting Circles With Anchor Positioning II](https://css-tip.com/connected-circles-2/)：CSS Tips 锚点定位系列文章，通过改进之前的实现，展示了如何使用 CSS 锚点定位技术动态连接两个圆圈，并在连接箭头的形状中计算并显示它们之间的距离。
- [纯 CSS 实现两个元素之间折线自动相连](https://www.zhangxinxu.com/wordpress/2026/01/css-anchor-position-connect/)：本文详细介绍了如何利用 CSS 锚点定位实现两个元素之间纯 CSS 自动连接的折线效果，并探讨了当前方案的实现原理及局限性。

## 趣站与 Codepen 精选

[Playing With CodePen slideVars](https://css-tricks.com/playing-with-codepen-slidevars/)：介绍 CodePen 官方推出的 slideVars 工具，它可以自动检测 CSS 变量并生成交互式控制面板，现在在 codepen 里写交互式 Demo 更方便了。

https://codepen.io/geoffgraham/pen/myEOqJg

![](https://r2.cosine.ren/i/2026/01/86fef9a9ebcbbd142278ebb09cb030f2.webp)

## Refs

- [JavaScript Weekly #768](https://javascriptweekly.com/issues/768)
- [React Status #458](https://react.statuscode.com/issues/458)
