---
title: "FE Bits Vol.33 | Vercel 四月安全事件、sizes auto 终结响应式图片之痛"
link: weekly-33
description: 社区焦点：Vercel 因第三方 AI 工具遭入侵披露安全事件；sizes="auto" 全面支持，响应式图片手写 sizes 时代终结。文章精选 Git 2.54 实验性 git history、Shopify 性能优化与 2026 技术 SEO 指南。趣站推荐 WebGPU 百万级草叶景观 False Earth 与纯 CSS 重现 Vision Pro 动画。
lang: cn
date: 2026-04-26 22:00:00
categories:
  - 周刊
updated: 2026-04-26 22:43:00
---

+++primary 关于本周刊
> 本期网址 <https://blog.cosine.ren/post/weekly-33>
> 本周刊更新时间期望是在每周天。
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe)

本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。
+++

今天是 2026 年 4 月 26 日，星期日。

## 随便聊聊

> 最近感觉写的有点没意思了，开一个随机聊聊的小栏目，随机推荐一些我觉得不错的东西，不限于技术方面的等，有可能是小知识，有可能是一段话，也有可能是我很久以前用过的觉得还不错的东西这周又看到了，也有可能我就是胡言乱语想聊聊什么。

如何活的开心？这是一个很轻松的话题。

- 该吃吃该喝喝，对花钱让自己获得快乐不要有心理负担～
- 自己的身心健康是最重要的，并不是鼓吹消费主义，而是不要连为自己花钱都会感觉有罪恶感。
- 不开心了想休息就休息，想摆烂就摆烂
- 少比较，比较是偷走幸福的小偷
- 有一个能令自己幸福的支点，可能是一个人、一个兴趣爱好、一个目标等等，能让自己在不开心的时候有个寄托的东西。（没错，没事儿喜欢跑跑编译也可以是一个支点）

关于对象

- 经常会在网上看到各种形形色色的人，由于各种原因经常会嚎找不到对象/这辈子就这样了等的消极对象主义言论。
- 抛开狗叫的因素不谈，有对象的前提自然是你也要努力成为一个值得被爱的对象，想想自己都不喜欢自己了，那别人为什么要喜欢你呢？
- 并且对象这件事，就算有了也绝对不可能是完美的，世界上没有完全适合自己的人，所以不要过于苛求对象，想想自己也不完美，别人也不完美，能找到一个愿意和你一起努力的就不错了。
- 最重要的一点：不要把任何事情当成自己人生的全部，人生还有很多其他的东西，比如朋友、家人、兴趣爱好等等，不要把所有的幸福都寄托在一个人身上，这样压力太大了，也不公平。

言尽于此，祝大家都能找到自己的幸福，不管是对象还是其他的东西，都希望大家能过得开心快乐！

## 个人动态

本周末提前进入度假状态，技术没看多少，讲真该把标题改成 Cosine Weekly Bits （笑死）
在玩异环，从去年中 BW 就开始期待到现在了，终于上线了，场景太戳我了，感觉我很大一部分是冲着场景和二次元来玩的，惊艳的风景，并且雨天、雪天、晴天、日出日落各有各的美，而且能航拍。

![](https://r2.cosine.ren/i/2026/04/4e0d6e9c3e2db7aac4843606383b6ad7.webp)

偶然发现的樱花树场景，配合当时的天气。

![](https://r2.cosine.ren/i/2026/04/c2b7342872707f5e363bb46f3cae9c3e.webp)
![](https://r2.cosine.ren/i/2026/04/8dd54ce74840fb2af0fc6638829a8c0f.webp)

偶然发现的铁路轨道……

![](https://r2.cosine.ren/i/2026/04/1e95a54e6b508603f13b07c92e7d88b2.webp)

偶然在日落的时候，传送到一个传送点，有一种平静的美好感。

![](https://r2.cosine.ren/i/2026/04/2082b66bb73fdd5b1391e40ce6c6e2fa.webp)
![](https://r2.cosine.ren/i/2026/04/ea3f7c0477719e7c422c8b0750a96934.webp)

支线的教堂彩窗……原谅我截图的画质一般，实机很惊艳。

![](https://r2.cosine.ren/i/2026/04/b73401f19aa4206be9aa5ec795c6f9f1.webp)

已买好大平层。

![](https://r2.cosine.ren/i/2026/04/07e95efdeb60dc4e3da135dca02c67c9.webp)
![](https://r2.cosine.ren/i/2026/04/d079a856291e58f285f9daafc78b5e5c.webp)

这游戏的都市是真的让人觉得活在其中的，这个没得说，所有店铺都能无缝直接进入，boss 设计也很惊艳，比如开车开车开着开进海底隧道那个异象了。

有时候觉得自己真是太幼稚了，玩个游戏、看看每月的新番、吃吃好吃的，就满足了，如此往复二十多年。

跟妹妹聊天的时候，感慨现在的大学生也还是跟以前一样有很多破事儿，下周五一假期就要去日本旅游一整个假期了，很期待。

## 社区动态

- [What's New in WebGPU (Chrome 147-148)](https://developer.chrome.com/blog/new-in-webgpu-147-148?hl=en)：介绍了 Chrome 147 与 148 版本中 WebGPU 的最新功能更新，重点包括 WGSL 索引扩展及 Linux 平台支持优化。

- [Vercel April 2026 security incident](https://vercel.com/kb/bulletin/vercel-april-2026-security-incident)：Vercel 披露 2026 年 4 月因第三方 AI 工具导致的内部系统及环境变量泄露事件。本次安全事故源于 Vercel 员工使用的第三方 AI 工具 Context.ai 遭到入侵，攻击者借此接管该员工的 Google Workspace 账号并渗透进 Vercel 内部系统。事件导致部分客户存储在 Vercel 上的 Environment Variables 被非法读取。目前 Vercel 已联合 Google Mandiant 等专家完成修复，确认 npm 软件包未受影响，并强烈建议相关用户立即轮换（Rotate）凭证并开启多因素认证（MFA）。

- [The end of responsive images](https://piccalil.li/blog/the-end-of-responsive-images/)：响应式图像标准的制定者 Mat Marquis 宣布，随着浏览器对 `sizes="auto"` 特性的全面支持，开发者终于可以告别手动计算并编写复杂 `sizes` 属性的痛苦。

## 文章

- [Constructable Stylesheets and adoptedStyleSheets: One Parse, Every Shadow Root](https://frontendmasters.com/blog/constructable-stylesheets-and-adoptedstylesheets-one-parse-every-shadow-root/)：深入解析 Web Components 中如何通过可构造样式表实现 CSS 的高效复用与单次解析，优化内存占用与渲染性能。

- [Git 2.54 实验性命令 git history 详解](https://cekrem.github.io/posts/git-history-git-2-54/)：探讨 Git 2.54 引入的 git history 命令，介绍其如何通过“确定性执行”哲学简化历史修改逻辑并避免冲突。

- [Shopify 店铺性能优化实战指南](https://www.debugbear.com/blog/shopify-speed-optimization)：深入探讨 Shopify 性能优化的核心瓶颈，提供从图片压缩、JS 延迟加载到字体子集化等一系列实战修复方案。

- [2026 年技术 SEO 完整指南](https://www.debugbear.com/blog/technical-seo-checklist)：详细讲解在 AI 搜索时代如何通过技术手段优化网站抓取、索引及性能，助力面向生成式引擎的优化 (GEO)。

- [使用 shape() 函数反转 CSS 形状](https://css-tip.com/invert-shape/)：介绍如何利用 clip-path: shape() 配合 evenodd 填充规则，通过简单的变量切换实现形状的正反反转效果。

![](https://r2.cosine.ren/2026/04-24-xaupjyz7.jpg)

## 工具

- [Math Curve Loaders：基于数学曲线的加载动画集](https://github.com/Paidax01/math-curve-loaders)：一个基于数学公式生成的加载动画集合，支持多种曲线类型与实时参数调节，兼具数学美感与实用性。

![](https://r2.cosine.ren/2026/04-25-w778gd0c.jpg)

- [jameskerr/react-arborist](https://github.com/jameskerr/react-arborist)：React 生态中功能完备的树形视图 (Tree View) 组件，旨在提供媲美 VSCode 侧边栏、Mac Finder 或 Figma 图层面板的用户交互体验。

## 趣站

- [False Earth：WebGPU 驱动的百万级草地景观](https://false-earth.mingjyunhung.com/)：利用 WebGPU 和 Three.js 构建的拥有数百万根交互式草叶的无限程序化景观，展示了高性能图形渲染的演进。

![](https://r2.cosine.ren/2026/04-22-rrxp1m51.jpg)

- [Recreating Apple’s Vision Pro Animation in CSS](https://css-tricks.com/recreating-apples-vision-pro-animation-in-css/)：探讨如何仅使用现代 CSS（如滚动驱动动画）重现苹果 Vision Pro 官网复杂的滚动拆解动画，并实现响应式适配。

<https://codepen.io/undeadinstitute/pen/bNweEOB>

![](https://r2.cosine.ren/i/2026/04/b8771a5c742c070d7f2e9c6cf81d12ed.webp)
