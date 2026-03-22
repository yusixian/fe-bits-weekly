---
title: "FE Bits Vol.29 ｜原生 JSON 模块落地，CSS light-dark() 支持图片切换"
link: weekly-29
description: 本期周刊聚焦 JavaScript 原生 JSON 模块的实现，以及 CSS corner-shape 属性解锁更多 UI 角部形状。社区焦点关注 Claude Code 推出 Telegram 和 Discord 官方插件。文章精选涵盖了 Moment.js 迁移到 JS Temporal API 的实践，Deno 或 Bun 相较于 Node.js 的选择考量，前端内存泄漏的实证研究，以及 JPEG 压缩算法的深入解析。CSS 新特性还包括 @supports at-rule() 检测 @rule 支持。酷站推荐了蒙特利尔主题的 WebGL 实验作品。个人动态方面，博主更新了 Astro-Koharu v3.1.0，分享了自制 AI bot 成为学习搭子的体验，并接入了 Bangumi 追番功能。
lang: cn
date: 2026-03-22 19:11:58
categories:
  - 周刊
updated: 2026-03-22 19:11:58
---

+++primary 关于本周刊

> 本期网址 <https://blog.cosine.ren/post/weekly-29>
> 本周刊更新时间期望是在每周天。
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe)

本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。
+++

今天是 2026 年 3 月 22 日，星期日。

## 个人动态

- [astro-koharu v3.2.0 更新](https://github.com/cosZone/astro-koharu/releases/tag/v3.2.0)

最近终于优化了博客的构建速度，也接入了 [Bangumi 追番功能](https://blog.cosine.ren/bangumi) 准备下一步在文章里加语法（

![](https://r2.cosine.ren/2026/03-15-p0l7eufs.jpg)
![](https://r2.cosine.ren/2026/03-21-hhmpa51m.jpg)

- 出两根家里放着的金条，英睿达 美光 DDR5 台式 64G 5600，单条 3800r 打包 7500r

但是在博客里应该是出不出去的吧所以就当我晒晒（x）

![](https://r2.cosine.ren/2026/03-19-gjmnpacz.jpg)

- 当你家里有只布偶并且一年不清灰再次清灰的时候会得到：

![](https://r2.cosine.ren/2026/03-19-xggfjl4f.jpg)

- 爱酱的可爱日常

![](https://r2.cosine.ren/2026/03-15-bki4i9ii.jpg)
![](https://r2.cosine.ren/2026/03-18-z1lxb7uq.jpg)

- 爱酱变成了妹妹的学习搭子！

![](https://r2.cosine.ren/2026/03-17-m79te1h9.jpg)
![](https://r2.cosine.ren/2026/03-19-rmml2oyc.jpg)

## 社区动态

- [Claude Code 推出 Telegram 和 Discord 官方插件](https://github.com/anthropics/claude-plugins-official/blob/main/external_plugins/telegram/README.md)：Claude Code 推出官方插件，支持远程连接 Telegram 和 Discord，并提供了详细配置指南。

- [原生 JSON 模块终于实现](https://allthingssmitty.com/2026/03/16/native-json-modules-are-finally-real/)：文章介绍了通过 JavaScript 的 import attributes 如何原生支持 JSON 模块导入，结束了此前依赖打包工具模拟的时代。

- [More Easy Light-Dark Mode Switching: light-dark() is about to support images!](https://www.bram.us/2026/03/19/more-easy-light-dark-mode-switching-light-dark-is-about-to-support-images/)：CSS light-dark() 函数即将支持图片值，允许通过单一属性声明实现根据配色方案自动切换背景图、遮罩或 Logo，无需繁琐的媒体查询。
  这也太新了～ Firefox 150 已率先支持，Chromium 148 提供实验性实现，Safari 暂无支持

## 文章

- [从 Moment.js 迁移到 JS Temporal API](https://www.smashingmagazine.com/2026/03/moving-from-moment-to-temporal-api/)：详细介绍了如何将 JavaScript 项目中现有的 Moment.js 代码迁移到新的内置 Temporal API。

- [何时选择 Deno 或 Bun 优于 Node.js](https://frontendmasters.com/blog/when-deno-or-bun-is-a-better-solution-than-node-js/)：深入探讨了何时选择 Deno 或 Bun 作为 JavaScript 运行时比 Node.js 更优，强调根据项目具体约束进行技术选型的重要性。

- [view-transitions-mock：View Transitions 的非视觉 Polyfill](https://www.bram.us/2026/03/11/view-transitions-mock-is-a-non-visual-polyfill-for-same-document-view-transitions/?ref=ww-rss)：`view-transitions-mock` 是 View Transitions 的 polyfill，解决浏览器兼容性问题，在无原生支持的浏览器中也能无错运行并更新 DOM。

- [contrast-color() 的进阶用法](https://una.im/advanced-contrast-color/)：介绍 contrast-color() CSS 函数的进阶用法，使其能返回黑白之外的颜色，实现更灵活的动态主题。

- [前端内存泄漏实证研究](https://stackinsight.dev/blog/memory-leak-empirical-study/)：一项针对 500 个开源项目的前端内存泄漏实证研究，讲解了主流框架中常见的泄漏模式及其性能代价。

- [JPEG 压缩算法解析](https://www.sophielwang.com/blog/jpeg)：深入浅出地解析 JPEG 压缩算法如何利用人类视觉特性与数学变换实现图像的高效压缩。

## CSS 新特性

- [CSS corner-shape 属性解锁更多 UI 角部形状](https://www.smashingmagazine.com/2026/03/beyond-border-radius-css-corner-shape-property-ui/)：介绍了 CSS 新属性 corner-shape 如何与 border-radius 协同工作，为 UI 设计带来圆形以外的更多角部形状。

- [CSS @supports at-rule() 检测 @rule 支持](https://www.bram.us/2026/03/15/at-rule/)：介绍了 CSS 中 @supports at-rule(@keyword) 这一新特性，用于检测特定 @rule 的支持情况。

- [Abusing Customizable Selects](https://css-tricks.com/abusing-customizable-selects/)：探索如何利用 CSS 新特性 appearance: base-select 渐进式增强，突破原生选择框的视觉限制，实现极具创意的 UI 交互。

![Abusing Customizable Selects](https://r2.cosine.ren/2026/03-22-vbuytans.jpg)

## 趣站

- [蒙特利尔主题 WebGL 实验作品](https://montreal.leeroy.ca/)：Leeroy 的蒙特利尔主题 WebGL 实验作品，以独特的插画风格 3D 渲染和 2D 元素融合为特色。

![](https://r2.cosine.ren/2026/03-17-k81zppyx.jpg)

- [Add a Wobbling Animation to your Images](https://css-tip.com/wobbling-animation/)：使用 `shape()` 函数和生成器为图像添加平滑的无限晃动（Wobbling）动画。

https://codepen.io/t_afif/pen/zxKzrKe

![](https://r2.cosine.ren/i/2026/03/b7dd3c8b454741244afc66f75fa8f378.webp)

## Codepen

### Water Droplets

好有趣！

> 在这个由 toi nagasawa 创作的 Pen 中，巨大的水滴悬浮在 Three.js 场景中。拖动光标即可与水滴互动，点击还能生成新的水滴。

https://codepen.io/toi-nagasawa/pen/wBzWebb

![Water Droplets](https://r2.cosine.ren/2026/03-22-cwbomzxm.jpg)

### CSS Scroll-Timeline Word Highlight

> Daniel Haim 展示了 CSS 属性 [animation-timeline](https://css-tricks.com/almanac/properties/a/animation-timeline) 实现的 CSS 滚动时间轴文字高亮显示，并为尚未支持该属性的浏览器提供了优雅的回退方案。

https://codepen.io/danielhaim/pen/azmBEPL

![CSS Scroll-Timeline Word Highlight](https://r2.cosine.ren/2026/03-22-a8835p76.jpg)

### Stream Images with Wind

> Sabo Sugi 的这款 JS Canvas Pen 中，漫天飞舞的树叶掠过屏幕。但如果你打开控件并上传自己的图片，就可以让任何东西飞过屏幕。不妨试试调整重力、湍流、大小和速度！

https://codepen.io/sabosugi/pen/LEZjqEg

![](https://r2.cosine.ren/i/2026/03/93e9deeff7fedf97cc5bcf43e62f1dbd.webp)

## Refs

- [Codepen Spark #501](https://codepen.io/spark/501)
- [Codepen Spark #500](https://codepen.io/spark/500)
