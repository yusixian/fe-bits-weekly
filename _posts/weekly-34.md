---
title: "FE Bits Vol.34 | @antv npm 包供应链攻击，Tailwind v4.3 发布"
link: weekly-34
description: 本期周刊分享离职感慨与 AI 前景讨论等个人动态。社区焦点涵盖 Next.js 严重 WebSocket SSRF 漏洞（CVE-2026-44578）、TanStack OIDC 令牌泄露导致 84 个包投毒、AntV npm 供应链攻击，以及 Tailwind CSS v4.3 正式发布（新色板、webpack 插件等）和 Bun 合并 .claude 相关 PR。文章精选包括控制无限 CSS 动画的巧妙技巧、本地优先 Web 架构解析、Node.js 26 新特性概览、跨文档视图过渡的避坑指南等。CSS 新特性关注 Chrome 149 原生支持 Gap Decorations 与 Safari 26.5 新增 :open 伪类等。工具推荐集成 AI 配对的字体浏览工具 Find Font，趣站则呈现 Dave Holloway 极具个性的 WebGL 作品集。
lang: cn
date: 2026-05-19 20:23:11
categories:
  - 周刊
updated: 2026-05-19 20:23:11
---

+++primary 关于本周刊
> 本期网址 <https://blog.cosine.ren/post/weekly-34>
> 本周刊更新时间期望是在每周天。
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe)

本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。
+++

今天是 2026 年 5 月 19 日，星期二。

## 个人动态

五一给我玩爽了！还面基了砍砍和智子大佬呜呜呜，一大坨五一去日本游玩的照片，就不放在这里了，等有心情了再单独发博客吧，这期依旧短短的。

1. 闲逛发现的正佳广场啤酒交易站
：我什么世面没见过
：我去，这个我是真没见过，怎么啤酒交易站什么的还有涨跌的 x
![](https://r2.cosine.ren/2026/05-17-pdzqt75m.jpg)
2. 周末[和 bug 姐面基了](https://t.me/polebugisabug/377)！超开心！，bug 姐送的水晶超好看 ww
![水晶](https://r2.cosine.ren/2026/05-17-knfq6hap.jpg)
3. 一些感慨
得知前司产研设计全都 n+1 了，有点唏嘘，有些感慨，有点遗憾。

唏嘘在我走在 2 月底，没有为了年终奖而再待几个月，因为我想做更有意思的事儿，走得毅然决然，无缝入职新公司了。

但是当时我完全没想象到居然会直接解散了，我走的时候还很真情实感的伤心了一阵子因为同事都很好。

也就是说我的跳槽错过了前司年终奖和 n+1 赔偿，可能会是人生第一次的体验。但是后续我会怎么样呢？我不知道，也许拿着赔偿可以休息休息，然后再找。

当时跳槽的时候也是觉得之前的业务太没有意思了，能感觉得出来，而现在的公司干的非常快乐非常有满足感，各方面都很开心。

真是人生无常啊，有时候真的觉得人生会不会存在很多 if 线。

看到有个评论我感觉说得很好也比较认可：「也许你继续待下去可能会错过比年终奖跟 n+1 更重要的东西」

至少我现在在现在的公司待的很好很开心，我是很满足的。

一些碎碎念

<https://x.com/_cosine_x/status/2055542646563840314>

<https://x.com/_cosine_x/status/2053446680633307393>

### 项目

最近有些无精打采的，不过假期玩的很开心，开新项目和维护旧项目都很佛系

<https://x.com/_cosine_x/status/2053349127480844358>

<https://x.com/_cosine_x/status/2053471845702316094>

<https://x.com/_cosine_x/status/2054809477724180929>

## 社区动态

- [Next.js WebSocket SSRF 漏洞 CVE-2026-44578](https://x.com/modat_magnify/status/2054848379339837850)：Next.js 的 WebSocket upgrade handler 存在 SSRF 漏洞，影响多个版本，需立即升级。

![](https://r2.cosine.ren/2026/05-14-ikb8pjur.jpg)

- [Bun 合并 Rewrite Bun in Rust 的巨大 PR](https://github.com/oven-sh/bun/pull/30412)：+1,009,257 -4,024……

![](https://r2.cosine.ren/2026/05-14-tvf4lmjo.jpg)

- [Next.js Security Update](https://vercel.com/changelog/next-js-may-2026-security-release) | [TanStack Postmortem](https://tanstack.com/blog/npm-supply-chain-compromise-postmortem)
虽然是前阵子发过的了，但是合订本一下方便我发周刊（什么，原来我在更新吗 x）

> Next.js (CVE-2026-32485/6) 于 2026 年 5 月发布安全更新，修复 13 个安全公告，包括中间件/代理绕过（5 个）、拒绝服务（3 个，含上游 React 组件漏洞 CVE-2026-23870）、服务器端请求伪造（SSRF，1 个）、缓存中毒（2 个）与跨站脚本（XSS，2 个）。所有使用受影响版本（Next.js 13.x/14.x/15.x/16.x 及对应 react-server-dom-*）的用户应立即升级到修复版本（Next.js 15.5.18 或 16.2.6，React 相应版本）。仅打补丁可完全修复，WAF 无法可靠拦截。\

> TanStack (2026-05-11)：因 OIDC 令牌泄露被投毒 84 个包，一小时内被恢复，目标是窃取 AWS/SSH 等敏感密钥。只有 Router/Start 代码库受到影响，包含 42 个 monorepo 包，每个包有两个版本。所有包都在一小时内被弃用，并随后被 npm 移除。

- [Tailwind CSS v4.3 发布](https://tailwindcss.com/blog/tailwindcss-v4-3)：新颜色调色板、高性能 webpack 插件、滚动条样式、容器大小等。

- [@antv npm 包供应链攻击](https://socket.dev/blog/antv-packages-compromised)：npm 上 AntV 包被植入恶意代码，窃取环境变量和 npm token。

## 文章

- [控制无限 CSS 动画的技巧](https://frontendmasters.com/blog/how-to-control-infinite-css-animations-part-1-of-2/)：利用 animation-composition: add 叠加两个相同动画，实现无限动画的加速、减速、停止和反向。

- [PL Nerd 迎来惊天大变 Vibe Coder 喜提 AI 原生 - 某知乎文章](https://zhuanlan.zhihu.com/p/2039725076204016063)：非常离谱 hhhhh

- [本地优先 Web 开发架构深度解析](https://www.smashingmagazine.com/2026/05/architecture-local-first-web-development/)：基于实战经验剖析本地优先架构的核心概念、存储方案、同步与冲突处理及工程权衡。

- [使用 conic-gradient 实现方形点背景](https://frontendmasters.com/blog/repeating-square-dots-backgrounds-in-css/)：探讨如何利用 conic-gradient 高效实现背景透明的正方形重复网格点效果。

- [控制无限 CSS 动画平滑启停](https://frontendmasters.com/blog/how-to-control-infinite-css-animations-part-2-of-2/)：结合 animation-play-state 和 transition 实现无限循环动画的平滑启动与停止。

- [使用 CSS Offset 与 Border 制作标注 UI](https://frontendmasters.com/blog/callout-ui-with-css-offset-border/)：运用 offset-path 和边框技巧打造灵活且能随边框自动关联的 Callout 组件。

- [探索 HTML-in-Canvas 提案](http://tympanus.net/codrops/2026/05/13/exploring-the-html-in-canvas-proposal/)：深入探讨 WICG 提案：在 Canvas 中直接渲染保留 CSS 样式与可访问性的 HTML 元素。

- [使用 Obs.js 实现上下文感知性能优化](https://csswizardry.com/2026/05/meet-your-users-where-they-are-with-obs-js/)：通过浏览器信号（网络、电池等）动态调整 Web 体验。

- [Node.js 26 新特性概览](https://nodejsdesignpatterns.com/blog/whats-new-in-nodejs-26/)：稳定 Temporal API、Map.getOrInsert 语法糖、V8 14.6 等。

- [跨文档视图过渡的隐藏坑](https://css-tricks.com/cross-document-view-transitions-part-1/)：避开过时教程的坑，详解超时机制、图片拉伸及 pagereveal/pageswap 事件。

## CSS 新特性

- [CSS Gap Decorations 正式支持](https://developer.chrome.com/blog/gap-decorations-stable?hl=en)：Chrome 149 原生支持给 Flex/Grid 间隙添加分割线，告别伪元素和 Border Hack。

- [Safari 26.5 CSS 新特性概览](https://webkit.org/blog/17938/webkit-features-for-safari-26-5/)：带来 :open 伪类、random() element-scoped、锚点定位修复等。

## 工具

- [Find Font - 字体浏览与下载工具](https://www.findfont.co/)：集成实时比较与 AI 配对功能的免费字体浏览与下载工具，超过 5000 种字体。

## 趣站

- [Dave Holloway 的 WebGL 作品集](https://daveholloway.uk)：极具个性的 WebGL 作品集，拥有独特的瓷砖状扭曲效果和丰富的互动细节。

![](https://r2.cosine.ren/2026/05-16-5jy9a9jh.jpg)
