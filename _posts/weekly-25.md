---
title: FE Bits Vol.25 | Yarn 6 将用 Rust 重写，CSS Grid Lanes 进展
link: weekly-25
lang: cn
date: 2026-02-01 23:20:36
categories:
  - 周刊
updated: 2026-02-01 23:29:35
---

> 本期网址 <https://blog.cosine.ren/post/weekly-25>\
> 本周刊更新时间期望是在每周天。\
> 推荐订阅本周刊的 [RSS](https://blog.cosine.ren/rss.xml)。\
> 公众号 前端周周谈 FE Bits，点击阅读原文链接可查看原文。\
> QQ 讨论小群 598022684 / [Discord 群](https://discord.gg/XzvrvNMcSe)\
> 本周刊文章内容同时也开源在 [fe-bits-weekly](https://github.com/yusixian/fe-bits-weekly)，欢迎关注。

今天是 2026 年 2 月 1 日，星期天。

已经 2 月了啊，好快哦。

## 个人动态

### 碎碎念

看了超时空辉夜姬，给我看的好感动……好久没看到这么令人感动的国宴了……

简直是神，还是真百，推荐所有人观看美少女贴贴，在我心里是作画运镜无死角全方面的神作～

撒糖撒糖还是撒糖，后劲也大，全程都在库库截图，我没有什么不满的我觉得美少女特别有活力的贴贴特别好。

![太甜了吧！](https://r2.cosine.ren/i/2026/01/e4c28d8555e361e7bd0f9ee55e4838de.webp)
![两只小可爱！](https://r2.cosine.ren/i/2026/01/da6440716dc4a4cf25cf3d76ad422272.webp)

上一次看完有如此感慨的还是游戏人生剧场版……但是那个高度……

这部的优缺点都很明显，在强无敌的作画下剧情的平平无奇反而变成了短板，但是我觉得还是瑕不掩瑜，非常非常值得一看！

泛式说得好啊：

<https://www.bilibili.com/video/BV1Fcz1BZEVz>

这个杂谈说得也很好：

<https://www.bilibili.com/video/BV1w8zrBHEZC>

### 项目更新

给博客做了以下更新。

<https://github.com/cosZone/astro-koharu/releases/tag/v2.5.0>

<https://github.com/cosZone/astro-koharu/releases/tag/v2.5.1>

给 Moe Copy AI 插件做了深色模式，还在持续优化中。

<https://github.com/yusixian/moe-copy-ai/releases/tag/0.3.3>

![](https://r2.cosine.ren/i/2026/02/2b63baa07b19d4dd20d14233b7628790.webp)

## 社区动态

- [When will CSS Grid Lanes arrive? How long until we can use it?](https://webkit.org/blog/17758/when-will-css-grid-lanes-arrive-how-long-until-we-can-use-it/)：探讨了 CSS Grid Lanes（原生瀑布流布局）在各浏览器的实现进度，并详细介绍了如何通过渐进增强（Progressive Enhancement）技术在当下提前使用这一新特性。

  - Safari 已经在技术预览版中支持
  - Firefox 在 2020 年最早实现了早期草案，目前正致力于更新至最新的规范语法和 `flow-tolerance` 属性
  - Chrome 与 Edge 的加入：Chromium 团队在经历了语法争议后，目前已达成共识并正在更新其实现代码，标志着三大引擎达成一致。

- [Yarn 6 预览版发布](https://yarn6.netlify.app/blog/2026-01-28-yarn-6-preview/)，为了极致性能正转向使用 Rust 语言重构，预计 2026 年 Q3 发布稳定版。

- [Try text scaling support in Chrome Canary](https://www.joshtumath.uk/posts/2026-01-27-try-text-scaling-support-in-chrome-canary/)：介绍 Chrome Canary 中新增的 `<meta name="text-scale">` 标签，该功能允许网页响应移动端操作系统的全局字体大小设置。

- React 紧急发布 19.2.4、19.1.5 和 19.0.4 版本，修复了 React Server Components (RSC) 中未完全解决的拒绝服务 (DoS) 漏洞：[Denial of Service Vulnerabilities in React Server Components](https://github.com/facebook/react/security/advisories/GHSA-83fc-fqcc-2hmg) (真累啊)

- [Vercel 的最新研究](https://vercel.com/blog/agents-md-outperforms-skills-in-our-agent-evals)表明，在针对 Next.js 16 开发的最新评估中，他们发现将 8KB 的文档索引塞进 AGENTS.md 文件中效果更好，因为 skills 无法可靠地触发。

- SolidJS 创始人 Ryan Carniato 发布 [JavaScript Frameworks - Heading into 2026](https://dev.to/this-is-learning/javascript-frameworks-heading-into-2026-2hel)，分析当前充满活力的前端开发领域。

## 优质文章

- [Unstacking CSS Stacking Contexts — Smashing Magazine](https://www.smashingmagazine.com/2026/01/unstacking-css-stacking-contexts/)：非常好的好文章！条理清晰，深入剖析 CSS 层叠上下文 (Stacking Contexts) 的工作原理，解释为什么 `z-index` 会失效，并提供实用的调试技巧与解决方案。被安利了 [Better CSS Stacking Contexts](https://marketplace.visualstudio.com/items?itemName=mikerheault.vscode-better-css-stacking-contexts) 这个 vscode 插件。

- [There is No Need to Trap Focus on a Dialog Element](https://css-tricks.com/there-is-no-need-to-trap-focus-on-a-dialog-element/)：介绍在使用原生 `<dialog>` 元素时，为什么开发者不再需要手动实现复杂的焦点陷阱（Focus Trap）逻辑。

- [From pixels to characters: The engineering behind GitHub Copilot CLI’s animated ASCII banner](https://github.blog/engineering/from-pixels-to-characters-the-engineering-behind-github-copilot-clis-animated-ascii-banner/)：本文深入探讨了为 GitHub Copilot CLI 开发 3 秒 ASCII 动画背后的复杂工程实现，涵盖了终端渲染限制、色彩一致性及无障碍设计。
  ![](https://r2.cosine.ren/i/2026/02/a0bab00540fdb5e998994464a75cce10.webp)

### 10 Tips for Claude Code

https://x.com/bcherny/status/2017742759218794768

Claude Code 的开发者 Boris Cherny 分享了其使用 Anthropic 最新推出的 Claude Code 命令行工具的进阶技巧，涵盖自动化、调试、学习模式及多代理协作。

#### 1. 自动化与技能扩展（Skills & Automation）

- 建议将每日重复操作转化为自定义技能（Skills），并提交至 Git 仓库供跨项目复用。
- 创建 `/techdebt` 指令，在每个会话结束时运行，用于发现并消除重复代码。

#### 2. 高效调试与流程集成（Debugging & CI/CD）

- 启用 Slack MCP（Model Context Protocol），直接将 Slack 中的 Bug 讨论贴入 Claude 进行修复，减少上下文切换（Context switching）。
- 授权 Claude 自动修复失败的 CI 测试，或通过分析 Docker 日志定位问题，无需微观管理（Micromanage）。

#### 3. 提示词工程与代码评审（Prompting & Code Review）

- 让 Claude 扮演评审者（Reviewer），通过“对我提交的代码进行质询，直到通过测试再创建 PR”等提示词提升质量。
- 要求 Claude 对比主分支（Main branch）和功能分支的行为差异，证明代码的有效性。

#### 4. 环境配置与工具优化（Environment & Setup）

- 推荐使用 Ghostty 终端以获得更好的同步渲染和 24 位色彩支持。（我用 warp 也很好用）
- 使用 `/statusline` 自定义状态栏，实时显示上下文使用情况（Context usage）和当前 Git 分支。

#### 5. 复杂任务与数据分析（Subagents & Analytics）

- 在请求中加入 “use subagents” 指令，让 Claude 投入更多算力（Compute）处理复杂问题，并保持主代理上下文整洁。

- 通过编写技能调用 BigQuery (bq) 等命令行工具，直接在 Claude Code 中进行实时数据指标分析。

#### 6. 深度学习与知识内化（Learning & Understanding）

- 在 `/config` 中开启“解释模式”（Explanatory/Learning output style），让 Claude 解释代码变更背后的原因（Why）。 (我觉得这个解释模式真的好用)
- 利用 Claude 生成视觉化的 HTML 演示文稿（Slides）或 ASCII 图表，辅助理解陌生的代码库或协议。
- 构建间隔重复（Spaced-repetition）学习技能，通过问答形式填补知识盲区。

### 新特性

- [如何为新的 ::search-text 和其他高亮伪元素设计样式](https://css-tricks.com/how-to-style-the-new-search-text-and-other-highlight-pseudo-elements/)：介绍 Chrome 144 新推出的 `::search-text` 伪元素，以及如何利用 CSS 相对颜色语法统一美化各种文本高亮样式。

- [告别 insertBefore，使用 moveBefore 移动 DOM 元素](https://www.zhangxinxu.com/wordpress/2026/01/insertbefore-movebefore-dom/) 介绍了原生 DOM 新 API `moveBefore` 的用法、优势及其在 Web Components 中的应用，并对比了传统 `insertBefore` 的局限性。

## 工具

- [agentation](https://github.com/benjitaylor/agentation)：一款为 AI Agents 设计的视觉反馈工具，通过点击并添加标注，随后生成包含元素路径、CSS 选择器（Selectors）、位置等详细上下文的 Markdown 文本。[文档](https://agentation.dev)| [Tweet](https://x.com/benjitaylor/status/2014109590972145908)

![agentation 演示](https://r2.cosine.ren/i/2026/01/7707ab61737d10cd6788684bd391b8ee.webp)

- 这个 [MarginLab](https://marginlab.ai/trackers/claude-code/) 挺有意思的，一个针对 Claude Code 和 Codex 的独立性能监控工具，模拟真实用户编码场景来监测大模型的“降智”，

<https://x.com/vikingmute/status/2017495789443199126>

## 趣站与 Codepen 精选

### React Tilt Button - 3D Tactile React Button Component

好喜欢这个！感觉是很巧妙的设计。
一个具备 3D 触感、支持倾斜和深度效果的 React 交互按钮组件。它利用 CSS 的 3D 变换（3D Transforms）技术，为传统的按钮元素注入了物理深度（Depth）和动态倾斜（Tilt）效果。组件不仅内置了从复古游戏（Arcade）到现代金属（Steel）等多种预设主题，还开放了高度细粒度的自定义参数，让开发者可以轻松调整按钮的海拔高度（Elevation）、圆角（Radius）及光泽感（Glare），从而打造出极具表现力的用户界面。

https://react-tilt-button.vercel.app/

![](https://r2.cosine.ren/i/2026/02/7b566e0382bffe8ecafba88829007a02.webp)

GitHub 源码

https://github.com/archisvaze/react-tilt-button

### Super Monkey Ball

开发商 Twilight 将[世嘉经典游戏《超级猴子球》移植到网页上](https://example.com)，做得非常出色且运行流畅。

https://bsky.app/profile/twilightpb.bsky.social/post/3mdbynphtbc2l

![](https://r2.cosine.ren/i/2026/02/d94a3de701caad8680595c0835025a67.webp)

https://monkeyball-online.pages.dev/

可以查看[源代码](https://github.com/sndrec/WebMonkeyBall)。

### Typewriter Web Component V2

https://codepen.io/luis-lessrain/pen/EaKjXwB

目前该项目仅在 CodePen 上提供，但它的效果非常出色。演示允许您交互式地启动、暂停/恢复、完成和重置动画。此外，还有一个进度条和按钮，可以跳转到特定的进度点。

![](https://r2.cosine.ren/i/2026/02/78044015d16e7335da5a0cfc3bd00e7d.webp)

## Refs

- [Frontend Focus #726](https://frontendfoc.us/issues/726)
- [React Status #460](https://react.statuscode.com/issues/460)
