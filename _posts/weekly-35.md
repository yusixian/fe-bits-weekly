---
title: "FE Bits Vol.35 | Deno 2.8 发布，CSS 2026 新特性梳理"
link: weekly-35
description: 本期周刊回归：个人吐槽 VSCode 变卡后转向 lazygit 与 Zed；社区焦点关注 Deno 2.8 正式发布，Node.js 兼容率飙升至 76.4%，支持 deno install 替代 npm install。文章精选涵盖自定义滚动条实现、Cross-Document View Transitions 深度解析、2026 年 CSS 居中方法全面梳理、框架无关设计系统构建、Chrome 声明式部分更新 API、GSAP 滚动驱动 SVG 地图动画、CSS vs JS 动画性能对比，以及 AI 时代技术写作价值探讨。CSS 新特性关注 contrast-color() 等进入 Baseline。工具推荐 react-doctor（React 代码诊断修复）与 Liquid Layout（轻量布局引擎）。另附 Aimee's Papercraft World 纸艺互动网站与 JS Crossword 硬核填字游戏。
lang: cn
date: 2026-06-01 18:40:17
categories:
  - 周刊
updated: 2026-06-02 00:40:17
---

+++primary 关于本周刊

> 本期网址 <https://blog.cosine.ren/post/weekly-35>
> 本周刊更新时间期望是在每周天。
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe)

本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。
+++

今天是 2026 年 6 月 1 日，星期一，儿童节快乐呀！

## 个人动态

### 1.搬家

这两周都在忙着搬到惠州住，忙的不停，搬家收拾东西真的好累哦……虽然我不是主力搬东西和装东西的，主要起到一个装饰和收拾的作用（

买了一大堆东西，燃尽了，这几天都是拆快递拿快递收拾屋子忙的要死才只搬了一半。

但是惠州大亚湾待着的生活质量真的比广州舒服多了，喜欢，还经常看到有人在唱歌，没事儿了走几步就能到万达和永辉超市，绿化感觉也很好，一点儿都没有鬼城的感觉  。而且也没有广州那么多到处乱窜的电动车，不禁摩，这点真是太好了呜呜。

89r 的烤肉双人餐吃撑了……太好吃了性价比直接给到夯，而且荤素搭配还很均衡。店名是三肥七瘦。

![](https://r2.cosine.ren/i/2026/06/df6d2bcbb62b68318cd2d9a2249fa361.webp)

最近忙的脚不沾地的，感觉更新周刊的动力不太足呢，但是还是更一下。

### 2.VSCode 更新后个人体感变卡了

起因是发了条推表示「有点小悲伤，vscode 现在真的变得超级卡，打开速度奇慢无比，再也没有频繁使用的欲望，推荐插件的欲望了，以前的 vscode 插件推荐系列文章感觉也已经要成为过去式了，现在也是拥抱上 lazygit 和 zed 了」

然后正好也看到了很多吐槽 VSCode 更新的，所以也在这里记录一下我的体感。

因为以前是重度 VSCode 用户，以前虽然内存占用也大，但不会像新版本的一坨 AI 功能更新后，冷启动等一百年。

叠甲：我 M1 max 64g 之前经常同时启动 Cursor / Zed 和 VSCode 换着用，都是 disable all 插件启动新的 worktree 项目，VSCode 反正是明显感觉比起之前来说变得巨慢……

然后工具不好用那当然是换几个工具试试看 hhh 等好用了，再换回来也未尝不可。

不过就算这样也没卸载，因为我真的很喜欢 VSCode 的插件生态，电脑上还是 Zed Cursor VSCode 都有的状态，该吃的还得吃 x

Zed 虽然快，但是他的布局什么的也确实得适应适应，看看后面体验如何了。

### 3.最近的表达欲下降严重

感觉热情也下降了一些，这是怎么回事呢（？）

## 文章

- [Deno 2.8 正式发布，Node.js 兼容性大幅提升](https://deno.com/blog/v2.8)：Node.js 兼容率飙升至 76.4%，支持 deno install 替代 npm install。

- [一根上流滚动条的诞生](https://roriri.one/2026/05/06/better-scroll-bar)：介绍如何用 CSS 实现超酷的自定义滚动条效果。

- [Cross-Document View Transitions Part 2 深度解析](https://css-tricks.com/cross-document-view-transitions-part-2/)：深入探讨 View Transitions API 在 MPA 跳转中的动画平滑处理与状态恢复。

- [2026 年 CSS 居中方法全面梳理](https://css-tricks.com/the-state-of-css-centering-in-2026/)：系统对比 Flexbox、Grid 等现代方案的居中技巧，适合初学者参考。

![](https://r2.cosine.ren/2026/05-26-fs5qxghe.jpg)

- [框架无关的设计系统构建（第一部分）](https://piccalil.li/blog/framework-agnostic-design-systems-part-1/?ref=articles-rss-feed)：使用 Web Components 和 Elena 构建可移植的设计系统组件库及文档。

- [Chrome 声明式部分更新 API 详解](https://developer.chrome.com/blog/declarative-partial-updates)：介绍两组新 API 实现 HTML 非顺序流式交付，提升性能与开发体验。

- [用 GSAP 创建滚动驱动的 SVG 地图动画](https://tympanus.net/codrops/2026/05/21/creating-scroll-driven-svg-map-animations-with-gsap/)：教程详解如何结合 GSAP 的 ScrollTrigger 实现 SVG 地图动态轨迹与交互。

- [CSS vs JavaScript 动画性能深度剖析](https://www.joshwcomeau.com/animation/css-vs-javascript/)：打破传统误区，解释主线程阻塞对动画流畅度的本质影响。

- [AI 时代技术写作的价值与建议](https://css-tricks.com/technical-writing-in-the-ai-age/)：探讨 AI 对技术写作的冲击，提出聚焦真实案例、避免 AI 生成正文等建议。

- [用 CSS letter-spacing 实现文本揭示动画](https://css-tricks.com/revealing-text-with-css-letter-spacing/)：通过负值间距隐藏文本再过渡展开，实现逐字母揭示效果。

## CSS 新特性

- [2026 年 4 月 Baseline 月度更新：CSS contrast-color() 等新特性](https://web.dev/blog/baseline-digest-apr-2026?hl=en)：CSS 自动对比色函数、高精度求和等多项 Web 特性进入 Baseline。

- [In-N-Out Animations: Dialogs (Part 1/3)](https://frontendmasters.com/blog/in-n-out-animations-dialogs-part-1-3/)：介绍如何利用现代 CSS 新特性（allow-discrete 和 @starting-style）优雅地解决 `<dialog>` 等元素在 display 离散属性切换时的进出场动画难题。

## 工具

- [react-doctor：React 代码自动诊断修复工具](https://github.com/millionco/react-doctor)：开源工具，支持自动修复不良 React 代码，可作 AI Agent 的 Skill 使用。

- [Liquid Layout 轻量级 Web 布局引擎发布](https://x.com/AndrewPrifer/status/2060189424672194824)：一款灵感来自 SwiftUI、专为 Canvas 等 CSS 无能为力场景设计的小型可扩展布局引擎。[Demo](https://liquid-layout.vercel.app/) | [GitHub](https://github.com/AndrewPrifer/liquid-dom/tree/master/packages/layout) | `npm i @liquid-dom/layout`

![](https://r2.cosine.ren/2026/05-29-hx1np7k2.jpg)

## 趣站

- [Aimee's Papercraft World 纸艺互动网站](https://aimees-papercraft-world.com)：展现精美纸艺创作的视觉互动网站，交互设计独特。

![](https://r2.cosine.ren/2026/05-26-9ouxeyev.jpg)

- [JS Crossword：硬核 JavaScript 填字游戏](https://lyra.horse/fun/jscrossword/)：谜面等于谜底 eval()结果的趣味填字游戏，考验 JS 隐式转换。

![](https://r2.cosine.ren/2026/05-29-aduiv9ba.jpg)
