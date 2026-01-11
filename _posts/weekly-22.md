---
title: FE Bits Vol.22 | CSS @scope 全面可用，ViteLand 12 月回顾
link: weekly-22
description: 本期包含个人与项目进展：Discord 公群开放，Koharu 主题 v2 发布并上架 Astro 商店，新增 Koharu CLI（备份/还原、主题更新、内容生成、备份管理），Moe Copy AI 上架 Firefox；技术侧聚焦 CSS @scope 全面可用与 ViteLand 12 月回顾（Oxc 数十倍性能、Vite 8 Beta 原生插件、Vitest 引入 OpenTelemetry 与 fs 缓存、Rolldown 优化分块与选项）；精选 Temporal、Web Install API、现代 Hooks、包体积减重、加速计/Three.js/WebGL 动效等文章；工具与灵感涵盖 DiceBear、在线抖动器及 GitHub .png/.keys 小技巧，另荐 Addy Osmani 14 年 21 条职业经验与多款趣站/CodePen 作品。
catalog: true
lang: cn
date: 2026-01-11 19:30:00
categories:
  - 周刊
---

> 本期网址 https://blog.cosine.ren/post/weekly-22 \
> 本周刊更新时间期望是在每周天。 \
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。\
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。\
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe) \
> 本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。

今天是 2025 年 1 月 11 日，星期天。

年终总结在写了（还在写？）

建了个 discord 群，虽然不怎么上 discord（）

https://discord.gg/XzvrvNMcSe

因为后知后觉的意识到 Discord 群作为公开群好像比较合适比较方便（嗯）

总之想找我聊天或者问问题的都可以加，后续应该会作为各种项目里边 link 的公开群。

然后是博客主题更新，新增了 Koharu CLI 交互式命令行工具，提供博客内容备份/还原、主题更新、内容生成、备份管理等功能。配置文件也统一更改为 config/site.yaml 了。

https://github.com/cosZone/astro-koharu/releases/tag/v2.0.0

![](https://r2.cosine.ren/i/2026/01/388028f78817bf496d1c8223ef4b26b4.gif)

然后觉得还挺有意思的，之后准备写一篇博客简单讲讲（实现交互式 Git 主题更新 CLI 的完整方案）

![](https://r2.cosine.ren/i/2026/01/2867558b13c393a4e16b4f9c6ca186a2.webp)

上架了 astro 主题商店，发了一篇 v2ex 帖子。

https://astro.build/themes/details/koharu

https://v2ex.com/t/1184086

并且 Moe Copy AI 插件上架火狐商店了（没想到不怎么需要适配）

https://addons.mozilla.org/zh-CN/firefox/addon/moe-copy-ai/

## 社区动态

### CSS `@scope` 规则已广泛可用

CSS `@scope` 已获得所有主流浏览器支持，该规则允许您选择特定 DOM 子树中的元素，精确定位元素，而无需编写难以覆盖的过于具体的选择器。

- MDN：[@scope - CSS | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/At-rules/@scope)
- 文章：[How to @scope CSS Now That It’s Baseline](https://frontendmasters.com/blog/how-to-scope-css-now-that-its-baseline/)

用法形如

```css
@scope (.article-body) to (figure) {
  img {
    border: 5px solid black;
    background-color: goldenrod;
  }
}
```

### ViteLand 12 月回顾

[What’s New in ViteLand: December 2025 Recap](https://voidzero.dev/posts/whats-new-dec-2025)：ViteLand 生态在 2025 年 12 月迎来了一系列重要更新，涵盖了 Vite、Vitest、Rolldown、Oxc 等项目。

Oxlint 和 Oxfmt 如今已能取代传统工具，而且还在不断改进。可以查看 [2026 年路线图](https://github.com/oxc-project/oxc/issues/17411)

期待能在项目里广泛使用的那天！

1.  Oxc 的性能突破

    - Oxlint 和 Oxfmt 在代码校验（linting）和格式化（formatting）方面提供比 ESLint 和 Prettier 更快的速度（分别快 50-100 倍和 30 倍）。
    - Oxlint 已推出 1.0 版本，并新增了类型感知校验（type-aware linting）和兼容 ESLint 的 JS 插件。
    - Oxfmt 新增了对嵌入式语言和实验性导入排序的支持。
    - Bun、Vue、Preact、date-fns、Inquirer.js、Shopify、Miro、Airbnb 等多个项目已迁移至 Oxc。
    - Oxc 团队计划在 2026 年推出对动态配置（dynamic configs）的支持。
    - Oxc 在性能优化方面持续投入，实现了语义分析性能的提升。

2.  Vite 项目更新

    - 发布了多个 Vite 8 beta 版本，修复了 bug 并提升了稳定性。
    - Vite 8 beta 提供了第二版原生插件（native plugins），改进了动态导入（dynamic import）和导入 glob（import glob）插件的对齐。

3.  Vitest 项目更新

    - 新增实验性的 OpenTelemetry 支持，用于分析测试性能瓶颈。
    - Vitest UI、CLI 和 VS Code 扩展支持分析和分解导入，识别减慢测试速度的依赖。
    - 支持通过 `experimental.fsCache` 缓存转换后的文件，加速后续测试运行。

4.  Rolldown 项目更新

    - 支持通过手动指定 `tsconfig` 来使用 TypeScript 项目引用（TypeScript project references）。
    - 优化了默认的代码块（chunking）算法，减少了生成的代码块数量。
    - 提供了 `postBanner` 和 `postFooter` 选项，用于在打包后的代码前后追加内容。
    - 插件的 `resolveId` 钩子支持通过 `importerId` 进行过滤，提高性能。

5.  社区动态与合作
    - Framer 发布了关于使用 Rolldown 改进性能的案例研究。
    - TypeScript.fm 和 Syntax.fm 播客讨论了 ViteLand 项目的更新和发展预测。
    - Ninja Squad 撰写了关于使用 Vitest 浏览器模式测试 Angular 的文章。
    - 社区涌现出多个基于 Oxc 和 Rolldown 的新工具和迁移案例，如：
      - `oxlint-plugin-complexity`：用于校验代码复杂度的 Oxlint 插件。
      - `Roll(down)phobia`：基于 Rolldown 的包大小分析工具。
      - RSC Explorer：使用 Vite 8 和 Rolldown 构建的 RSC（React Server Components）工具。
      - Facetpack：使用 Oxc 替换 Babel 的 React Native 工具。
      - MonkeyType：迁移到 Oxlint 以获得更快的类型感知校验速度。
      - create-better-t-stack：从 Biome 迁移到 Oxlint 和 Oxfmt。
      - Ultracite：提供基于 Oxc 的预设配置。
      - rollipop：完全基于 Rolldown 的 React Native 构建工具。

## 文章与社区动态

- [Building a toast component](https://emilkowal.ski/ui/building-a-toast-component)：Emil 分享了制作  [Sonner](https://sonner.emilkowal.ski/)  时候的设计思路与技术实现，太细致了。

- [包大小调查：一步一步缩小 JavaScript 的指南](https://www.developerway.com/posts/bundle-size-investigation)：相当实用的好文，教你怎么减小打包体积，分析 JavaScript 打包大小、优化导入方式、解决重复库和处理传递依赖。

- [React 已发生变化，您的 hook 也应如此](https://allthingssmitty.com/2025/12/01/react-has-changed-your-hooks-should-too/)：当前主流项目仍以传统方式使用 React Hooks（如滥用 useEffect），忽视了 React 在并发模式与异步数据处理上的演变。作者从设计理念出发，提出现代 Hook 的核心精神是“架构化的状态与逻辑管理”，强调使用 `useSyncExternalStore`、`useDeferredValue`、`useEffectEvent` 等新 API 优化性能和可测试性，鼓励开发者更多关注派生状态（derived state）而非副作用（side effects）

- [AI 编码代理如何在我们的应用中隐藏定时炸弹](https://acusti.ca/blog/2025/12/09/how-ai-coding-agents-hid-a-timebomb-in-our-app/): AI Agent 写代码的时候无意中在应用程序中引入了一个隐藏的、导致浏览器崩溃的无限 React 组件树，而 React 19 的 `<Activity>` 组件则巧妙地掩盖了这个问题。

- [require(esm) in Node.js: implementer's tales](https://joyeecheung.github.io/blog/2025/12/30/require-esm-in-node-js-implementers-tales/)：Joyee Cheung 是 Node.js 的核心贡献者之一，长期以来一直致力于 Node.js 对 `require(esm)` 的支持（即使用 require 加载 ES 模块）。在这篇系列文章中，她分两部分详细阐述了 `require(esm)` 实现历程及其具体细节。

- [超越鼠标：使用移动加速计制作动画](https://frontendmasters.com/blog/beyond-the-mouse-animating-with-mobile-accelerometers/)：探讨了如何利用移动设备的加速计和运动传感器为网页动画注入动态交互，从而在移动设备上实现与桌面端鼠标交互相媲美的沉浸式用户体验。
  （这个我两年前有做过类似的需求，也叫陀螺仪，iOS 必须请求陀螺仪权限才能用，除了这个缺点，整体上其实用起来挺舒服的）

- [A first look at the Web Install API](https://frontendmasters.com/blog/a-first-look-at-the-web-install-api/)：探讨了新兴的 Web Install API，该 API 已在 Chromium 浏览器中进入 Origin Trial 阶段，并在 Microsoft Edge beta 版中展现出最完整的功能。此 API 的目标是允许网站通过简单的按钮点击直接安装 PWA (Progressive Web Apps)。相关链接: [The Web Install API is ready for testing](https://blogs.windows.com/msedgedev/2025/11/24/the-web-install-api-is-ready-for-testing/)

- [Important and CSS Custom Properties](https://frontendmasters.com/blog/important-and-css-custom-properties/)：澄清了 CSS 自定义属性 (`CSS Custom Properties`) 中 `!important` 的作用机制，指出 `!important` 修饰的是声明本身而非其值，从而避免常见误解。

- [用 WebGL 着色器构建实时 ASCII 和抖动效果](https://tympanus.net/codrops/2026/01/04/efecto-building-real-time-ascii-and-dithering-effects-with-webgl-shaders/)：很厉害的 ASCII 艺术生成网站 https://efecto.app/ 之前发过，这篇是作者的详细技术解析。

- [无限画布：建立一个无缝的，平铺任何地方的图像空间](https://tympanus.net/codrops/2026/01/07/infinite-canvas-building-a-seamless-pan-anywhere-image-space/)：很详细的教程，详细介绍了如何使用 React Three Fiber 构建一个无限可平移的图像画布，通过区块 (chunk) 渲染和性能优先的技术，创建一个流畅且可无尽探索的图像空间。

![](https://r2.cosine.ren/i/2026/01/b42a0836b926029e589b98995214216f.webp)

- [超越 RxJS: TanStack Pacer 指南](https://blog.logrocket.com/beyond-rxjs-guide-tanstack-pacer/)：讲了怎么使用 TanStack Pacer 来管理前端应用中的异步事件时序，以优化性能并避免 RxJS 的复杂性。

- [VSCode 的 6 种快速的（原生）替代方案](https://blog.logrocket.com/native-alternatives-vscode/)：本文探讨了广受欢迎的 VSCode 因其基于 Electron 的架构所带来的性能局限性，并介绍了六款用 C++、Rust 等原生语言开发的快速、高效的替代编辑器。

- [程序员和整洁的 Home](https://www.geedea.pro/essays/clean-home/)：如何通过遵循 XDG Base Directory Specification (XDG BDS) 来整理混乱的 Home 目录，从而更好地管理配置文件、数据和缓存文件。

- [Vitest Browser Mode - The Future of Frontend Testing](https://howtotestfrontend.com/resources/vitest-browser-mode-guide-and-setup-info)： 介绍了 Vitest Browser Mode，可以在真实浏览器环境中进行前端组件测试。

## 新特性

- [重要信息 #2：条件视图转换、CSS/SVG 文本特效、最佳 CSS Bluesky 等](https://css-tricks.com/whats-important-2/)：回顾了 2025 年末 CSS 领域的一些重要进展、新特性、社区讨论以及行业动态，并展望了 2026 年的趋势。

- [Date is out, Temporal is in](https://piccalil.li/blog/date-is-out-and-temporal-is-in/?ref=articles-rss-feed)：一篇 Temporal 的介绍。JavaScript `Temporal` 是 `Date` 的完美替代方案，已进入 TC39 标准化过程的第三阶段 (Stage 3)，在 Chrome 和 Firefox 等主流浏览器的最新版本中落地实现。

- [2026 年每个前端开发者都应该知道的 4 个 CSS 特性](https://nerdy.dev/4-css-features-every-front-end-developer-should-know-in-2026?utm_source=rss)：介绍了前端开发者在 2026 年应该掌握的四个重要 CSS 新特性，包括 `sibling-index()`、`@container scroll-state()`、`text-box` 和 `typed attr()`。

## 工具

- 做友链功能的时候发现的，还挺好用的：[DiceBear](https://github.com/dicebear/dicebear) 是一个功能强大的头像库，旨在帮助设计师和开发者快速为项目创建多样化的头像。它提供了从抽象形状到精心设计的人物角色等多种头像风格。用户不仅可以生成随机头像，还可以通过设定 seed 实现确定性头像生成，或利用丰富的定制选项创建个性化头像。DiceBear 通过 JavaScript 库、HTTPS API、命令行工具 (CLI)、Figma 插件和在线 Playground 等多种方式提供。

- [Dither Image Online](https://ditherimage.online/)：一个免费、快速、实时的在线抖动（dithered）图像生成器，或者说像素艺术风格，效果太酷了！

![](https://r2.cosine.ren/i/2026/01/5bff5c48402d8f31baff6664b658431f.webp)

- 你知道吗？可以通过在 GitHub 个人资料页面 URL 后添加 `.png` 来获取你的 GitHub 个人资料图片，例如 `github․com/USERNAMEHERE.png` - 还可以附加 `.keys` 来获取公钥，附加 `.atom` 来获取公开时间线活动的动态。[Refernce](https://bsky.app/profile/cassidoo.co/post/3mbs2sqipuc25)

## 趣站与 Codepen 精选

### GACHAGO! MarbleRace

非常可爱的网站！看了看首页还有很多有趣的东西

是一个基于物理模拟的弹珠台式抽奖工具，灵感来源于游戏内的抽奖玩法，通过模拟物理碰撞（例如红色柱子增加弹力）来决定结果，使得抽奖过程更具趣味性和不可预测性。

![](https://r2.cosine.ren/i/2026/01/ea73017f59b01b1c427a860da51c21eb.webp)

https://www.gachago.net/MarbleRace

https://x.com/Mant0uStudio/status/2009279695276089512

作者是 [@Mant0uStudio](https://x.com/Mant0uStudio)

### Mr. Panda's Psychologically Safe Portfolio

很有创意的一个滚动驱动的 portfolio 页面：[Mr. Panda's Psychologically Safe Portfolio](https://www.mr-pandas-psychologically-safe-portfolio.com/)

- 开源在：[GitHub - andrewwoan/mr-pandas-psychologically-safe-portfolio](https://github.com/andrewwoan/mr-pandas-psychologically-safe-portfolio)
- 技术解析文章：[The Increasing Importance of Psychological Safety and Self-Awareness for Creative Work](https://tympanus.net/codrops/2025/12/30/the-increasing-importance-of-psychological-safety-and-self-awareness-for-creative-work/?_thumbnail_id=107253)

![](https://r2.cosine.ren/i/2026/01/2f73902c267d3f94972cbf124ed7af7b.webp)

### 像素化图片掉落特效

[How to Create a Pixel-to-Voxel Video Drop Effect with Three.js and Rapier](https://tympanus.net/codrops/2026/01/05/how-to-create-a-pixel-to-voxel-video-drop-effect-with-three-js-and-rapier/)

这个教程详细介绍了如何利用 Three.js、着色器和 Rapier 物理引擎，将 2D 视频流转化为动态的 3D 体素 (voxel) 下落效果。文章从核心概念——像素和重力——出发，逐步讲解了如何构建一个由 `InstancedMesh` 和刚体 (rigid bodies) 组成的平面，通过着色器实现平铺像素到 3D 体素的涟漪 (ripple) 变形效果，并最终通过 JavaScript 模拟涟漪进程来激活物理引擎，使体素在逼真的物理作用下散射和恢复。作者还分享了实现过程中的技术细节、优化考量以及未来扩展的可能性。

![](https://r2.cosine.ren/i/2026/01/9945061fadee6845fa2eaf24796b5756.webp)

### Bongo Cat Codes #2 - Jamming

好萌，被萌到了

https://codepen.io/carolineartz/pen/qBOEzQa

![Bongo Cat Codes #2](https://r2.cosine.ren/i/2026/01/e0f7bfdff20d71ab1a258f9346972134.webp)

### 果冻压扁按钮

> 你需要预留一点时间来压扁这个东西。无论是垂直拖动光标，还是单击 "跟随鼠标 "复选框，都可以将这个由 Voicu Apostol 制作的内含果冻的按钮的压扁效果与鼠标移动联系起来。

https://codepen.io/cerpow/pen/LEZYxqM

好可爱的按钮！看了一下原理。

这不是真正的 3D 果冻，而是通过快速切换预渲染的图片序列来模拟果冻挤压效果，类似电影胶片的原理。预加载了 215 张连续的果冻形变图片，这些图片记录了果冻从静止到被挤压到回弹的完整动画过程，通过切换不同帧号的图片来做的。

![](https://r2.cosine.ren/i/2026/01/2e8bfc8d0c7b929a26ba63df6ddfacec.webp)

### 文本框边框动画旋转 [CSS & SVG] V2

> 在 Fernando Cohen 制作的这个流畅的 CSS 和 SVG 动画中，文字栅栏围绕着一张照片的边缘。看看悬停照片时会发生什么，还可以看看他的 [2022 年的早期迭代作品](https://codepen.io/designfenix/pen/gOGVXWw)。

https://codepen.io/designfenix/pen/OPyapww

![](https://r2.cosine.ren/i/2026/01/626dbe1ad688022823daf884f69eeb36.webp)

看了一下原理，这是一个使用 SVG 和 CSS 创建的**文字沿着有机形状边框旋转动画**效果。

首先使用 **SVG Blob 形状生成**，创造有机的 blob 形状

```svg
<path d="M43.1,-68.5C56.2,-58.6,67.5,-47.3..." />
```

这个路径数据可能来自 [Blob Generator](https://www.blobmaker.app/) 等工具

然后是使用 clip-path 进行**图片裁剪**，将矩形图片裁剪成 blob 形状，同时通过 `preserveAspectRatio="xMidYMid slice"` 确保图片填充满整个区域。

```svg
<clipPath id="blobClip">
  <path d="..." transform="translate(100 100)"/>
</clipPath>
<image clip-path="url(#blobClip)" />
```

然后使用 `pathLength` 进行**文字路径动画**，定义文字路径

```svg
<path id="text" d="..." fill="none" stroke="none" pathLength="100" />
```

- `pathLength="100"` 标准化路径长度，便于动画计算
- `fill="none" stroke="none"` 路径本身不可见，仅作为文字轨迹

将文字沿路径排列：

```svg
<text class="text-content">
  <textPath href="#text" startOffset="0%">
    ❤ MADE WITH LOVE ❤ MADE WITH LOVE...
    <animate attributeName="startOffset"
             from="0%" to="100%"
             dur="15s"
             repeatCount="indefinite" />
  </textPath>
</text>
```

- `<textPath>` 让文字沿着指定路径排列
- `startOffset` 控制文字在路径上的起始位置
- `<animate>` 元素实现 SMIL 动画（SVG 原生动画）

那无缝循环是怎么做的呢？他用了两段文字，当第一段文字从 0% 移动到 100% 时，尾部会消失，第二段文字从 -100% 移动到 0%，正好填补空白。两段文字首尾相连，形成无缝循环。

```svg
<!-- 第一段文字：0% → 100% -->
<textPath href="#text" startOffset="0%">
  <animate from="0%" to="100%" />
</textPath>

<!-- 第二段文字：-100% → 0% -->
<textPath href="#text" startOffset="100%">
  <animate from="-100%" to="0%" />
</textPath>
```

最后是这个 **交互式缩放效果**，是通过悬停时放大裁剪区域（而非整个 SVG）来做的。

![](https://r2.cosine.ren/i/2026/01/605f335c304c6e98761fc87d3199ef86.webp)

## 文摘

### 在谷歌工作 14 年的 21 条经验

最近读的有一篇文章感觉很棒，所以单独列出来。

每一条都是我赞同的！写得真好啊。

https://addyosmani.com/blog/21-lessons/

Addy Osmani 在 Google 14 年的职业生涯中，总结出 21 条经验教训。

1.  以用户为中心

    - 真正的价值来自于深入理解并解决用户问题，而非仅仅热衷于技术本身。
    - 通过参与客服、与用户交谈、观察用户痛点来深入理解问题。

2.  协作与对齐

    - “对”固然重要，但“一起达成对”才是真正的挑战和价值所在。
    - 避免成为“房间里最聪明的人”，应创造空间让他人参与，并对自己的观点保持适度怀疑。
    - 绝大多数“慢”的团队实际上是“错位”的团队，即方向、接口或优先级不明确。

3.  行动与交付

    - 完美的追求会阻碍进步，先行动、再完善、再优化。
    - “行动导向”比“分析瘫痪”更能带来清晰度，可编辑错误页面，但无法编辑空白页面。
    - AI 可以辅助快速迭代和反馈。

4.  清晰度而非技巧性

    - 代码需要清晰易懂，以便他人（尤其是在紧急情况下）能够理解和维护。
    - 为维护者（包括 2 AM 时的你）而非自己写代码。

5.  谨慎创新

    - 创新是有成本的，应谨慎使用“创新代币”。
    - 只在有独特价值的地方创新，其他地方应倾向于使用成熟、可靠的技术。

6.  价值的可视化与倡导

    - 优秀的成果需要被看见，代码不会替你说话，人会。
    - 要让你的影响对他人可见，尤其是在你不在场时。

7.  代码的最小化

    - 最“好”的代码是你根本不需要写的代码。
    - 在构建之前，思考“如果我们不这样做，会发生什么？”。

8.  兼容性即产品

    - 在大规模系统下，即使是 bug 也会成为用户的依赖。
    - API 设计实际上是 API 退休设计，需要考虑兼容性、时间和用户体验。

9.  聚焦可控因素

    - 在大型组织中，很多变量不可控，应专注于自己的影响范围。
    - 保持理智和高效的关键在于聚焦可控之事。

10. 抽象的代价

    - 抽象会转移复杂性，而非消除它，当问题发生时，你仍需要理解底层。
    - 持续学习“更低级”的知识，以应对抽象失效的情况。

11. 教学即学习

    - 写作和教学是促进理解的有效方式，能暴露自己知识的不足。
    - 尝试用简单的方式解释事物，是检验和深化理解的捷径。

12. “粘合剂”工作的价值与可见性

    - 文档、入职、跨团队协调等“粘合剂”工作至关重要，但容易被忽视。
    - 要将这些工作视为可见的影响，而非仅仅是“乐于助人”。

13. 避免轻易获胜

    - 如果总是轻易获胜，可能意味着积累了“沉默的阻力”。
    - 真正的对齐需要时间、理解和妥协，而非赢得争论。

14. 度量与目标

    - 任何被量化的指标都会被“博弈”。
    - 在衡量时，应同时关注速度和质量/风险，并注重趋势分析。

15. 承认未知

    - 领导者承认“我不知道”能创造一个更安全的环境，鼓励团队成员也敢于提问。
    - 好奇心和承认未知才能促进团队学习。

16. 人脉网络

    - 人脉是你最重要的长期资产，远比任何一份工作都持久。
    - 以好奇和慷慨的态度建立和维护人脉。

17. 性能提升源于移除

    - 许多性能提升来自于移除不必要的工作，而非增加技术复杂度。
    - 最快的代码是那些从不运行的代码。

18. 流程的本质

    - 良好的流程应简化协调、降低失败成本，而非制造官僚主义。
    - 如果流程的价值无法解释，它可能只是负担。

19. 时间价值

    - 职业生涯后期，时间成为比金钱更宝贵的资源。
    - 有意识地权衡时间和回报，避免过度追求金钱而牺牲宝贵的时间。

20. 复利效应

    - 专业技能的提升需要刻意练习和时间积累，没有捷径。
    - 将职业生涯视为复利增长，而非购买彩票，持之以恒会带来长远回报。

21. 核心思想
    - 保持好奇心、谦逊，并始终记住工作关乎人（用户和团队成员）。
    - 工程师的职业生涯足够长，可以从错误中学习，并分享经验。

## Refs

- [Codepen Spark #490](https://codepen.io/spark/490)
- [科技爱好者周刊（第 380 期）：为什么人们拥抱"不对称收益" - 阮一峰的网络日志](https://www.ruanyifeng.com/blog/2026/01/weekly-issue-380.html)
- [Web Weekly #179](https://webweekly.email/archive/web-weekly-179)
- [Node Weekly #606](https://nodeweekly.com/issues/606)
