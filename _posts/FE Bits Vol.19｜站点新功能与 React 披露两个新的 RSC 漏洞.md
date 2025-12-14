---
title: FE Bits Vol.19｜站点新功能与 React 披露两个新的 RSC 漏洞
link: weekly-19
description: 本期周刊记录了站点新增“零后端”相关推荐与 AI 摘要；缓存增量构建、上线零开销。生态方面，RSC 披露新漏洞并已修复，Three.js r182 发布，Deno 2.6 推出 dx，TypeScript 7 原生工具链进展显著，CSS 多项新特性推进。
catalog: true
lang: cn
date: 2025-12-14 20:46:00
categories:
  - 周刊
---

> 本期网址 https://blog.cosine.ren/post/weekly-19
> 本周刊更新时间期望是在每周天。
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。
> QQ 讨论小群 598022684，讨论前端技术 & 生活，也可在群里投稿自己的文章，随意加入，比较偏向粉丝群的性质～
> 本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。

今天是 2025 年 12 月 14 日，星期天。

本周给我的博客站点增加了无需后端的相关推荐和 AI 摘要功能。

相关推荐是参考了这篇超赞的实现：

https://alexop.dev/posts/semantic-related-posts-astro-transformersjs/

用 transformers.js 在本地算“语义相似度”，自动挑出最相关的 5 篇文章。

然后自己又实现了一下，支持排除特定文章（比如周刊），还可以选择是否把“正文”也纳入计算：

- 只用标题+描述：速度飞快，适合文章多的情况，但不是很准。
- 加上正文：效果明显更好，就是生成会慢亿些。

```bash
# 使用 Snowflake/snowflake-arctic-embed-m-v2.0 计算 168 篇文章（标题+描述）的时间
Done! Generated similarities for 168 posts in 4.1s

# 使用 Snowflake/snowflake-arctic-embed-m-v2.0 计算 168 篇文章（标题+描述+正文）的时间
Done! Generated similarities for 168 posts in 219.3s
```

这速度差别有亿点大，但是我个人很喜欢带正文的结果，效果显然会更好。

那有没有更折中的方案呢？于是我决定再加一个跑 AI 摘要的功能，使用 [xsai](https://xsai.js.org/docs/packages/generate/text) sdk，本地 LM Studio 使用 `qwen/qwen3-4b-2507` 模型跑一遍，跑起来结果又快又好！新增文章通过缓存，只需要跑新增文章的摘要就行，而且效果跟使用正文差不多！

文章详情里还有个可折叠的摘要卡片，点开有打字机小动画（尊重无动画偏好）

都在构建时本地跑完 git 提交，线上零开销。后面会继续调模型和缓存等，优化一下，写的比较匆忙。

欢迎来试试新功能！精力有限还没有写部署文档等，但是有一篇尚未发布的让 AI 写的 [astro-koharu-使用指南](https://github.com/cosZone/astro-koharu/blob/main/src/content/blog/tools/astro-koharu-%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97.md)，可能会有错漏，但是大体配置上差不多，求 star ～

https://github.com/cosZone/astro-koharu

![跑出来的文件](https://r2.cosine.ren/i/2025/12/3262e3664b7525f5d3770b8d0fde419a.webp)
![AI 摘要](https://r2.cosine.ren/i/2025/12/b168de06cc98f80e26754f03e92c0f13.webp)
![相关推荐](https://r2.cosine.ren/i/2025/12/76252d37c923a25bdb5d68c8d2ef5dc7.webp)

很开心，忙里偷闲写这些东西，超级开心。

## 生态与社区动态

- [React Router's take on React Server Components](https://www.epicreact.dev/react-routers-take-on-react-server-components-4bj7q)：React Router 正在添加 RSC 支持。

> 你知道 React Router 正在添加对 React Server Components (RSC) 的支持吗？虽然目前还处于实验阶段，但距离正式发布已经非常接近了，而且我认为 React Router 对 RSC 的实现非常出色。

- [Three.js r182 released 📈](threejs.org/changelog/?r182)：进行了全面升级，核心改动包括迁移到 ESLint 9、引入 flat config、对 WebGLRenderer 与 WebGPURenderer 进行多项性能与功能优化（如更高效的阴影映射、EAC 纹理支持、VSM 代码重构），节点系统得到显著改进（支持更多类型、优化缓存、引入 float packing/unpacking），同时大量 bug 修复、文档清理与示例更新，整体提升了代码质量、可维护性与渲染效率。

https://x.com/threejs/status/1998816106728010050

一些官方示例：

https://x.com/threejs/status/1998816109223723084

- [Deno 2.6: dx is the new npx](https://deno.com/blog/v2.6)：Deno 2.6 通过引入 `dx`（类似 `npx`）简化了包二进制的执行，新增细粒度权限控制与权限代理，使用 Go 编写的 `tsgo` 加速 TypeScript 类型检查，并支持 Wasm 源码导入。安全方面加入 `deno audit` 与 `--socket`，改进依赖管理与脚本审批。

- [微软推出 VS Code Insiders 播客](https://code.visualstudio.com/blogs/2025/12/03/introducing-vs-code-insiders-podcast)：由 Visual Studio Code 官方团队打造，深度访谈开发者、产品经理以及社区贡献者，解密新特性、实验工具和 AI 驱动的工作流。

  > 想知道世界上最受欢迎的代码编辑器背后究竟发生了什么吗？ VS Code Insiders Podcast 将为你揭开神秘面纱，带你深入了解塑造 Visual Studio Code 未来的功能、决策和人员。

- [使用 Chrome DevTools MCP，让您的编码代理调试浏览器会话](https://developer.chrome.com/blog/chrome-devtools-mcp-debug-your-browser-session?hl=en)：Chrome DevTools MCP 终于能让你的 AI 编程助手直接介入浏览器调试了，更丝滑了！好耶！

> 如需将 chrome-devtools-mcp 服务器连接到正在运行的 Chrome 实例，请使用 --autoConnect 命令行实参来设置 MCP 服务器

> 注意： 在 Chrome M144 达到稳定版之前，您必须指定 --channel=canary

```json
{
  "mcpServers": {
    "chrome-devtools": {
      "command": "npx",
      "args": [
        "chrome-devtools-mcp@latest",
        "--autoConnect",
        "--channel=canary"
      ]
    }
  }
}
```

- [为您希望看到的网络功能投票](https://web.dev/blog/upvote-features?hl=en)：现在，你可以通过点赞 (upvote) 来影响你最想看到的 Web 特性啦！

WebDX 社区组织推出了一项新功能，允许开发者直接通过“点赞 (upvote)”来表达对特定 Web 特性的需求，以帮助浏览器厂商优先考虑开发。虽然点赞多不代表直接采纳，但开发者的需求将成为浏览器厂商决策的重要参考因素。

> 你是否曾经在 Can I Use 网站上看到某个你非常想使用的功能被标记为红色，然后恨不得直接戳戳浏览器厂商，说：“嘿，我需要这个功能！”？现在你可以了。

> WebDX 社区小组推出了一种新方式，让您可以直接表达哪些 Web 功能对您来说最重要。现在，您可以为希望在主流浏览器之间实现互操作的功能投票 。

> 从今天起，您可以在 web.dev、 caniuse.com 和 webstatus.dev 上找到这些已集成的点赞功能。其他平台，例如 MDN，也在研究类似的集成方案。

### React 在研究 React2Shell 过程中披露了两个新的 RSC 漏洞

[React 在研究 React2Shell 过程中披露了两个新的 RSC 漏洞](https://react.dev/blog/2025/12/11/denial-of-service-and-source-code-exposure-in-react-server-components)：CVE‑2025‑55184 与 CVE‑2025‑67779（高危 - 拒绝服务）以及 CVE‑2025‑55183（中危 - 源代码泄露）。这些缺陷可被恶意 HTTP 请求触发，导致服务器无限循环或泄露服务器函数内部代码。React 已在 19.0.3、19.1.4、19.2.3 版本中修复，受影响的框架与打包器（如 Next、React‑Router、Vite 等）亦需同步升级。

https://react.dev/blog/2025/12/11/denial-of-service-and-source-code-exposure-in-react-server-components

- 拒绝服务（高危）： CVE-2025-55184 与 CVE-2025-67779 (CVSS 7.5) 可被恶意 HTTP 请求触发，导致服务器无限循环
- 源代码暴露（中等）： CVE-2025-55183 (CVSS 5.3) 可能会泄露服务器函数内部代码，源代码中硬编码的 secret 可能会被暴露，运行时 secret 如 process.env.SECRET 不受影响。

官方解释称：

> 重大漏洞披露后，往往会发现后续漏洞。当一个重大漏洞被披露后，研究人员会仔细检查相邻的代码路径，寻找变种的利用技术，以测试初始缓解措施是否可以被绕过。
> 这种模式在整个行业中普遍存在。例如，在 Log4Shell 之后，随着社区对原始修复程序的审查，又报告了其他 CVE。额外的披露可能会令人沮丧，但这通常是健康应对机制的标志。

> 只有源代码中的 secret 才能被泄露。
> 源代码中硬编码的 secret 可能会被暴露，但运行时 secret 如 process.env.SECRET 不受影响。
> 暴露代码的范围仅限于服务器函数内部的代码，这可能包括其他功能，具体取决于捆绑器提供的内联支持程度。
> 一定要核对生产包。

https://nextjs.org/blog/security-update-2025-12-11

Next 用户可以使用 `npx fix-react2shell-next` 进行升级。

我看到这个消息的第一想法嘛，如下：

https://x.com/_cosine_x/status/1999356620732793076

https://x.com/_cosine_x/status/1999359307482300511

## Shopify Editions Winter 2026

这是每半年固定发布，用于介绍 Shopify 又做了哪些功能更新的网站！

性能和兼容性可能相对一般，但做了完整的移动端适配，纯炫技网页，浓缩了超多细节和彩蛋和 CSS 新特性。

https://www.shopify.com/editions/winter2026

[彩蛋 1](https://x.com/avstorm/status/1998853569936851292)：点击钥匙，会弹出一个新的无边框窗口来进行解锁。应该用到了[跨窗口通信](https://www.zhangxinxu.com/wordpress/2025/01/js-broadcast-channel-api/)

> 以前有一个类似的[尝试用 three.js 实现了这个跨窗口的粒子动画](https://juejin.cn/post/7306033185934622731)，我猜应该是和这个一个原理，[GitHub 仓库](https://github.com/bgstaal/multipleWindow3dScene)

![](https://r2.cosine.ren/i/2025/12/01162d230f16b2910b7710d15155a67e.gif)

彩蛋 2：解锁后这个窗口还能跟着原来的页面滚动。

![](https://r2.cosine.ren/i/2025/12/7546226e60f8ce11962da28800eadb8c.gif)

[彩蛋 3](https://x.com/wentingyong/status/1999230215097082200)：点击帽子

![](https://r2.cosine.ren/i/2025/12/9c230863dbf24faf4135dc3df2744c67.gif)

技术解析：

> [jhey ʕ•ᴥ•ʔ(@jh3yy)](https://x.com/jh3yy/status/1999131244345405664)：今年的版本页面真是太棒了——有太多精彩的细节了 👨‍🍳
> 很荣幸能参与其中，团队表现出色 👏
> 除了令人惊叹的 WebGL 技术之外，还巧妙地运用了 CSS 容器查询、计数器、过渡/动画和 SVG！

## 文章与视频

- [我在制作微型 GLSL 演示时学到的一系列技巧和技巧](https://blog.pkh.me/p/48-a-series-of-tricks-and-techniques-i-learned-doing-tiny-glsl-demos.html)：作者分享了自己在制作 512 字符限制的微型 GLSL（OpenGL Shading Language）图形演示过程中，积累的一系列图形渲染技巧与心得。

- [TypeScript 7 的进展 - 2025 年 12 月](https://devblogs.microsoft.com/typescript/progress-on-typescript-7-december-2025/)：TypeScript 团队把编译器和语言服务迁移到原生代码（代号 Project Corsa），现在已提供可在 VS Code 中使用的预览版。编辑器功能完整、性能提升显著，编译器在类型检查和增量构建上几乎全兼容 5.9，并实现十倍左右的速度提升。文章还列出了与 5.9 的差异、即将废弃的选项以及后续路线图，强调 6.0 将是基于旧代码的最后一次发布，之后所有重点转向 7.0。

  > 今年早些时候， [TypeScript 团队宣布，我们一直在将编译器和语言服务移植到原生代码](https://devblogs.microsoft.com/typescript/typescript-native-port/)， 以充分利用原生代码的优势，从而获得更佳的原始性能、内存使用效率和并行处理能力。这项工作（代号“Project Corsa”，即将更名为“TypeScript 7.0”）是一项意义重大的工程，但我们在过去的几个月中取得了长足的进步。我们很高兴向大家介绍目前的进展，并展示全新的 TypeScript 工具集如今的“真实”面貌。

- [Do's and Don'ts of useEffectEvent in React](https://slicker.me/react/useEffectEvent.html)：了解 React 新增的 useEffectEvent hook，用来在 Effect 中获取最新的 props / state 而不触发 Effect 重新执行。本文列举了它的使用场景、何时可使用与何时不可使用与迁移建议。

- [Manage a Next.js Monorepo with Prisma](https://blog.appsignal.com/2025/11/26/manage-a-nextjs-monorepo-with-prisma.html)：本文展示了使用 Next.js 与 Prisma 在 Postgres 上实现完整的 CRUD Pizza 订餐系统一套流程。（是比较完整的一篇实践，小项目这么折腾全栈是可以的，但是大项目的话，写后端需要慎重～）

- [2025 回顾：Web 性能有什么新变化？](https://www.debugbear.com/blog/2025-in-web-performance?utm_campaign=web-weekly)：轻松回顾 2025 年前端性能的变化与新工具，包括 Core Web Vitals 指标的跨浏览器推进、新的 Lighthouse 与 DevTools 检测能力、浏览器 API（如 Scheduler API、软导航观测）的演进、CrUX 和实时监测数据的细化、对图像格式（如 JPEG XL）的最新态势，结尾展望了 2026 年可能的方向（更多 AI 集成与更完整的软导航指标支持）。

- [Using CSS to fix the irradiation illusion](https://nerdy.dev/adjust-perceived-typepace-weight-for-dark-mode-without-layout-shift)：在深色背景下，白色文本会显得比同等粗细的黑色文本更粗。这种现象叫做“辐照错觉”（irradiation illusion），本文介绍了如何利用可变字体（variable fonts）的 `GRAD` 轴（grade axis）在不改变字形大小的情况下调整文本的可感知粗细。

- [Tailwind CSS: Targeting Child Elements (when you have to)](https://cekrem.github.io/posts/tailwind-targeting-child-elements/)：本文详细介绍了如何利用 Tailwind 的任意变体 (Arbitrary Variants) 和 `[&_selector]` 语法来实现子元素样式控制。

## CSS 新特性

- [CSS Wrapped 2025](https://chrome.dev/css-wrapped-2025/)：一份来自 Chrome 团队的年度 CSS 功能大盘点，看看明年你的 CSS 能玩出什么新花样！

https://chrome.dev/css-wrapped-2025/

![](https://r2.cosine.ren/i/2025/12/bbd61522ff87b2d9429540600e3fe669.webp)

- [Fit width text in 1 line of CSS](https://css-tricks.com/fit-width-text-in-1-line-of-css/)：CSS 新属性 `text-grow` 用一行 CSS 就能让文本自动填满容器宽度，告别过去的复杂方案，不过它还在实验阶段。

- [Scrollytelling on Steroids With Scroll-State Queries](https://css-tricks.com/scrollytelling-on-steroids-with-scroll-state-queries/)：使用 CSS 的新滚动状态查询，让网页故事像游戏一样交互。

- [CSS Scroll-Triggered Animations are coming to Chrome!](https://www.bram.us/2025/12/12/css-scroll-triggered-animations-are-coming-to-chrome/)：Chrome 浏览器将在明年初推出纯 CSS 实现的滚动触发动画。这是一种基于时间，并在特定滚动偏移量（scroll offset）触发的动画，与现有的滚动驱动动画不同。这项功能有望在 Chrome 145 版本正式发布，它将替代部分 `IntersectionObserver` 的用途。

- [CSS progress()函数简介](https://www.zhangxinxu.com/wordpress/2025/12/css-progress-function/)：本文介绍了 CSS 新增的 `progress()` 函数，它能将指定范围内的值映射为 0 到 1 之间的进度值，兼容性一般，还处于 Chrome 的实验阶段。

## 小贴士

使用 [scrollbar-gutter](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/scrollbar-gutter) CSS 属性可以为滚动条预留空间，防止滚动条出现或消失时布局发生偏移。

可以将 body （或任何其他容器元素）上的 `scrollbar-gutter` 属性设置为 `stable`，以确保始终为滚动条预留空间，防止布局偏移。

`scrollbar-gutter` 属性是 CSS 中一个相对较新的属性，自 2024 年 12 月起，主流现代浏览器都支持它。因此，可以放心地使用它来渐进式的提升网页的用户体验。

https://www.amitmerchant.com/one-css-trick-to-eliminate-scrollbar-layout-shifts/

## 工具

- [remend](https://vercel.com/changelog/new-npm-package-for-automatic-recovery-of-broken-streaming-markdown)：Vercel 推出新 npm 包 remend，自动修复流式 Markdown 的破碎语法，尤其适用于处理 LLM 等应用。提取自 Vercel 的 Streamdown 库，该库是 react-markdown 的即插即用替代方案，专为 AI 驱动的流媒体应用而设计。（PS：与 Streamdown 同类型的 [Simon He](https://x.com/simon_he1995) 的 [markstream-vue](https://github.com/Simon-He95/markstream-vue) 也很好！）

### React Grab

[React Grab](https://www.react-grab.com/blog/agent)：React Scan 的作者 Aiden 出的新工具，它允许你从应用组件中“抓取”上下文，并将其提供给你选择的智能体，以便进行详细的修改。

CLI 设置只需要在你的项目根目录下运行这个命令，将检测您的框架并自动添加必要的脚本。

```bash
npx grab@latest init
```

Claude Code 的设置的话，服务器通过 4567 端口运行，并与 Claude Agent SDK 接口连接。将以下脚本添加到 package.json 中：

```json
{
  "scripts": {
    "dev": "npx @react-grab/claude-code@latest && next dev"
  }
}
```

## Codepen 精选

### 霓虹正弦波效果 GLSL

> Fabio E Zola 的这段 GLSL 动画中，闪烁的正弦波脉动着。您可以暂停动画、截屏，或从顶部的控制面板切换像素比例。

![](https://r2.cosine.ren/i/2025/12/2673b2f8e847cd11f37714e71c559315.gif)

### 花瓣

https://codepen.io/rileyjshaw/pen/xbVQQGr

> Riley Shaw 分享了一朵梦幻般的 CSS 和 JS 花朵，花瓣如万花筒般旋转 🪷

![](https://r2.cosine.ren/i/2025/12/8a0df10caab02e9888e12a0a91dff989.gif)

### 伪 3D 旋转球切换（仅 CSS）

https://codepen.io/alvaromontoro/pen/xbVydXq

> Alvaro Montoro 巧妙地通过移动点阵图案来模拟旋转动画，这个“切换组件是用 HTML 和 CSS 创建的。没有图片，也没有 JS。”

![](https://r2.cosine.ren/i/2025/12/4b69790f736320068d65f4ac076b6c2a.gif)

## Refs

- [Codepen Spark #486](https://codepen.io/spark/486)
- [React Status Issue 454: December 3, 2025](https://react.statuscode.com/issues/454)
- [Node Weekly Issue 604: December 9, 2025](https://nodeweekly.com/issues/604)
- [React Status Issue 455: December 10, 2025](https://react.statuscode.com/issues/455)
- [Web Weekly #178](https://www.stefanjudis.com/blog/web-weekly-178/)
