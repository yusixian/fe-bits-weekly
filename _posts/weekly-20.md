---
title: FE Bits Vol.20 | 博客更新与 FEDAY 见闻，Shadcn Create 发布
link: weekly-20
description: 本期周刊记录了赴长沙参加 FEDAY 2025 的见闻与个人博客更新：移植 Fumadocs 风格的移动端目录、为图片加入 LQIP 并显著提升性能；前端动态包括 shadcn 3.6 推出可定制组件库、Storybook v7+ 构建或泄露 .env 的安全公告、TanStack Start 增加 Vue 支持、Chrome DevTools 144 支持单请求限速；技巧分享用 SVG vectorEffect 修复虚线缩放问题；精选多篇 React/CSS/WebGPU/GSAP 优质内容与 CodePen 作品。
catalog: true
lang: cn
date: 2025-12-21 22:15:00
categories:
  - 周刊
---

> 本期网址 https://blog.cosine.ren/post/weekly-20
> 本周刊更新时间期望是在每周天。
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。
> QQ 讨论小群 598022684，讨论前端技术 & 生活，也可在群里投稿自己的文章，随意加入，比较偏向粉丝群的性质～
> 本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。

今天是 2025 年 12 月 21 日，星期天。

这周相当的充实，去参加了 FEDAY 2025，之前没参加过这种活动，很好奇，加上反正今年去了好多活动，感觉这种活动偶尔参加一下还很有意思的，而且顺便也能去长沙旅游一趟，就去了。

参加完的感受是今年的主题特别特别多与 AI 相关的，可以看出 AI 对前端的助益是真的很大，我是比较 AI 乐观主义的，觉得 AI 能帮我省下来很多时间干我想干的事，并且也取代不了前端，但真的需要多进行学习，不断学习。

https://cos.afilmory.art/photos/MVIMG_20251220_090431

https://cos.afilmory.art/photos/IMG_20251219_183401

https://cos.afilmory.art/photos/IMG_20251219_182549

然后呢，这周将 [Fumadocs](https://www.fumadocs.dev/docs/ui) 里我很喜欢的移动端 header 目录搬到我的博客 [astro-koharu](https://github.com/cosZone/astro-koharu) 了，我很喜欢～

![移动端目录](https://r2.cosine.ren/i/2025/12/de3ae273e856a0b5105166b1e7d97fdf.webp)

然后为图片加上了 LQIP，写了 [在 Astro 博客中实现 LQIP（低质量图片占位符）](https://blog.cosine.ren/post/astro-lqip-implementation)

![LQIP_01](https://r2.cosine.ren/i/2025/12/40e44c8ac166183d5f823d7aa81fa792.webp)
![LQIP_02](https://r2.cosine.ren/i/2025/12/2e91463883247a340dc99ddc1c97ae74.webp)

然后将性能等，也优化了一下：

| 优化前                                                                               | 优化后                                                                               |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| ![性能优化前](https://r2.cosine.ren/i/2025/12/6260b997f694ec82699bb55ba5a12c9b.webp) | ![性能优化后](https://r2.cosine.ren/i/2025/12/e93f40c340a626c4ab72212a84cf6d5d.webp) |

## 生态与社区动态

- [shadcn 发布 3.6](https://ui.shadcn.com/docs/changelog)：借助新的 `npx shadcn create` CLI 或者 [New Project](https://ui.shadcn.com/create)，现在可以使用 Radix UI 或 Base UI 来创建你自己的定制 shadcn 组件库了。

![shadcn create](https://r2.cosine.ren/i/2025/12/6f81247bb1f1ccd42df35c4ae94557bc.webp)

- [Storybook 安全公告](https://storybook.js.org/blog/security-advisory/)：
  又一个 [CVE-2025-68429 7.3/10](https://github.com/storybookjs/storybook/security/advisories/GHSA-8452-54wp-rmv6?ref=storybookblog.ghost.io)， Storybook v7+ 版本构建时可能会不小心把 .env 打包进去。

- [Vue start by birkskyum · Pull Request #6055](https://github.com/TanStack/router/pull/6055)：继 React 和 Solid 之后，TanStack Start 又新增了对 Vue 的支持。

- [Throttle individual network requests](https://developer.chrome.com/blog/throttle-individual-network-requests?hl=en)：Chrome DevTools 144 版本可以让你单独对每个网络请求限速进行调试。

## 小贴士

写了这么一段代码，想要一段可随高度变化可控制间距的虚线。

```tsx
<svg
  className="pointer-events-none absolute bottom-0 left-px h-[calc(100%+1rem)] w-[1.5px]"
  viewBox="0 0 2 366"
  preserveAspectRatio="none meet"
  aria-hidden="true"
>
  <path d="M0.749978 365.5L0.750106 0" stroke="white" strokeOpacity="0.2" strokeWidth="1.5" strokeDasharray="5.25 5.25" />
</svg>
```

发现不对！高度特别小的时候挤在一块了。

咋办？使用 `vectorEffect="non-scaling-stroke"`

https://developer.mozilla.org/zh-CN/docs/Web/SVG/Reference/Attribute/vector-effect

non-scaling-stroke 的使用可以看这篇文章：[CSS vector-effect 与 SVG stroke 描边缩放](https://www.zhangxinxu.com/wordpress/2018/12/vector-effect-non-scaling-stroke/)

> MDN 的官方解释是：该值修改了笔触的方式。通常，笔触涉及在当前用户坐标系中计算形状路径的笔触轮廓，并用笔触颜料（颜色或渐变）填充轮廓。该值的最终视觉效果是笔触宽度不依赖于元素的变换（包括非均匀缩放和剪切变换）和缩放级别。

为什么不用 [`border-style: dashed;`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Reference/Properties/border-style) ？因为他没有办法定义线段的长度和大小，视不同实现而定。

```diff
             strokeOpacity="0.2"
             strokeWidth="1.5"
             strokeDasharray="5.25 5.25"
+            vectorEffect="non-scaling-stroke"
           />
         </svg>
```

完美实现！

| 使用 `vectorEffect="non-scaling-stroke"` 前                                  | 使用 `vectorEffect="non-scaling-stroke"` 后                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| ![前](https://r2.cosine.ren/i/2025/12/9c3a0cfd4fe806d978f0d7cdea031869.webp) | ![后](https://r2.cosine.ren/i/2025/12/d2caa5c99c35e45de7f4b8fed1f5944e.webp) |

## 文章与视频

- [React Compiler 的静默失败 (以及如何修复它们)](https://acusti.ca/blog/2025/12/16/react-compiler-silent-failures-and-how-to-fix-them/)：作者分享了在使用 React Compiler 过程中遇到的“静默失败”问题，即编译器在无法优化组件时不会报错，而是回退到标准 React 行为，这可能导致性能下降。为了解决这个问题，作者发现并利用了一个未文档化的 ESLint 规则 `react-hooks/todo`，通过将其设置为错误级别，可以在编译失败时中断构建过程。
- [使用 GSAP 构建响应式、滚动触发的曲线路径动画](https://tympanus.net/codrops/2025/12/17/building-responsive-scroll-triggered-curved-path-animations-with-gsap/)：这篇文章提供了一个好工具 [Paths & Control Points](https://codepen.io/betawaxx/pen/JoGZQLZ)，让开发者能够拖拽控制点实时调整曲线。
- [用 WebGPU 来造一场雪 | Cyandev](https://cyandev.app/post/make-a-snowfall-with-webgpu)：手把手教你如何用 WebGPU 在网页上下雪，兼顾性能与效果，让你的博客在圣诞带上节日色彩～
- [How to type React children correctly in TypeScript](https://blog.logrocket.com/react-children-prop-typescript/)：还在为 React 中 `children` prop 的 TypeScript 类型定义挠头？这篇博文介绍了如何在 React 应用中如何正确使用 TypeScript 定义 `children` prop 的类型。
- [Different Page Transitions For Different Circumstances](https://frontendmasters.com/blog/different-page-transitions-for-different-circumstances/)：这篇博文教你如何使用 `View Transitions`（视图转换）为多页应用程序（MPA）创建差异化的页面切换动画。
- [How AI Coding Agents Hid a Timebomb in Our App](https://acusti.ca/blog/2025/12/09/how-ai-coding-agents-hid-a-timebomb-in-our-app/)：一篇关于 AI 编程助手“无意间”在应用里埋下了一颗定时炸弹的故事：
  > 一个由 AI 编程助手（AI Coding Agent）删除的代码注释，导致一个关键的 `readOnly` 属性被移除，进而引发了 React 组件的无限递归渲染。更糟的是，React 19 的 `<Activity>` 组件将这个 Bug 隐藏了起来，使其在数分钟内都不会崩溃，极大增加了调试难度。作者通过痛苦的调试过程，最终发现罪魁祸首是 AI 删除了注释，以及自己没有为关键的结构性约束编写测试。文章强调了在 AI 辅助开发背景下，测试而非注释，才是确保代码质量和安全的关键。

## CSS 新特性

- [State, Logic, And Native Power: CSS Wrapped 2025](https://www.smashingmagazine.com/2025/12/state-logic-native-power-css-wrapped-2025/)：深入解读了 Chrome 团队发布的“[CSS Wrapped 2025](https://chrome.dev/css-wrapped-2025/)”年度总结报告，强调 CSS 正从单纯的样式语言向构建动态、强大应用的原生工具集转变，开启了一个激动人心的前端新时代。
- [Creating Scroll-Based Animations in Full view()](https://css-tricks.com/creating-scroll-based-animations-in-full-view/)：介绍了 CSS `animation-timeline` 属性中的 `view()` 函数，它允许开发者创建基于元素在滚动容器（scrollport）中可见性（visibility）的动画。
- [What Else Could Container Queries... Query?](https://css-tricks.com/what-else-could-container-queries-query/)：容器查询（container queries）可不止查询尺寸那么简单，未来还有更多可能性等待探索！
- [🎥 2025 年所有浏览器支持的 11 个 CSS 新特性](https://www.youtube.com/watch?v=55uUK-iJeNM)
- [Responsive List of Avatars Using Modern CSS (Part 2)](https://css-tricks.com/responsive-list-of-avatars-using-modern-css-part-2/)：是 “使用现代 CSS 创建响应式头像列表”系列的第二部分，主要探讨如何利用 `offset` 或 `transform` 属性，结合 `sibling-index()` 和 `sibling-count()` 等 CSS 函数，实现一个响应式圆形头像列表的布局。

## 工具

- [Andy Clarke’s Toon Text](https://stuffandnonsense.co.uk/toon-text/tool.html)：Andy Clarke 开发的一款卡通标题文本生成器，它可以生成具有卡通风格的文本，并提供 CSS 代码。
  [介绍文章](https://css-tricks.com/toon-title-text-generator/)还重点介绍了其核心功能 Splinter.js，它通过包裹每个字符的 <span> 标签，并加入 ARIA 属性，在实现逐字样式控制的同时，增强了可访问性，解决了传统工具可能导致辅助技术识别障碍的问题。

![](https://r2.cosine.ren/i/2025/12/ab482b28222826e47f5618422ab4f5fe.webp)

- Raycast 插件：https://www.raycast.com/j3lte/css-tricks
  介绍文章：[Search CSS-Tricks Raycast Extension](https://css-tricks.com/search-css-tricks-raycast-extension/)
  > 一个 Raycast 扩展，可以直接从本地计算机搜索 CSS-Tricks 文章。该扩展使用 WordPress REST API 获取实时搜索结果，提供了一种快速查找和复制文章 URL 的方法。单击结果会显示摘要并在浏览器中打开文章。

## Codepen 精选

https://x.com/Andersonmancini/status/2000589287515959496

> Anderson Mancini(@Andersonmancini): 🎵 太阳出来了 ☀️
> 我终于完成了将我的“终极镜头光晕”移植到 #threejs WebGPU 的工作。性能简直令人难以置信，因为现在 threejs 已经将遮挡查询直接集成到了渲染管线中。如果你需要知道某个物体是否被遮挡，只需直接向 threejs 查询即可。文档中有示例。
> 这样一来，我就不再需要光线投射器来检测遮挡了，这就是性能大幅提升的原因。
> 如果您想查看结果：https:// planpoint-webgpu.vercel.app

https://x.com/Andersonmancini/status/2000589289868931516

![](https://r2.cosine.ren/i/2025/12/2ed4fd7cb089993bee9270bdcb98a548.webp)

### CyberPopover 2025

https://codepen.io/jh3y/pen/yyNWGNG

> 在 Jhey Tompkins 这款 Codepen 中，点击闪烁按钮即可打开带有电子音效的 CyberPopover。作为 Jhey 的经典之作，这款 Pen 是可配置的！打开右上角的面板，即可进行设置。

![](https://r2.cosine.ren/i/2025/12/403b16f637bc713974df139ee1b554d0.webp)

### 无需 JavaScript 的 Lightbox（灯箱）

https://codepen.io/daviddarnes/pen/bNbagPy

> David Darnes 分享了一个快速演示，展示如何使用 Popover API 构建一个简单的照片灯箱，无需 JS，只需不到 30 行 CSS 代码。

![](https://r2.cosine.ren/i/2025/12/18647a9d75aaa24ece6ba9ca36b8b458.webp)

## Refs

- [React Status #456](https://react.statuscode.com/issues/456)
- [Frontend Focus Issue 722: December 17, 2025](https://frontendfoc.us/issues/722)
- [This Week In React #263](https://thisweekinreact.com/newsletter/263)
