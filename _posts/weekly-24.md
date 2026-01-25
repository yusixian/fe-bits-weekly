---
title: FE Bits Vol.24 | Rolldown 1.0 RC、Anime.js v4.3 自动布局与 Chrome 145 100vw 滚动条感知
link: weekly-24
lang: cn
date: 2026-01-25 18:53:00
categories:
  - 周刊
updated: 2026-01-25 18:55:45
---

> 本期网址 <https://blog.cosine.ren/post/weekly-24>\
> 本周刊更新时间期望是在每周天。\
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。\
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。\
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe)\
> 本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。

今天是 2025 年 1 月 25 日，星期天。

## 个人动态

### 碎碎念

以下是一些碎碎念杂谈：

越用 AI 会越有种「啊他果然取代不了我」的感觉，尤其是他犯蠢的时候。

但是很多时候又很方便确确实实省下来了很多摸鱼时间，又爱又恨的感觉。

也不奇怪很多程序员会排斥 AI 写代码，因为架构上真的很容易犯蠢，写的代码但凡是个代码洁癖都会感觉哎呦还不如自己来写，但是重复性业务工作真的太省劲了。

虽然下沉市场和资本感觉都在 AI 狂欢，但我体感上的话，感觉其实平常程序员的生活是从写代码变成审计划和审代码改代码了，更爽了，写自己的东西更有劲了 x

ai 真的容易堆屎山，我现在每次写完让 opus 4.5 review 一遍 codex review 一遍都差不多了我再看才能好点儿，不过他们自己 review 的效果还是挺好的。

PS: 仅限前端/ Swift 领域，后端我只能通过同事的使用感受推测。

### 项目更新

<https://github.com/yusixian/moe-copy-ai>

我很喜欢现在 [Moe Copy AI 的内容提取功能](https://moe.cosine.ren/docs/user-guide/usage#%E6%89%B9%E9%87%8F%E6%8A%93%E5%8F%96)～

现在可以直接选中提取推文串进行总结的，准备下个版本改改加一下常用的选择器，现在还是直接选中元素提取出来进行总结。

![Moe Copy AI 内容提取功能示例](https://r2.cosine.ren/i/2026/01/d61710239f2f8c765531ef38cb1df897.webp)

然后这周 Moe Copy AI 发了 [v0.3.0](https://github.com/yusixian/moe-copy-ai/releases/tag/0.3.0)，太感动了终于有大佬 [@hakadao](https://github.com/hakadao) 帮忙改了一下最开始 AI 写的一坨的 UI 了，工作量巨大，现在 UI 清爽多了！（[#26](https://github.com/yusixian/moe-copy-ai/pull/26)）

虽然现在还在陆续改，但是我也看不下去之前的了所以直接推了一版（

[更新日志](https://moe.cosine.ren/docs/changelog#v030---2026-01-22) | [下载](https://chromewebstore.google.com/detail/moe-copy-ai/dfmlcfckmfgabpgbaobgapdfmjiihnck)

![Moe Copy AI 新 UI 示例](https://r2.cosine.ren/i/2026/01/f1c2f06395200826a0c7e99afd7fedcc.webp)

### 博客更新

然后博客更新这边，最近把我们的 Electron 应用配置上了 Mac 端的 TestFlight，用 GitHub Actions 实现自动化构建和上传。踩了不少坑，记录一下整个流程。

[用 GitHub Actions 自动化 Electron 上架 MAS（Mac App Store）](https://blog.cosine.ren/post/electron-mas-testflight-guide)

然后给 astro-koharu 添加了无后端的编辑功能，只在本地 dev 模式有，还打算加一个无后端管理本地文章的 CMS 功能，灵感来源于上周发的 [OS 即 CMS 文章](https://blog.jim-nielsen.com/2026/os-as-cms/)\
编辑器使用的是 [BlockNote](https://github.com/TypeCellOS/BlockNote) 是好用的，基于 Prosemirror 和 Tiptap。

![astro-koharu 编辑功能演示1](https://r2.cosine.ren/i/2026/01/a1c1d69ef48c758010e553e882e470db.webp)![astro-koharu 编辑功能演示1](https://r2.cosine.ren/i/2026/01/6c6956e3b49729ddf272669f3f738f13.webp)

另外现在可以自动创建不存在的分类映射了，也可以改～

![astro-koharu 编辑功能演示3](https://r2.cosine.ren/i/2026/01/1d86afe19ed2fe921990657685393c2d.webp)

## 社区动态

- [Announcing Rolldown 1.0 RC](https://%3Chttps://voidzero.dev/posts/announcing-rolldown-rc%3E)：Rolldown 正式发布 1.0 发布候选版本（RC），作为 Vite 未来的核心打包工具，它在保持 Rollup 兼容性的同时，凭借 Rust 实现了 10-30 倍的速度提升。此 RC 标志着 API 的稳定性。在 1.0 之前不会有任何破坏性改动。

- Vercel 公布了 [skills.sh](http://skills.sh)，是一个用于查找和共享代理 Skills 的网站，其中 Remotion 也出了 skill，现在只需要使用 Claude Code 即可通过编程方式制作视频！通过 `npx skills add remotion-dev/skills`。

https://x.com/vercel/status/2013660091854000360

https://x.com/Remotion/status/2013626968386765291

- [Using 100vw is now scrollbar-aware](https://www.bram.us/2026/01/15/100vw-horizontal-overflow-no-more/)：从 Chrome 145 开始，如果根元素（而非  `body` ）设置了`overflow: scroll`，则在  `vw`  的大小中应考虑默认滚动条宽度，解决了长期以来因视口单位导致的网页多余水平滚动问题。该改进同样适用于 vh（对应水平滚动条）以及视口单位的小、大、动态变体（sv*, lv*, dv\*）

### Anime.js v4.3

Anime.js v4.3 发布，引入强大的自动布局（Auto Layout）动画功能，支持平滑处理复杂的 CSS 布局变换。

这个真的好诶！跨框架造福前端人。

https://x.com/JulianGarnier/status/2013661582417375320

官方提供了 [文档说明](https://animejs.com/documentation/layout) 和 [发布日志](https://github.com/juliangarnier/anime/releases/tag/v4.3.0)，并在 CodePen 上发布了 [示例集合](https://codepen.io/collection/yykPaw)

找了一个示例如下，太丝滑了：

<https://codepen.io/juliangarnier/pen/PwzmxwR>

## 优质文章

- [不会编程的人能靠 AI 独立开发应用吗？](https://blog.solazy.me/20260120/)：作者认为，AI 确实大幅降低了“将想法翻译成代码”的技术门槛，但“不会编程”、“靠 AI”和“应用”这些词语的边界远比想象中模糊。在与 AI 协作的过程中，使用者会不自觉地习得编程概念，AI 更多是作为博学但死板的“徒弟”或“翻译官”，帮助有逻辑、有想法的人实现愿景，而非代替思考和定义问题。

- [Inside Turbopack: Building Faster by Building Less](https://<https://nextjs.org/blog/turbopack-incremental-computation>)：深入解析 Next.js 的新一代打包工具 Turbopack 如何通过增量计算（Incremental Computation）和细粒度缓存实现极致的开发响应速度。

- [The Incredible Overcomplexity of the Shadcn Radio Button](https://paulmakeswebsites.com/writing/shadcn-radio-button/)：探讨了现代前端 UI 框架（如 Shadcn）如何将原本简单的原生单选按钮变得异常复杂，并呼吁回归 CSS 原生开发。

- [HTTP Archive 2025 Web Almanac | CSS-Tricks](https://css-tricks.com/http-archive-2025-web-almanac/)：介绍 HTTP Archive 发布的 2025 年度《Web 年鉴》报告，总结了当前 Web 性能、CSS 趋势、可访问性及资源膨胀等核心数据。

- [The challenges of soft delete](https://atlas9.dev/blog/soft-delete.html)：探讨了传统“软删除”模式（如 `archived_at` 列）带来的长期复杂性，并对比分析了触发器、应用层事件和 WAL 等更优的替代方案。\
  对于新项目，作者优先推荐基于触发器的方案，因为它部署简单、不引入额外基建，且有效隔离了活跃数据与归档数据。

- [Rethinking “Pixel Perfect” Web Design — Smashing Magazine](https://www.smashingmagazine.com/2026/01/rethinking-pixel-perfect-web-design/)：探讨了在多设备、响应式和动态内容的现代 Web 环境下，为何传统的“像素级完美（Pixel Perfect）”观念已不再适用。

- [localspace](https://github.com/lin-michael/localspace)：现代化的  `localForage`  替代方案，提供简单的浏览器存储封装。

- [Overscroll Effects On Nested Scrollers In All Browsers](https://nerdy.dev/overscroll-effects-on-nested-scrollers-in-all-browsers?utm_source=rss)：Chrome 145 现已支持嵌套滚动容器的过度滚动效果（Overscroll Effects），实现了全浏览器体验的一致性。此前该效果仅在根页面有效，且只有 Safari 和 Firefox 支持子容器的回弹。

- [How to animate SVG with CSS: Tutorial with examples](https://blog.logrocket.com/how-to-animate-svg-css-tutorial-examples/)：这篇教程详细介绍了如何利用 CSS 属性和关键帧动画为 SVG（Scalable Vector Graphics，可缩放矢量图形）添加动态效果，从基础嵌入到复杂的路径动画均有涵盖。

### 新特性

- [Follow-the-leader pattern with CSS anchor positioning](https://una.im/follow-the-anchor)：介绍如何利用 CSS 锚点定位（CSS Anchor Positioning）实现元素跟随交互目标移动的“随动”（Follow-the-leader）模式。

![Follow-the-leader 示例](https://r2.cosine.ren/i/2026/01/a7ab50a04bff59e7940cac51bb2ff71d.webp)

## 工具

- [darula-hpp/shimmer-from-structure](https://github.com/darula-hpp/shimmer-from-structure)：一个能够根据 React 组件实际 DOM 结构自动生成像素级精确骨架屏（Shimmer Skeleton）的工具库。

- [Better SVG](https://frontendfoc.us/link/179582/web)：用于编辑带有实时预览功能的 SVG 文件的 VS Code 扩展程序，包含许多实用功能，例如实时预览、颜色选择器、缩放/平移控件、可编辑的配色方案 currentColor 值、深色背景切换以及 SVGO 集成，一键优化 svg 体积。

![扩展示例](https://r2.cosine.ren/i/2026/01/d6869db7c4de12b7514420cb44836be6.webp)

## 趣站与 Codepen 精选

### **使用 CSS 中的 drop-shadow() 滤镜为不规则形状添加阴影**

<https://www.wearedevelopers.com/en/magazine/675/adding-shadows-to-irregular-shapes-in-css-with-filter-drop-shadow-675>

> Chris Heilmann 向我们展示了如何使用  `filter: drop-shadow()`  为不规则形状添加阴影，该过滤器可以识别“图像的透明部分或 SVG 路径的形状，并相应地应用阴影”。

<https://codepen.io/codepo8/pen/qENbVmb>

![BlockNote image](https://r2.cosine.ren/i/2026/01/61443be0ae7d2172563bb0d574c7355d.webp)

### **使用 superellipse() 函数创建迷人的角形 — 仅 CSS**

> 在这个由 Zoran Jambor 创作的 Pen 中，一个简单的圆形通过“ `superellipse()` CSS 函数的随机值”演变成万花筒般的形状。点击“关于”按钮，即可查看关于  `superellipse()`  函数的简短教程和实用资源。

<https://codepen.io/ZoranJambor/pen/ogLLLgr>

![Codepen 示例2](https://r2.cosine.ren/i/2026/01/605f54710d717bbd7b63235bd90c4d0d.webp)

### **CSS 光学错觉**

> Alvaro Montoro 在这份令人惊艳的合集中分享了大量用纯 CSS 实现的著名光学错觉作品。其中一张在电视模式下简直太震撼了 😵‍💫

<https://codepen.io/collection/GpWqKk>

![Codepen 示例3](https://r2.cosine.ren/i/2026/01/7896eaf9e6daefc9237eec2a9f17bd19.webp)

### **旧布随风飘扬**

> 在 Sabo Sugi 的这个 Three.js 场景中，一块饱经风霜的布料在微风中轻轻飘动。深入设置控件，即可更改图像、颜色、风力和撕裂效果。

<https://codepen.io/sabosugi/pen/ByzLYpb>

![Codepen 示例4](https://r2.cosine.ren/i/2026/01/cae6c7302db262b055672db83ada32ff.webp)

## Refs

- [React Status #459](https://react.statuscode.com/issues/459)

- [Frontend Focus #725](https://frontendfoc.us/issues/725)

- [Code Spark #491](https://codepen.io/spark/491)

- [Code Spark #492](https://codepen.io/spark/492)
