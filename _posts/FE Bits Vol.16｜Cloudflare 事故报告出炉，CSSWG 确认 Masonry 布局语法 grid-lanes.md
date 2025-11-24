---
title: FE Bits Vol.16｜Cloudflare 事故报告出炉，CSSWG 确认 Masonry 布局语法 grid-lanes
description: 本期：Git 2.52 首次引入 Rust；Cloudflare 故障；Angular v21 聚焦 AI；CSS 进展：Masonry grid‑lanes、Chrome 144 锚点变换感知。
link: weekly-16
catalog: true
lang: cn
date: 2025-11-23 19:30:00
tags:
  - 前端
  - JavaScript
  - CSS
categories:
  - 周刊
---

> 本期网址 https://space.cosine.ren/post/weekly-16
> 本周刊更新时间期望是在每周天
> 目前推荐使用 [Folo](https://folo.is/) 订阅本周刊的 [Quaily RSS](https://quaily.com/cosine/feed/atom)。
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。
> QQ 讨论小群 598022684，日常讨论前端技术 & 生活，也可在群里投稿自己的文章，随意加入，比较偏向粉丝群的性质～
> 本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。

今天是 2025 年 11 月 23 日，星期天。

网站用 [astro-pagefind](https://github.com/shishkin/astro-pagefind) 实现了无需后端的搜索，好用的。

![](https://r2.cosine.ren/i/2025/11/429d0e73b863269741029207fbed29fc.webp)

计划在没有后端的情况下把网站功能完善，然后再逐步加上有后端的功能，这样没后端的也好部署，就像以前用 hexo 的体验一样。

![](https://r2.cosine.ren/i/2025/11/d01f66f7df2a7dd34388608e6fdc1230.webp)

## 生态与社区动态

- [Highlights from Git 2.52](https://github.blog/open-source/git/highlights-from-git-2-52/)：Git 2.52 带来了新命令、性能优化，此版本首次使用 Rust 代码来实现 Git 的一些内部功能，Git 3.0 将全面要求 Rust。

- Cloudflare 于北京时间 2025 年 11 月 18 日晚间发生全球性网络故障，事件影响遍及多个地区和服务，包括 WARP 及 Application Services，最终在连续两个多小时后逐步恢复正常。

> 故障时间线与恢复进展
> 20:13 起部分地区恢复，之后多次“再爆炸”与恢复循环。
> 21:04 官方确认在伦敦禁用 WARP 访问，说明问题基本定位。
> 21:09~21:35 官方多次更新状态，逐步恢复 Access、WARP 与应用服务（Application Services）。
> 22:03 时 X（即 Twitter）网页版恢复访问

如果你好奇原因，那么可以查看[官方事故报告](https://blog.cloudflare.com/18-november-2025-outage/)。

- [React 2025 年现状调查](https://survey.devographics.com/en-US/survey/state-of-react/2025)：React 生态系统年度调查又开始了。提交截止日期为 11 月 25 日，也就是下周二。感兴趣的可以在这里查看 [2024 年的调查结果](https://2024.stateofreact.com/en-US)。

这种调查的填写过程中其实能学到不少东西。类似之前的 JS / CSS 的年度调查。

React 团队近年来以稳健的节奏迭代，引入了 Server Components、Compiler 等，还设立了 React Foundation 进行管理。

- [Announcing Angular v21](https://blog.angular.dev/announcing-angular-v21-57946c34f14b)：Angular 迎来 v21，这是一次面向未来的版本更新，专注于 AI 集成、可访问性及现代开发体验。

- Reddit `/r/node` 讨论 [**NestJS** 的优缺点](https://www.reddit.com/r/node/comments/1ov6xrd/nestjs_is_bad_change_my_mind/)，引发社区思考框架选型取舍。

## 文章与视频

- [如何撰写出色的 agents.md 文件：来自 2500 多个代码库的经验总结](https://github.blog/ai-and-ml/github-copilot/how-to-write-a-great-agents-md-lessons-from-over-2500-repositories/)：GitHub 分享了从 2500+ 仓库提炼出的经验，教你如何写出真正有用的 `agents.md` 文件。

- [谈谈工作中的犯错 | CatCoding](https://catcoding.me/p/avoid-mistake/) 错误不仅是个人问题，也暴露团队在设计、权限、质量控制、代码 Review 等方面的短板。

- [从 Cloudflare 故障到代码安全 | Cyandev](https://cyandev.app/post/from-cloudflare-outage-to-code-safety)：从一次 Rust 相关的服务中断聊到内存安全与代码复杂度。

- [如何使用分层模式在 CSS 中创建 3D 图像](https://frontendmasters.com/blog/how-to-create-3d-images-in-css-with-the-layered-pattern/)：使用 CSS 的 `transform-style: preserve-3d` 让所有层在三维空间可见，利用透视与光影制造立体幻觉，并通过 `perspective`、`translateZ()`、`filter` 等技巧实现动态的 3D 效果。

![](https://r2.cosine.ren/i/2025/11/2ca04a3a3ba0f48802a02210f4fc825c.webp)

- [Keyframes Tokens 跨项目动画标准化](https://www.smashingmagazine.com/2025/11/keyframes-tokens-standardizing-animation-across-projects/)：如何通过将动画关键帧 (`@keyframes`) 设计为可重用的 Keyframes Tokens，来实现动画系统的标准化与可维护化。

- [我打赌你不知道可以用 Chrome 浏览器开发工具做的六件事 Part 1](https://www.readwriterachel.com/things-i-learned/2025/11/09/devtools-1.html)：带你发现 Chrome DevTools 中那些被忽略却超实用的隐藏技巧，提升调试效率。

本篇是 Part 1，涵盖前三个内容：

1. 用 `console.time()` 和 `console.timeEnd()` 精准计时函数执行。
2. 利用 DOM Breakpoints 实时捕捉元素变化，并自动暂停脚本运行。
3. 用 `monitor()` 在控制台监听任意函数调用。

断点是真的很重要，严肃学习！

## CSS 新特性

- [通过实验学习更多 CSS random() 功能](https://frontendmasters.com/blog/more-css-random-learning-through-experiments/)：作者通过多个实验展示了如何用 CSS 的 `random()` 函数创造动态有趣的视觉效果，如旋转星空、滚动视差(parallax)星空及基于滚动的点阵动效，虽然目前仅 [Safari 技术预览版](https://developer.apple.com/safari/technology-preview/)支持该功能，但文章提供了可视化演示和代码片段，展示了 `random()` 带来的新创意空间和未来样式系统的潜能。

- [介绍下与 CSS 自定义组件相关的 :state() 函数](https://www.zhangxinxu.com/wordpress/2025/11/css-state-function/)：介绍了 CSS :state() 伪类函数，这是 Web Components(网页组件) 的新特性，可用来根据组件内部状态修改样式。

- [在 Chrome 浏览器 144+ 中，锚点定位具有变换感知功能](https://www.bram.us/2025/11/20/anchor-positioning-is-transform-aware-in-chrome-144/)：Chrome 144 将 Anchor Positioning 改为对 transform 变换敏感（transform-aware），更新后 tooltip、浮层等会根据元素的变换后位置进行定位。

- [Masonry Switch 语法 #1022](https://github.com/w3c/csswg-drafts/issues/12022#issuecomment-3525043825)：CSS 工作组（CSSWG）确定采用新语法 `display: grid-lanes` 来启用 CSS Grid Level 3 新增的 Masonry 布局。

## 小贴士

虽然发过那么多次 CSS 新特性的博文推荐，但是在项目中实际用上的没那么多，决定开个新栏目，记录一下平常真在项目里用上了的小 tip！

CSS `scroll-state` 用来渐进式的增强滚动容器底部的羽化遮罩时还是很好用的～

![](https://r2.cosine.ren/i/2025/11/eb89146b7bf76508c7e2a67325d0b710.gif)

```css
/* https://github.com/parcel-bundler/lightningcss/issues/887 */
.scroll-feather-mask {
  container-type: scroll-state;
}
@container scroll-state(scrollable: bottom) {
  .scroll-feather-mask::before {
    content: "";
    background: linear-gradient(
      to bottom,
      transparent 0%,
      var(--gradient-bg-start) 70%,
      var(--gradient-bg-start) 100%
    );
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 10;
    display: block;
    height: 5rem;
  }
}
```

参考链接

1. [Adaptive Alerts (a CSS scroll-state Use Case)](https://frontendmasters.com/blog/adaptive-alerts-a-css-scroll-state-use-case/)
2. [CSS @container scroll-state 容器滚动查询](https://www.zhangxinxu.com/wordpress/2025/08/css-container-scroll-state/)
3. [Chrome 133 Goodies](https://css-tricks.com/chrome-133-goodies/#aa-scroll-states-in-container-queries)

## 工具

- [Free Online Image Converter](https://imageconverter.dev/) 无需登录、无需上传服务器的在线图片转换工具，完全运行于浏览器端，支持多种主流与新兴图片格式的相互转换，可调整输出格式及质量，立即下载结果，没有水印、不限数量。

- [Baseline JS Docs](https://baselinejs.vercel.app/)：检测 JavaScript 代码是否符合 Web 平台 Baseline 标准的 ESLint 插件，让代码对所有浏览器都更友好。

## 趣站与 Codepen 精选

### Classic 8×8-pixel B&W Mac patterns

网站：https://paulsmith.github.io/classic-mac-patterns/
介绍文章： [Classic 8×8-pixel B&W Mac patterns](https://pauladamsmith.com/blog/2025/09/classic-mac-patterns.html)

由 Paul Smith 制作的 Classic Mac OS System 1 背景图案，这些极小尺寸的复古像素图案可通过 CSS `background-repeat` 实现无限平铺效果。尽管源自经典的 Mac OS 设计风格，但它们在现代网页中依然有独特的美感和实用价值。

![](https://r2.cosine.ren/i/2025/11/c9884109fffdba36b2b9c28ba003611a.webp)

### Creepy Button

https://codepen.io/jkantner/pen/ZYWKvqW

> "这个按钮在监视你"。从 Jon Kantner 这款俏皮的按钮下面探出头来，你会发现一双卡通眼睛正在跟踪你的一举一动 👀。

![](https://r2.cosine.ren/i/2025/11/b2d6e6c953d6300483d906c7d699efdd.gif)

### Liquid Glass Clock

https://codepen.io/alexandrevacassin/pen/YPqqqwr

顾名思义，一个液态玻璃数字时钟。

![](https://r2.cosine.ren/i/2025/11/ab2be23ad6110f1d322cc6f90d9d57aa.webp)

## Refs

- [React Status Issue 452: November 19, 2025](https://react.statuscode.com/issues/452)
- [JavaScript Weekly Issue 762: November 21, 2025](https://javascriptweekly.com/issues/762)
- [Node Weekly Issue 601: November 18, 2025](https://nodeweekly.com/issues/601)
- [Frontend Focus Issue 718: November 19, 2025](https://frontendfoc.us/issues/718)
- [Codepen Spark #483](https://codepen.io/spark/483)
