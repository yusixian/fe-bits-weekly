---
title: FE Bits Vol.27 | Oxfmt Beta 发布，Chromium「CSS 漏洞」实为 UAF
link: weekly-27
description: 本期周刊回归：过完年恢复更新，同时开源了轻量级 macOS 划词翻译 MoePeek（Swift 6，约 5MB/50MB）。社区焦点：React 基金会迁入 Linux 基金会、TanStack 推出 Hotkeys、Oxfmt 进 Beta（Prettier 规则全兼容、多格式与 Tailwind 类排序）、Claude Code 上线远程控制；所谓“CSS 漏洞”实为 Chromium UAF。文章精选涵盖更安全的 Error.isError、显式资源管理 using/[Symbol.dispose]、高鲁棒 React 组件、十亿行虚拟滚动，以及 CSS 列表/zoom/sprites 实战。CSS 新特性关注 border-shape；工具与玩具包括 Modern CSS Snippets、CanWeUse 聚合、broz 截图浏览器、SVG Studio，并附多款精致 CodePen 与趣站。
lang: cn
date: 2026-03-01 23:21:22
categories:
  - 周刊
updated: 2026-03-01 23:52:00
---

> 本期网址 <https://blog.cosine.ren/post/weekly-27>
> 本周刊更新时间期望是在每周天。
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe)

本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。
+++

今天是 2026 年 3 月 1 日，星期天。

## 个人动态

过年放假，给我放爽了，停更的这阵子疯狂写代码，肝项目，现在周刊恢复更新啦～

想说些什么，却又有些不知道该说什么，等我更新年终总结吧（真有人 3 月份才写去年的年终总结啊）（哦原来那个人是我啊.webp）

过完了年，也跳完了槽，在新公司干了一阵子之后，愈发觉得自己的选择没错，这阵子发生了很多～

有关注我的前端频道的应该就能明白我最近在做什么，所以也在这里正儿八经发一下我们公司的招聘。招很多前端，有图像编辑器经验的话更好！岗位都在 JD 里了，二次元浓度越高越好（逃）欢迎佬来撩，远程办公，年限不限，实习兼职都可以，主要看适配程度，感兴趣的欢迎直接邮箱 `ball@mewtant.io` 投递！备注一下 cos 内推的就行，也欢迎私聊我了解了解情况～

我进来工作的感觉反正是灰常爽的！太二次元了很对我电波！

> 【我们的产品】我们是一家专注于研究二次元生成式 AI 的创业公司，目前已研发上线的 text-to-image AI 生成和消费平台已成为海外头部产品，用户量和市场占有率迅速增长中。\
> 【我们的资本背景】现已获得 makers fund 等多家一线顶级机构的多轮投资，目前估值上亿美元。\
> 【我们的团队】公司总部位于新加坡，五湖四海的小伙伴同样支持远程办公。公司团队成员背景丰富，技术能力扎实，没有无聊的潜规则，实习小天才和大师傅都能尽情发挥和学习。\
> 【你能得到】获得赛道最前沿技术/产品认知，一起 work on 一个产品，切实体验让想象成为现实的经历，一段有意义且实现自身价值的工作。

> JD 相关： job.mewtant.io \
> 公司相关的 pr：曾获红杉投资、估值上亿美元，二次元公司凭动漫向 AI 生图掘金海外

企业文化 Be Like（直接偷偷 saka 发的）

https://x.com/Manjusaka_Lee/status/1924870680115609842

### MoePeek

之前 Easydict 经常漏内存太麻了，用久了就卡的要死，然后我的划词翻译需求又其实特别少，正好之前学了点 Swift 就自己过年顺手 vibe 写了一个（

主要自己用，纯 Swift 6 构建，安装体积约 5 MB ，后台运行内存约 50 MB ，很放心的挂后台，如果开 OCR 截图的话运行内存差不多到 100 MB

开源出来欢迎提 Issue ～ 但是不一定会加新功能了，会修修 bug

- 这个项目有 PopClip 集成，就在 Release 中，README 里有常见问题说明
- 成熟方案建议 Bob 或者 clicknow，这几个商业化的项目做的都很成熟

PS：我真的很喜欢 Easydict 但是找他们的内存泄漏问题再改有点难了  hhh  索性 vibe 一个只加自己需要的功能

一款轻量级 macOS 划词翻译工具，纯 Swift 6 开发，安装体积仅 5MB ，后台运行内存稳定约 50MB

GitHub: https://github.com/cosZone/MoePeek

![MoePeek-promo.webp](https://github.com/cosZone/MoePeek/raw/main/Resources/MoePeek-promo.webp)

## 社区动态

- [React 基金会：由 Linux 基金会托管的 React 新家园](https://react.dev/blog/2026/02/24/the-react-foundation)：React 官方宣布 React 基金会正式在 Linux 基金会（Linux Foundation）旗下成立，标志着 React 正式脱离 Meta 成为独立的开源项目。

- [TanStack 团队发布新库 TanStack Hotkeys](https://x.com/tan_stack/status/2022348762299904354)，解决键盘快捷键开发中常见的跨平台、作用域冲突、输入框聚焦忽略等“小坑”，提供类型安全（Type-safety）、快捷键序列识别、状态追踪及 React 等框架适配器，并集成 Devtools 插件提升开发体验。

- [Oxfmt Beta](https://oxc.rs/blog/2026-02-24-oxfmt-beta)：Oxfmt 宣布进入 Beta 阶段，自 Alpha 版本以来，Oxfmt 大幅扩展了功能，包括 100% 兼容 Prettier 的 JavaScript 和 TypeScript 格式化规则、支持多种文件格式（如 JSON, YAML, HTML, CSS 等）、内置 Tailwind CSS 类排序和可配置的导入语句排序功能，并提供了 Node.js API 和广泛的编辑器支持。（开始用好一阵子了，很香）

- [Claude Code 发布远程控制功能](https://x.com/claudeai/status/2026418435408986423)
  ：Claude Code 发布了名为“远程控制”(Remote Control) 的新功能，允许 Max 和 Pro 用户在终端启动任务后，通过手机或网页端继续控制 Claude Code 会话，实现跨设备无缝工作。目前，该功能已向 Max 用户开放，并将很快扩展至 Pro 用户。用户可通过运行 `claude rc` 命令开始使用。

- [An Exploit ... in CSS?!](https://css-tricks.com/an-exploit-in-css/)：很有意思，这篇文章提到了 Chromium 浏览器中一个被报道为“CSS 漏洞”的零日漏洞 (zero-day exploit) [CVE-2026-2441](https://nvd.nist.gov/vuln/detail/CVE-2026-2441)，并澄清了其技术细节，指出恶意并非源于 CSS 本身，而是 Chromium 渲染引擎中一个 Use After Free (UAF) 的内存管理缺陷。

## 文章

- [从 instanceof 到 Error.isError：JavaScript 中更安全的错误检查](https://allthingssmitty.com/2026/02/23/from-instanceof-to-error-iserror-safer-error-checking-in-javascript/)：这篇文章介绍了在 JavaScript 中使用 `Error.isError()` 代替 `instanceof Error` 进行错误检查的优势，尤其是在处理跨域（cross-realm）错误时的安全性和可靠性。

- [构建无懈可击的 React 组件](https://shud.in/thoughts/build-bulletproof-react-components)：一位 Vercel 资深工程师分享如何构建能应对真实复杂场景的健壮 React 组件，涵盖服务端渲染（Server Rendering）、水合（Hydration）、多实例、并发渲染（Concurrent Rendering）、组合（Composition）、Portal、View Transition、Activity、数据泄露防护及未来兼容性等现代 React 应用中的关键挑战。

- [Logo 泛滥问题（及其解决方案）](https://www.sanity.io/blog/the-logo-soup-problem?ref=ww-rss)：Sanity 团队开发了 React 组件 <LogoSoup /> 解决网页中多品牌 Logo 排列时因尺寸、比例与视觉重量不一致导致的“Logo Soup”混乱问题。

- [你的 JavaScript 清理自身的工作很快就会变得简单很多](https://piccalil.li/blog/its-about-to-get-a-lot-easier-for-your-javascript-to-clean-up-after-itself/?ref=articles-rss-feed)：JavaScript 即将通过 Explicit Resource Management 提案引入 `using` 与 `[Symbol.dispose]`，使资源清理更统一、可靠且自动化。

- [深入解析 CSS 自定义列表样式指南](https://piccalil.li/blog/an-in-depth-guide-to-customising-lists-with-css/?ref=articles-rss-feed)：本文深入探讨了如何使用 CSS 从基础到高级全面自定义 HTML 列表样式，并兼顾了排版美学与无障碍访问。

- [Creating Query Abstractions](https://tkdodo.eu/blog/creating-query-abstractions)：在 React 开发中，开发者习惯通过封装自定义 Hook 来复用 `useQuery` 的逻辑。然而作者指出，在结合 TypeScript 时，这种做法不仅会导致类型推断 (Type Inference) 失效，还容易引发复杂的“泛型地狱”。

- [Zoom!](https://www.stefanjudis.com/today-i-learned/css-zoom-to-scale-elements/)：解析了 CSS `zoom` 属性在实际布局中的实用性，及其与 `transform: scale` 的区别。

- [Remember sprites](https://www.joshwcomeau.com/animation/sprites/)：2026，重新审视 CSS 图像精灵 (Sprites) 技术，结合 `object-fit`、`object-position` 和 `step()` 动画函数，实现有趣的逐帧动画。

- [Virtual Scrolling for Billions of Rows — Techniques from HighTable](https://rednegra.net/blog/20260212-virtual-scroll/)：本文介绍了 `<HighTable>` React 组件中如何通过五种核心技术实现数十亿行数据的虚拟滚动 (Virtual Scrolling，实现高性能和可访问性。

## CSS 新特性

- [border-shape: the future of the non-rectangular web](https://una.im/border-shape/)：本文深入介绍了即将到来的 CSS 属性 `border-shape`，它将彻底改变构建非矩形网页元素的方式。

## 趣站

- [Matthew Pothier 先生的个人作品集网站，融合了色彩在重叠图层中晕染开来的视觉效果](https://webgl.souhonzan.org/entry/?v=3100)：一位电影摄影师极简且具有独特 WebGL 色彩流动效果的个人作品集网站。

站点地址：[Matthew Pothier-Cinematographer](https://www.matthewpothier.com/)

![](https://r2.cosine.ren/i/2026/02/5d2a5606f38507d635e1906977392334.webp)

- [Express yourself with Unicode](https://kaomojicool.club/)：Kaomoji Cool Club 收集了大量有趣的颜文字 (Kaomoji)，让你用 Unicode 字符表达自我。

![](https://r2.cosine.ren/i/2026/03/bd1aa5e00e558586672193b9c4a5c2d1.webp)

## 工具

- [Modern CSS Code Snippets](https://modern-css.com/?ref=ww-rss)：modern-css.com 是一个对比旧有 CSS 技巧与现代原生解决方案的参考网站，帮助开发者摆脱过时方法，利用最新 CSS 特性实现更简洁、高效的网页设计，很实用了，还有 RSS。
- [Can We Use](https://canwe.dev/?ref=ww-rss)：`canwe.dev` 是一个聚合了多种实用网页开发工具的网站，可以帮助开发者快速查询 Can I Use / Can I Stop、电子邮件客户端支持、可访问性信息、Web 平台功能进展及浏览器开发路线图等，为前端开发者提供一站式的信息查询服务。
- [broz](https://github.com/antfu/broz)：antfu 出品，一款简洁、无边框的屏幕截图浏览器，`npx broz antfu.me` 即可使用
- [SVG Studio](https://www.svg.studio/)，又一款基于浏览器的 SVG 处理工具，集成了优化、调试及修复渲染问题等多种功能。很好用。
  ![](https://r2.cosine.ren/i/2026/02/3d0370087c85d5a68f81dbbaeab53ce4.webp)
  ![](https://r2.cosine.ren/i/2026/02/dbe1a5fd03d9a393038ee22527e9284b.webp)

## Codepen

### Flood Above the Floor

https://codepen.io/wakana-k/pen/Eayqjwr

> 步入 Wakana Y.K. 创作的这个 Three.js 场景，你会发现自己置身于一个优雅的房间，积水没过脚踝。环顾四周进行探索，或者思考一下那些精美的装修正遭受着多么严重的水浸破坏。

![](https://r2.cosine.ren/i/2026/03/0726d2d45ab323a0a6aaeb512ec6f840.webp)

### Sliding border glow on hover for beveled cards

https://codepen.io/thebabydino/pen/EayVXKj

> Ana Tudor 通过 `corner-shape` 和 `background-clip` 展示了现代 CSS 的大师级用法，以此回答了 Reddit 上的一个提问，并为尚不支持这些特性的浏览器提供了回退方案。请查看 Ana 那份注释极其详尽的代码，以了解具体实现细节。

### 文本特效

https://codepen.io/collection/Poergz

> Pedro Ondiviela 分享了一系列醒目的 SVG 滤镜和 CSS 文本效果。每个效果都是可编辑的，因此你可以使用自己的文字进行尝试。

### Aerodynamic Typography 空气动力学字体

https://codepen.io/mike-at-redspace/pen/EayBZwy

> 使用鼠标滚轮控制风扇，在这个来自 mike-at-redspace 的有趣 Matter.js Pen 中观看字母飞舞并从墙壁上反弹。

![](https://r2.cosine.ren/i/2026/03/5debf56b71f277677cbbd746f48470df.webp)

## Refs

- [Web Weekly #184](https://webweekly.email/archive/web-weekly-184/)
- [Codepen Spark #498](https://codepen.io/spark/498)
