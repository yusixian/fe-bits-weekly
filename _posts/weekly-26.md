---
title: FE Bits Vol.26 | Gatsby 支持 React 19，Rspress 2.0 发布
link: weekly-26
lang: cn
date: 2026-02-09 00:42:38
categories:
  - 周刊
updated: 2026-02-09 00:42:38
---

> 本期网址 <https://blog.cosine.ren/post/weekly-26>\
> 本周刊更新时间期望是在每周天。\
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。\
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。\
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe)\
> 本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。

今天是 2026 年 2 月 8 日，星期天。

虽然发的有点晚，已经 0 点了。

就快要过年放假啦！愉悦地停更俩星期！

这周忙自己的项目很愉悦，给我的博客新增了以前的 shoka 语法兼容和[歌单](https://blog.cosine.ren/music)版块，全部可开关。

这周把心心念念的博客歌单和播放器加上了，并且添加了之前 Hexo Shoka 主题的 Markdown 扩展语法兼容支持，可在这里查看全部新增的语法演示：[Shoka 主题 Markdown 语法演示](https://koharu.cosine.ren/post/note/shoka-features)\
然后增加音乐播放器和歌单页面，都可以开关～\
一点一点变成我想要的样子了～

<https://github.com/cosZone/astro-koharu/releases/tag/v2.6.0>

所以……现在我要激情安利山山歌单了!

<https://blog.cosine.ren/music>

![BlockNote image](https://r2.cosine.ren/i/2026/02/a0cf89fcc829ca1804efd94da6d25e1b.webp)

并且这周给 Moe Copy AI v0.3.5 新增了完整的 Prompt Template 管理功能，支持预设模版和自定义模版。之前还添加了深色模式！（是的没错都是我自用的功能）

<https://moe.cosine.ren/docs/changelog>

![BlockNote image](https://r2.cosine.ren/i/2026/02/c9b63e5b248226dbd560969277b41f0a.webp)

## 社区动态

- GitHub 正在讨论开源项目维护者如何应对日益增加的低质量、AI 生成的拉取请求（PR），可能包括允许用户完全禁用 PR，或者至少限制 PR 只能由协作者访问等操作，可以在这里参加讨论：[Exploring Solutions to Tackle Low-Quality Contributions on GitHub](https://github.com/orgs/community/discussions/185387)

- [Gatsby v5.16](https://www.gatsbyjs.com/docs/reference/release-notes/v5.16/) 支持 React 19，[Rspress 2.0](https://rspress.rs/blog/rspress-v2) 重大升级

- [New to the web platform in January](https://web.dev/blog/web-platform-01-2026?hl=en)：汇总了 2026 年 1 月 Web 平台的重大进展，包括 Chrome 144 和 Firefox 147 稳定版的发布。其中 CSS 锚点定位 (CSS Anchor Positioning) 和 Navigation API 随着 Firefox 的支持，都正式达到 Baseline Newly Available（新可用基准）状态。此外，Chrome 144 引入了期待已久的 Temporal API、声明式的 `<geolocation>` 元素以及用于自定义页内搜索样式的 `::search-text` 伪元素

- [互联网档案馆发布插件，解决 40% 的互联网死链问题 - 小众软件](https://www.appinn.com/internet-archive-link-fixer/)：互联网档案馆（Internet Archive）推出了 WordPress 插件 Link Fixer，旨在解决互联网日益严重的“链接腐化”（Link Rot）问题。该插件通过自动检测失效的 URL（如 404 错误），并引导用户访问 Wayback Machine 中存储的历史网页快照，据称能修复约 40% 的死链。

### ViteLand 最新消息：2026 年 1 月回顾

<https://voidzero.dev/posts/whats-new-jan-2026>

#### 品牌与设计统一

- 实现了 VoidZero 旗下所有项目（Vite, Vitest, Rolldown, Oxc）的视觉身份统一，发布了全新的官网和 Logo。

- 更新了 Vite 的启动模板（Starter Templates），将新品牌标识内置其中。

- 强调了工具链的深度集成：Vite 8 在底层直接使用 Rolldown 和 Oxc，实现了一致的开发者体验。

#### 核心项目进展

- Vite：自 2020 年发布以来，累计下载量超过 30 亿次；React 服务端组件（React Server Components, RSC）插件进行了优化，以支持 TanStack Start 等框架。

- Vitest：启动 4.1 测试版（Beta），引入测试标签（Test Tags）功能，并支持通过禁用 viteModuleRunner 选项在脱离 Vite 的情况下运行。

- Rolldown：正式达成候选发布版（Release Candidate, RC）里程碑，API 进入稳定阶段；推出“Lazy Barrel Optimization”，在 AntDesign 等场景下可减少 92% 的模块编译，提速 2 倍。

- Oxc：Oxlint 支持 oxlint.config.ts 动态配置；Oxfmt 实现了与 Prettier 100% 的一致性（Conformance），并新增了 Tailwind CSS 类名排序功能。

#### 社区动态与生态

- 榜单表现：在 2025 JavaScript Rising Stars 榜单中，Vite、Oxc、Rolldown 和 tsdown 均名列前茅。

- 生态迁移：Hugging Face、Turborepo 和 Lichess 等知名项目宣布从 ESLint/Prettier 迁移至 Oxlint/Oxfmt。

- 周边工具：社区推出了基于 Oxc 的代码体积优化工具 jsshaker 以及 Oxlint 的终端用户界面工具 oxlint-tui。

## 文章

- [A Percise Parser](https://thedailywtf.com/articles/a-percise-parser)：本文介绍了一个因硬编码地区数值格式（Locale Formatting）并使用拙劣的字符串操作，导致国际化失效的 JavaScript 解析器（Parser）案例。

- [Solving Shrinkwrap: New Experimental Technique](https://kizu.dev/shrinkwrap-solution/)\
  好文，利用 CSS Anchor Positioning（锚点定位）和 Scroll-Driven Animations（滚动驱动动画）解决网页排版中“自动换行导致的容器宽度无法自动收缩（Shrinkwrap）”这一经典难题。

- [Performance-Optimized Video Embeds with Zero JavaScript](https://frontendmasters.com/blog/performance-optimized-video-embeds-with-zero-javascript/)：本文介绍了一种利用原生 HTML 标签 `<details>` 和 `<summary>` 来优化视频嵌入性能的方法。通过这种方案，开发者可以在完全不使用 JavaScript 的情况下实现视频的按需加载。

- [CSS @scope: An Alternative To Naming Conventions And Heavy Abstractions](https://www.smashingmagazine.com/2026/02/css-scope-alternative-naming-conventions/)：介绍如何利用 CSS 原生的 `@scope` 规则来替代复杂的 BEM 命名规范或繁重的 CSS 框架，实现更简洁、可维护的样式隔离。

- [CSS Bar Charts Using Modern Functions | CSS-Tricks](https://css-tricks.com/css-bar-charts-using-modern-functions/)：本文介绍了如何利用 CSS 现代函数 `sibling-index()` 和增强后的 `attr()` 函数，以更简洁、高效的方式构建纯 CSS 柱状图。

## 新特性

- [Nice Select · February 3, 2026](https://nerdy.dev/nice-select?utm_source=rss)：本文展示了如何利用最新的 CSS 特性（如 `appearance: base-select`）在保持原生无障碍性的同时，打造高度可定制且视觉华丽的 `<select>` 下拉组件。

<https://codepen.io/editor/argyleink/pen/019c1f28-bbc2-7bac-ad4a-a7e41d3730f1>

- [Drawing Connections with CSS Anchor Positioning - Roland Franke](https://rolandfranke.nl/frontend-stories/drawing-connections-with-css-anchor-positioning/)：锚点定位真好玩儿吧。在无需 JavaScript 的情况下实现 UI 元素（如评论与其回复）之间的视觉连线。

<https://codepen.io/ROL4ND909/pen/gbMxLdL>

## 工具

- [jamiepine/voicebox](https://github.com/jamiepine/voicebox) 一款由 Qwen3-TTS 驱动的开源、本地优先语音克隆与合成工具

## Codepen 与趣站

### 不规则网格上带有凹面圆角的卡片

<https://codepen.io/thebabydino/pen/WbxpKPQ>

> “卡片和按钮之间的缝隙实现了真正的透明效果。没有尖角，全部都是圆角。除了 .jpg 格式的卡片背景图外，没有其他图片。卡片形状会根据按钮的大小和形状进行调整——您可以尝试只更改按钮元素的字体大小来查看效果。这不需要任何 JavaScript 代码——一切都归功于 CSS 子网格的神奇功能！” by Ana Tudor

![BlockNote image](https://r2.cosine.ren/i/2026/02/37b2d1691b9e51e8f8297d681dd55ac2.webp)

### 带有自定义 select 的文件夹堆叠

<https://codepen.io/captainbrosset/pen/dPXdgae>

> [现在选择元素是可以自定义的 ](https://developer.chrome.com/blog/a-customizable-select)，Patrick Brosset 向我们展示了点击后会弹出的文件夹堆叠，这给我们带来了很多乐趣。

![BlockNote image](https://r2.cosine.ren/i/2026/02/85203d57c955d41b833849bfdb16c99d.webp)

### 二进制时钟

<https://codepen.io/prisoner849/pen/zxBpPYW>

> prisoner849 在这段 Three.js 代码中展示了一款精美的时钟。即使你不懂[二进制时间 ](https://en.wikipedia.org/wiki/Binary_clock)，也能欣赏它的美——拿起时钟转动一下，从各个角度欣赏它塑料材质的光泽。

![BlockNote image](https://r2.cosine.ren/i/2026/02/7324e64ce37bdd35a183678a166e493f.webp)

## Refs

- [JavaScript Weekly #771](https://javascriptweekly.com/issues/771)

- [Codepen Spark #495](https://codepen.io/spark/495)
