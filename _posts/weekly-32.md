---
title: "FE Bits Vol.32 | MUI v9 发布、TanStack RSC 新解、Google 打击后退按钮劫持"
link: weekly-32
description: 本期周刊分享博主 4 月新番体验与年度体检后的减肥 flag。社区焦点：MUI v9 同步 MUI X 主版本、Chrome 148 Beta 引入音视频原生懒加载，Google 打击“后退按钮劫持”。文章精选涵盖 Web 动画挤压拉伸原则、垂直代码架构、Intl API、TanStack 对 React Server Components 的另类实现。CSS 新特性关注多列布局折行与纯 CSS 日期范围选择。工具推荐 Zig+WASM 高性能 Web 终端 wterm、动画 React 组件库 Animata 与 React Photo Album 相册组件。
lang: cn
date: 2026-04-19 19:58:50
categories:
  - 周刊
updated: 2026-04-19 21:21:50
---

+++primary 关于本周刊
> 本期网址 <https://blog.cosine.ren/post/weekly-32> \
> 本周刊更新时间期望是在每周天。\
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。\
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。\
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe)

本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。
+++

今天是 2026 年 4 月 19 日，星期日。

## 个人动态

- 4 月新番观看体验，包括骨头社新作、婚姻剧毒等作品的评价。

> 4 月的新番吃的也挺好的，不愧是骨头社，打戏做的真不错，原以为婚姻剧毒这个番 PV 观感一般般的，第二集 op 也好听两集连看下来也很爽！
> 反而成为了最喜欢的番之一了。（兄弟……兄弟？）还有上伊那牡丹和春夏秋冬代行者、石纪元和入间

![婚姻剧毒截图1 哥们真可爱吧](https://r2.cosine.ren/i/2026/04/1031be6be9e23f658e554984aab43ae5.webp)

![婚姻剧毒截图2 天王老子来了这也是妹子我不管](https://r2.cosine.ren/2026/04-14-e695jp0y.jpg)

- 健康碎碎念：年度体检查出脂肪肝和多囊，立 flag 后天启动减肥大业。

> 每当我感觉我老了的时候，去医院：小姑娘年纪轻轻的怎么有脂肪肝和多囊啊😎 跳了啊！后天开始减肥大业，真的呜呜呜呜。这次立 flag 必须减下来，减下来了才能发女装照 x👿

## 社区动态

- [Material UI v9.0 发布](https://mui.com/blog/introducing-material-ui-v9/)：跳过 v8 直接与 MUI X v9 同步主版本。新增基于 Base UI 的 `NumberField` 与支持多级子菜单的 `Menubar`；利用 `color-mix()` 增强 CSS 变量派生颜色；`sx` 处理性能提升最高 30%，整体包体积减小约 3%；清理旧版 `component`/`componentsProps` 属性，为彻底移除 Emotion 依赖铺路。

- [React Server Components Your Way | TanStack Blog](https://tanstack.com/blog/react-server-components)：TanStack Start 将 RSC 视为类似 JSON 的可获取、可缓存数据流原语，复用 TanStack Query 与 Router 的缓存机制；并提出“复合组件”模式，通过插槽让客户端保留组件树控制权，按需嵌入服务器内容。官博迁移实测客户端 JS 减少约 153KB，TBT 从 1,200ms 降至 260ms。

- [Chrome 148 Beta 发布](https://developer.chrome.com/blog/chrome-148-beta?hl=en)：重点引入 CSS 容器查询优化、音视频原生懒加载、Android 端 Web Serial 支持及内置 AI 能力增强。

- [Google 宣布打击“后退按钮劫持”行为](https://developers.google.com/search/blog/2026/04/back-button-hijacking)：Google 将“后退按钮劫持”行为列入垃圾内容政策，违规站点将面临手动降权或算法打压。

## 文章

- [Web 动画中的挤压与拉伸原则](https://www.joshwcomeau.com/animation/squash-and-stretch/)：介绍如何将迪士尼经典的“挤压与拉伸”动画原则应用到 Web 开发中，提升微交互质感。

- [7 种实用的 CSS 视图过渡方案](https://css-tricks.com/7-view-transitions-recipes-to-try/)：分享 7 种实用的 CSS 视图过渡代码方案，涵盖从基础配置到高阶动画的实现。

- [垂直代码架构：按功能划分的优势](https://tkdodo.eu/blog/the-vertical-codebase)：探讨为什么按功能垂直划分比按技术类型水平划分的代码架构更具扩展性与可维护性。

- [HTML 原生音视频懒加载指南](https://engineering.squarespace.com/blog/2026/how-to-use-standard-html-video-and-audio-lazy-loading-on-the-web-today)：介绍如何使用 HTML 原生的 loading="lazy" 属性为视频和音频元素实现延迟加载以优化性能。

- [深入探讨浏览器内置 Intl API](https://polypane.app/blog/the-intl-api-the-best-browser-api-youre-not-using/)：介绍 Intl API 如何以零成本、高性能的方式处理多语言环境下的日期、数字及文本格式化。

- [原生 TypeScript 中的代数思维实现](https://cekrem.github.io/posts/effect-without-effect-ts/)：介绍如何在不引入 Effect-TS 的情况下，利用原生 TS 实现类型安全错误处理和显式依赖注入。

- [Building a Blog in TanStack (Part 1 of 2)](https://frontendmasters.com/blog/building-a-blog-in-tanstack-part-1-of-2/)：本文介绍了如何利用 TanStack Start 框架构建一个基于 Markdown 的博客系统，涵盖了服务器函数、动态路由及代码高亮等核心实现细节。

## CSS 新特性

- [Chrome 145+ 多列布局新特性](https://css-tricks.com/css-multi-column-layout-wrapping-features/)：介绍 Chrome 145+ 引入的 column-wrap 和 column-height 属性，实现多列布局的垂直折行。

- [使用纯 CSS 实现日期范围选择高亮](https://css-tricks.com/selecting-a-date-range-in-css/)：探讨利用 CSS 的 :nth-child(n of selector) 语法简化日期范围选择器的交互逻辑与样式实现。

## 趣站与工具

- [wterm：基于 Zig 和 WASM 的高性能 Web 终端](https://wterm.dev/)：一款由 Zig 驱动、基于 DOM 渲染的轻量级高性能 Web 终端模拟器。

- [Animata：近 200 个动画 React 组件](https://animata.design/)：免费开源的 React 动画组件集合，基于 Tailwind CSS 构建，专注背景、按钮、文本及小组件的动画增强，支持复制粘贴快速集成并灵活自定义样式。

- [React Photo Album：响应式照片库组件](https://react-photo-album.com/)：支持行、列或瀑布流布局的 React 照片库组件，兼容 React 18+ 与 SSR，提供 [示例](https://react-photo-album.com/examples/masonry) 与 [Playground](https://react-photo-album.com/examples/playground) 预览不同配置效果。

## Codepen

### Pure CSS Ripple Effect 纯 CSS 涟漪效果

<https://codepen.io/editor/NikxDa/pen/019d5e38-b114-74da-bc98-e8862a92ecca>

> NikxDa 结合了 CSS 滤镜、模糊、对比度和混合模式，营造出从文本底部向外辐射的涟漪效果。目前建议使用 Chrome 或 Safari 查看。

![](https://r2.cosine.ren/i/2026/04/651d1bb01565e58fa8bc70e7628320ed.webp)

### Chunky 3D Buttons  厚实的 3D 按钮

<https://codepen.io/Andrew-Fisher-the-decoder/pen/raMZQNe>

> Andrew Fisher 用这一系列厚实、塑料质感的按钮，带我们回到了 2010 年代，按压起来非常令人满足。

确实解压。

![](https://r2.cosine.ren/i/2026/04/29c0876324fd26d8e4dc02b50c7f3e46.webp)

### 使用 GSAP 创建有趣的弹性复选框

<https://codepen.io/jdillon/pen/WbGgJqz>

> Josh Dillon 为我们带来了一组充满电子感的用户界面设计：三个复选框在被勾选时会以霓虹灯般跳跃的动画效果亮起，取消勾选时则会平滑地暗去。

![](https://r2.cosine.ren/i/2026/04/afde5d03b72e0f35a9c7b2601dbda258.webp)

## Refs

- [Codepen Spark #505](https://codepen.io/spark/505)
- [React StatusCode Issue #470](https://react.statuscode.com/issues/470)
