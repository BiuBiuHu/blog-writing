# Blog Writing

[English](README.en.md)

一个用于真实实践写作的 Codex skill。把经历、代码和发布记录整理成中英文博客，并在获得授权后完成 HTML 配图、阅读验证和发布。

它保留作者为什么做、怎样改变选择、哪里还没解决。不会强制把每篇经历改成原则清单、标准导读或总结金句，也不承诺搜索排名。

## 能做什么

- **写作与改稿**：从一手材料核实事实，保留用户确认的动机、名称和手动修改，章节使用阿拉伯数字。
- **中英文表达**：完整博客交付默认提供两版，英文自然重写，核对数字、单位、引用与不确定性；只要单语或片段时按请求执行。
- **解释性配图**：用 HTML/CSS 排版，浏览器渲染后截图为 PNG；分别适配两种语言，检查裁切和文字溢出，保留可编辑图源。
- **发布验证**：检查手机阅读、语言切换、图片加载与放大、元数据及已有 RSS/sitemap；已提交候选先预览，再按项目门禁发布生产。
- **版本追溯**：核对源码、CI产物、平台版本和正式入口，保留回滚点与实际验证记录。

这是指令与参考资料包，不是独立运行的博客程序。它使用 agent 已具备的文件、Git、浏览器和部署能力；不会自动安装工具、购买服务或创建云资源。

## 安装到 Codex

尚未安装同名 skill 时：

```bash
git clone https://github.com/BiuBiuHu/blog-writing.git "${CODEX_HOME:-$HOME/.codex}/skills/blog-writing"
```

也可以通过 Codex 的 `skill-installer` 从本仓库安装，指定仓库根目录作为 skill 路径、名称 `blog-writing`。已存在同名目录时，先备份并检查差异，不要直接覆盖。

安装后在下一轮对话使用 `$blog-writing`。

## 使用示例

写作：

> 用 $blog-writing 把这次开发经历写成文章，保留真实的判断过程，少写方法论和段末总结。先给中文稿，不发布。

改稿与双语整理：

> 中文稿已经确认。按 $blog-writing 整理中英文两版，解释图用 HTML 排版后截图，章节用数字编号。先落盘并本地验证。

完整发布：

> 按 $blog-writing 将中英文文章和配图放进现有博客，验证后发布。

“写稿”“放进博客”和“公开发布”是不同范围。明确授权验证后发布时会继续完成已授权步骤，不反复索要同一授权。后续独立文章不会因为安装了这个 skill 就自动公开。

## 工作流程

1. 确认项目、素材及作者认可的版本。
2. 写作或改稿，完成对应范围的中英文表达。
3. 制作 HTML/CSS 解释图，真实导出并查看 PNG。
4. 核对事实、元数据、图片路径、桌面和手机阅读。
5. 在获授权的发布任务中，提交候选并验证隔离预览。
6. 按项目门禁发布默认分支候选，复验正式入口与版本。

不会固定文章字数、章节数或图片数量。教程与实践叙事可采用不同结构，具体站点从项目配置读取。

## 文件

| 文件 | 用途 |
|---|---|
| [SKILL.md](SKILL.md) | 入口、写作偏好、范围与发布流程路由 |
| [文章质量标准](references/editorial-quality.md) | 读者收益、真实叙事、详略和 AI 味检查 |
| [双语与发布流程](references/bilingual-publishing-workflow.md) | HTML 配图、本地/预览/生产验证及版本追溯 |
| [站点适配检查](references/site-context.md) | 从目标项目发现目录、语言和部署约定 |
| [Codex 元数据](agents/openai.yaml) | 展示名称与调用提示 |

## 项目适配

Astro 的 `src/content/blog/`、`-en.md` 是常见约定，不是硬编码要求。使用前读取目标博客 schema、模板、语言路由及CI。已有 Vercel、Cloudflare 或其他发布方式都沿用项目配置。

仓库不包含任何部署凭据、云账号配置、用户数据、私有文章或截图工具。发布验证需要当前 agent 拥有对应能力与权限；未执行的检查必须如实记录。

## 实践来源

这套流程经过中英文博客写作、HTML 配图与发布验证迭代：

- [用了 Grok Bot 之后，我们为什么把安排日历迁到 Cloudflare](https://www.peak-lake.com/blog/grok-bot-vercel-cloudflare)
- [English: Why We Moved Anpai Calendar to Cloudflare After Starting to Use Grok Bot](https://www.peak-lake.com/en/blog/grok-bot-vercel-cloudflare)

## 许可证

[MIT](LICENSE)。
