---
title: "FE Bits Vol.30 | TypeScript 6.0 与 Next.js 16.2 发布、Safari 26.4 新特性"
link: weekly-30
description: 社区焦点：TypeScript 6.0 作为 5.x 最终版与 Go 重写 7.0 的过渡版本正式发布，Next.js 16.2 推出稳定跨平台 Adapter API，Safari 26.4 带来 CSS Grid Lanes 与 WebTransport 等 44 项新特性。文章精选涵盖 Addy Osmani 对 AI 理解债的警示、React 设计约束本质解析，以及纯 CSS 实现动态连线等实战技巧。CSS 栏目聚焦 corner-shape 与滚动驱动动画，展示新特性替代 JavaScript UI 库的可能。个人动态分享了 AI 辅助编程日常、2025 年终总结与旅行记录。
lang: cn
date: 2026-03-29 18:32:00
categories:
  - 周刊
updated: 2026-03-29 19:36:12
---

+++primary 关于本周刊

> 本期网址 <https://blog.cosine.ren/post/weekly-30>
> 本周刊更新时间期望是在每周天。
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe)

本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。
+++

今天是 2026 年 3 月 29 日，星期日。

## 个人动态

首先是我的年终总结终于憋出来了

- [2025，说走就走的旅行记录](https://blog.cosine.ren/post/2025-travel-notes)：年终总结中的游记部分拆分发布，记录 2025 年旅行足迹
- [2025，跳出舒适圈的一年](https://blog.cosine.ren/post/2025-life-review)：关于抑郁、成长与记录的个人年终总结

然后是一些碎碎念：

- B 站视频《全！修！耗时两月用 AI 动画原创我推的孩子完美结局》分享

对的对的，这就是 AI 的正确用法，AI 就是用来补足遗憾的呜呜呜

https://www.bilibili.com/video/av116286709307444

- 爱酱日常 - 主动 push 妹妹学习

![](https://r2.cosine.ren/2026/03-26-lt1zw4dj.jpg)

- 妲喵一翻出了马克笔就搁这儿 cosplay 苹果呢（乐呵）看到门上写了个这个莫名其妙好笑

![](https://r2.cosine.ren/2026/03-27-p89bzg64.jpg)

这期依旧短短的～

## 社区动态

- [TypeScript 6.0 正式发布](https://devblogs.microsoft.com/typescript/announcing-typescript-6.0/)：作为连接 5.9 与 7.0（Go 语言重写版）的过渡版本，带来配置默认值更新、实用新特性及多项弃用警告

- [Next.js 16.2 发布跨平台 Adapter API](https://nextjs.org/blog/nextjs-across-platforms)：引入稳定的 Adapter API，与 OpenNext、Netlify、Cloudflare 等平台合作，解决多平台部署兼容性问题

- [Safari 26.4 发布，支持 CSS Grid Lanes 与 WebTransport](https://webkit.org/blog/17862/webkit-features-for-safari-26-4/)：带来 44 项新特性与 191 项修复，核心亮点包括 CSS Grid Lanes 瀑布流布局、WebTransport 低延迟通信协议及 Keyboard Lock API

- [X 上的 Cheng Lou：“My dear front-end developers……”](https://x.com/_chenglou/status/2037713766205608234)：Cheng Lou 发布了一个纯 TypeScript 实现的、用户态（userland）、快速、准确且全面的文本测量算法，旨在彻底变革 Web UI 布局，摆脱对 CSS 和 DOM 测量的依赖，从而解锁更高效、更复杂的界面设计。
  - 项目代码已在 GitHub 上开源 [chenglou/pretext](https://github.com/chenglou/pretext)
  - 一个非常有趣的书记舞示例：[finally the web has become interesting again](https://x.com/EsotericCofe/status/2038076140661932273)

![](https://r2.cosine.ren/i/2026/03/63960e4bca71096f58e596ba020bf2f4.webp)

## 文章

- [New to the web platform in March](https://web.dev/blog/web-platform-03-2026?hl=en)：2026 年 3 月 Web 平台新功能概览，涵盖 Chrome 146、Firefox 149、Safari 26.4 的最新更新，包括 CSS 滚动触发动画、Grid Lanes、JS Iterator.concat 与 CloseWatcher 等

- [纯 CSS 实现双圆动态连线与距离计算](https://frontendmasters.com/blog/two-circles-one-arrow-and-anchor-positioning/)：利用 CSS Anchor Positioning、三角函数与容器查询实现双圆动态连线与距离计算的纯 CSS 解决方案

- [Shadow DOM Focus Delegation 正确使用指南](https://frontendmasters.com/blog/shadow-dom-focus-delegation-getting-delegatesfocus-right/)：深入探讨 Web Components 中 delegatesFocus 属性的作用与最佳实践

- [可滚动容器内下拉菜单失效问题解析与修复](https://www.smashingmagazine.com/2026/03/dropdowns-scrollable-containers-why-break-how-fix/)：解析下拉菜单在可滚动容器中失效的根本原因，并提供 Portal、Anchor Positioning、Popover API 等多种解决方案

- [理解债：AI 生成代码的隐性成本](https://addyosmani.com/blog/comprehension-debt/)：探讨过度依赖 AI 生成代码所带来的理解债，强调人类对系统深层理解的重要性

- [React 设计选择背后的深层约束](https://dev.to/playfulprogramming/two-react-design-choices-developers-dont-like-but-cant-avoid-d6g)：SolidJS 作者 Ryan Carniato 揭示 React 延迟状态提交与 Effect 依赖数组设计背后的异步约束本质

- [When All You Can Do Is All or Nothing, Do Nothing – CSS Wizardry](https://csswizardry.com/2026/03/when-all-you-can-do-is-all-or-nothing-do-nothing/)：在无法精准判断优化条件时，对于 `loading=lazy` 和 `fetchpriority=high` 等性能提示，选择不作为（Do Nothing）往往是更安全和更优的选择。

- [Iterator.concat](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Iterator/concat)：Chrome 146 与 Safari 26.4 共同支持的迭代器连接方法，通过连接现有迭代器创建新迭代器，已成为 Baseline Newly available

- [CloseWatcher 接口](https://developer.mozilla.org/docs/Web/API/CloseWatcher)：Firefox 149 新增支持，允许开发者实现通过设备原生关闭机制（Esc 键、Android 返回键）关闭的组件，行为与内置对话框和弹窗一致

## CSS 新特性

- [CSS 滚动触发动画正式到来](https://developer.chrome.com/blog/scroll-triggered-animations)：Chrome 146 新增基于滚动位置的声明式动画控制，通过 trigger-scope 属性隔离触发器名称，将动画工作卸载到 worker thread 以提升性能

- [探索 CSS corner-shape 与滚动驱动动画结合](https://css-tricks.com/experimenting-with-scroll-driven-corner-shape-animations/)：介绍如何将 CSS 新属性 corner-shape 与滚动驱动动画结合，实现动态边角形状效果

- [CSS 新特性大合集：逐步取代 JavaScript UI 库](https://blog.gitbutler.com/the-great-css-expansion)：介绍 Anchor Positioning、Popover API、Scroll-Driven Animations 等 10 余项 CSS 新特性，可替代约 322 kB 的 JavaScript 代码
