---
title: FE Bits Vol.21 | 博客圣诞特效与 Moe Copy 更新，AntV 推出 Infographic
link: weekly-21
description: 本期分享了个人项目和前端技术动态，包括博客中实现的 CSS 低质量图片占位符（LQIP）、可开关的圣诞特效模块，以及 Moe Copy AI 插件的 v0.2.0 更新。同时介绍了 CSS 新特性如文本装饰内边距（text-decoration-inset）、锚点定位回退检测和容器样式查询，盘点了前端社区热点与实用工具。
catalog: true
lang: cn
date: 2025-12-31 21:49:00
categories:
  - 周刊
---

> 本期网址 https://blog.cosine.ren/post/weekly-21
> 本周刊更新时间期望是在每周天。
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。
> QQ 讨论小群 598022684，讨论前端技术 & 生活，也可在群里投稿自己的文章，随意加入，比较偏向粉丝群的性质～
> 本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。

今天是 2025 年 12 月 31 日，星期三。

元旦放假，周刊停更一期，所以今天更新上周天的。

年终总结在写了在写了，但是今天就不一定写的出来了。

## 个人项目

这周圣诞节，前端圈都没什么动静，不过正好我做了一堆自己项目的更新。

今天一总结，发现真不少啊。

发了一篇博客「[Worktrunk 完全指南：让 Git Worktree 和 Claude Code 和平共处](https://blog.cosine.ren/post/git-worktrunk-guide)」因为我非常喜欢这个工具于是写了一篇博文卖安利～

### 博客项目

首先是博客的一些更新

#### LQIP

一开始想在博客中，实现类似 [Minimal CSS-only blurry image placeholders](https://leanrada.com/notes/css-only-lqip) 的 CSS-only LQIP（低质量图片占位符），使用单个 CSS 自定义属性 --lqip 编码图片的模糊预览。

这篇文章的技术原理是使用 20 位整数编码图片信息（8 位 Oklab 基础色 + 12 位亮度分量），在 CSS 中通过位运算解码（`mod()`, `round(down)`, `pow()` 等），使用径向渐变叠加渲染模糊效果，配合二次缓动实现平滑过渡。

我选择简化一些的实现，不追求 CSS Only 了，因为打算先做博客内部的图片，文章内部的外部图片等后续优化的时候再一起做，放上最终效果在这里：

![](https://r2.cosine.ren/i/2025/12/40e44c8ac166183d5f823d7aa81fa792.webp)

![](https://r2.cosine.ren/i/2025/12/2e91463883247a340dc99ddc1c97ae74.webp)

需要运行一下 `nr generate:lqips` 就会生成一个 `lqips.json` 的 json 文件在 assets 下，若没有这个文件则不提供占位符～

https://blog.cosine.ren/post/astro-lqip-implementation

后续看到有人提出更好的实现，已加入 [TODO](https://cos.featurebase.app/p/feature-geng-hao-de-lqip)！

https://x.com/radishzz_/status/2002647033086464476

#### 圣诞特效

究～极～花里胡哨！！
圣诞节到了，想给博客加点节日氛围。最终实现了一套可开关的圣诞特效模块，包括雪花和彩灯以及圣诞配色方案～

雪花效果是从 Shadertoy 上的 [Just snow](https://www.shadertoy.com/view/ldsGDn) 学来的！
彩灯是参考 [Toby J 的 CodePen](https://codepen.io/tobyj/pen/QjvEex) 实现，优化调整了性能，调整为圣诞配色（红、绿、金）

我知道肯定会有人说花里胡哨所以我加了开关，欢迎品鉴～

https://blog.cosine.ren/post/astro-christmas-effects

![圣诞特效展示 1](https://r2.cosine.ren/i/2025/12/7a36339bd35536b9ea9621db6cd238a2.webp)

如果嫌弃干扰阅读了，可以点击开关关掉～

![圣诞特效展示 2](https://r2.cosine.ren/i/2025/12/e3cd9efe4bf5f40215566de09d537b58.gif)

注意看这个雪是双层的，内容容器夹在雪花中间，远景雪花在文章后面飘过，近景雪花在前面飘过，配合视差效果，感觉还挺满意的。

![圣诞特效展示 3](https://r2.cosine.ren/i/2025/12/cabfd68dc8313ff59d0c744ca224a6ed.gif)

上面的雪花特效是最初的版本，现在的版本是后来又做了一些优化。

https://x.com/_cosine_x/status/2004244071393714301

#### 使用指南和反馈

把[博客的使用指南](https://blog.cosine.ren/post/astro-koharu-guide)先简单搓出来了，然后换了一下切换昼夜模式的过渡动画，从左往右扫过去的感觉。
虽然说现阶段还不建议使用，但如果想 fork 出去改改还是都可以的，预计元旦假期我会重点进行重构和性能优化、然后开放一个清理后的仓库方便部署，到那个时候就可以玩耍了！

https://x.com/_cosine_x/status/2005653281541103707

然后发现 alma 的[反馈页面](https://feedback.alma.now/)看起来很棒，看了下是用的 featurebase.app
于是我也想试试这个，给博客主题做了一个反馈页面（有没有人用再说吧）：

https://cos.featurebase.app/

### Moe Copy AI 插件更新

Moe Copy AI 插件也大改版了，然后收到了好朋友的 PR！发布了 v0.2.0，变得越来越好用了

https://github.com/yusixian/moe-copy-ai/releases/tag/0.2.0

https://x.com/_cosine_x/status/2005191726290608638

PR 在原本的直接 fetch 的基础上，提供了「后台打开新 tab」和在「当前页面跳转」来获取
下一页按钮选择器改用 XPath，还新增了自动翻页功能，支持跨页批量抓取，感谢 [@hyoban](https://github.com/hyoban) 贡献的这个[PR #15](https://github.com/yusixian/moe-copy-ai/pull/15)。

![](https://r2.cosine.ren/i/2025/12/22489cee45cbea49bba41cb8acf413d4.webp)

欢迎使用！欢迎反馈！文档在[这里](https://moe.cosine.ren/docs)。

https://chromewebstore.google.com/detail/moe-copy-ai/dfmlcfckmfgabpgbaobgapdfmjiihnck

https://github.com/yusixian/moe-copy-ai

## 文章与社区动态

- [antvis/Infographic](https://github.com/antvis/Infographic)：蚂蚁集团 AntV 团队推出新一代声明式信息图表（Infographic）生成与渲染框架，旨在通过 AI 驱动让数据叙事更简单。

- [How I use AI agents to write code](https://nolanlawson.com/2025/12/22/how-i-use-ai-agents-to-write-code/)：好文，我也是这样转变的（？）或者说没有转变。有趣的是 AI 出来之后我觉得编码热情或者说想构建产品的欲望越来越强烈了。

- [Frontend Wrapped 2025: The 10 storylines that defined the year - LogRocket Blog](https://blog.logrocket.com/frontend-wrapped-2025/)：2025 年前端世界发生了不少大事，这篇文章盘点了那些塑造了这一年的十大热点。

- [Ever wanted to have a rotating rainbow segments border](https://www.patreon.com/posts/ever-wanted-to-147025063)：介绍并对比了使用 CSS `conic-gradient()` 与 SVG `<rect>` 两种技术实现旋转彩虹分段边框的方法。

- [require(esm) in Node.js: implementer's tales](https://joyeecheung.github.io/blog/2025/12/30/require-esm-in-node-js-implementers-tales/)：Node.js 核心贡献者 Joyee Cheung 深入解析 `require(esm)` 功能实现过程中遇到的关键挑战与解决方案。

## CSS 新特性

- [补全不足，CSS 锚点定位支持锚定容器回退检测了](https://www.zhangxinxu.com/wordpress/2025/12/css-anchor-container-query/)：Chrome 143+ 引入 CSS 锚点定位回退检测机制，可自动检测容器布局变化并动态切换定位方向，解决传统锚点定位在空间受限时的显示异常问题。

- [今日学习 CSS style()样式查询及其 range 范围语法](https://www.zhangxinxu.com/wordpress/2025/12/css-style-container-range-syntax/)：介绍了 CSS @container 的样式查询 (Style Query) 新能力，展示从变量匹配到范围语法 (Range Syntax)、再到针对自身元素匹配的进阶使用技巧。

### text-decoration-inset

- MDN：[text-decoration-inset](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/text-decoration-inset)
- 兼容性：实验性，文中仅提到 Firefox 146+ 下有效。
- 介绍文章：[text-decoration-inset is Like Padding for Text Decorations](https://css-tricks.com/text-decoration-inset-is-like-padding-for-text-decorations/)

https://codepen.io/mrdanielschwarz/pen/VYaPVgr

CSS 中的 `text-decoration-inset` 允许开发者像设置内边距一样裁剪文字装饰（如下划线）的左右边缘，从而实现文字装饰与文字内容的精确对齐。该属性支持 em 等相对单位，使装饰能随字体大小缩放，并且可以配合动画和过渡效果，创造出更多原生的、引人注目的文字装饰动态效果。

## 工具

- [BentoPDF](https://github.com/alam00000/bentopdf): 功能强大、注重隐私的开源 PDF 工具集，可自部署，提供超过 50 种 PDF 操作工具，覆盖编辑、转换、安全、优化等多个维度。

## Codepen 精选

### CSS-Only Stacking Cards

使用 CSS Scroll-Timeline 实现的卡片堆叠，无需 JavaScript：

https://codepen.io/karabharat/pen/YPWXqmx

https://x.com/i/status/2005503369222512856

![](https://r2.cosine.ren/i/2025/12/ca34d5f3371ded092938b025f2d235f4.webp)

### easy rainbow segments card border cases

https://codepen.io/thebabydino/pen/RNRPEqb

文章：[Ever wanted to have a rotating rainbow segments border](https://www.patreon.com/posts/ever-wanted-to-147025063)

实现一个由等分彩虹色段组成的旋转边框效果。作者指出当容器的宽高比远离正方形时，单纯使用 CSS 的 conic-gradient() 方法无法保持色段等分，且分隔线难以垂直于边框。因此，文章提出了更优的解决方案：使用 SVG 的 <rect> 元素来精确控制每个色段的形状和动画，从而获得更稳定、更完美的视觉效果。

![](https://r2.cosine.ren/i/2025/12/58b95038b527cd20177db153d47f73fc.gif)
