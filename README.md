# GADE Content to WeChat

把视频、音频、字幕、访谈、新闻链接或原始文本，整理并改写成可发布的中文微信公众号文章。

从 `v1.1.0` 起，本 Skill 已合并 `gade-wechat-formatter` 的排版、微信预览与两端缩进能力，是 GADE 内容整理和公众号排版的唯一主入口。

这个 Codex Skill 强调两点：

- 忠实来源：先完整整理，再进行结构化改写；人物、时间、数字和公司公告需要核查。
- 可直接发布：生成标题、摘要、低 AI 感无字封面、按需提供正文配图，以及可复制到微信公众号编辑器的内联样式 HTML。

**[下载可直接安装的 v1.1.0 ZIP](https://github.com/jiangyifan587/gade-content-to-wechat/releases/download/v1.1.0/gade-content-to-wechat-skill-v1.1.0.zip)**

当前中文易读性与正文配图更新已在 `main`；下方 v1.1.0 ZIP 是历史版本。如需最新规则，请使用 Git 克隆或 Code → Download ZIP。

## 主要能力

- 支持 YouTube、Bilibili、播客、访谈、字幕、逐字稿、新闻与公司公告等来源
- 区分来源事实、直接引用、媒体观点与编辑性概括
- 重新组织文章逻辑，而不是逐句替换原文
- 使用自然、具体的中文，减少翻译腔与抽象名词堆叠
- 保留事实限制与来源归属，常规核查过程说明集中放在文末
- 生成 1 个推荐标题、4 个备选标题和公众号摘要
- 根据文章主题决定视觉方向，封面不强制套用 GADE 主色
- 封面默认无文字，并优先采用纪实、编辑摄影或克制的概念视觉，降低 AI 感
- 默认纯文字正文；用户需要时再规划或制作正文配图
- 输出适配微信公众号编辑器的内联样式 HTML
- 也可只排版已有正文，合并碎段并保留原文事实与结构
- 支持微信原生“两端缩进”的正文/落款分开复制方案

## 安装

### 方法一：Git 克隆

```bash
git clone https://github.com/jiangyifan587/gade-content-to-wechat.git
cp -R gade-content-to-wechat/gade-content-to-wechat ~/.codex/skills/
```

安装后重新启动 Codex，或新建一个任务，让 Codex 重新加载 Skills。

### 方法二：下载 ZIP

下载上方的安装包，或在 GitHub 仓库页面点击 **Code → Download ZIP**。解压后，把其中的 `gade-content-to-wechat` 文件夹复制到：

```text
~/.codex/skills/
```

## 使用方法

在 Codex 中直接说：

```text
使用 $gade-content-to-wechat，把这条视频改写成微信公众号文章：
[视频链接]
```

新闻或文章也可以：

```text
使用 $gade-content-to-wechat，把这篇新闻改写成 GADE 风格的微信公众号文章：
[新闻链接]

要求忠实原文，核查人物、时间与数字，生成标题、摘要、无字封面、正文配图建议和可复制的公众号 HTML。
```

如果已经有逐字稿或原文，直接粘贴内容即可。

已有成稿只需要排版时，仍然使用同一个 Skill：

```text
使用 $gade-content-to-wechat，只排版下面的文章。
保留原文完整，正文使用微信原生“两端缩进 8”，落款不缩进。
```

## 微信“两端缩进”兼容方案

微信复制粘贴可能保留字体、居中和边框，却清洗容器内边距、子元素边距、百分比宽度、透明边框或占位表格。因此，Skill 不会用叠加 CSS 来假装微信原生缩进。

需要手动缩进时，会在完整 HTML 之外同时交付：

1. `*-body-only.html`：开场分隔线、正文和来源说明。
2. `*-footer-only.html`：点赞转发提示、绿色横线、完结语、星标和社区 CTA。

先粘贴正文稿，只选中正文并在微信中应用“两端缩进 8”；再将落款稿粘贴到末尾，不要重新全选。这样可避免标准落款和 `62%` 宽绿色横线被二次压缩。

## 默认交付内容

1. 来源信息与事实核查说明
2. 推荐标题、4 个备选标题与摘要
3. 完整公众号正文
4. 低 AI 感、无文字封面
5. 正文默认不插图；按需提供配图建议或成图
6. 可复制到微信公众号的 HTML

## 仓库结构

```text
gade-content-to-wechat/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── assets/
│   ├── gade-brand-reference.png
│   ├── wechat-template.html
│   ├── wechat-body-only-template.html
│   └── wechat-footer-only-template.html
└── references/
    ├── editorial-workflow.md
    ├── source-workflow.md
    ├── style-guide.md
    └── visual-workflow.md
```

## 说明

- 对新闻、公司公告和可能变化的信息，Skill 会要求使用可核查的一手或权威来源。
- 生成图片时，版权、肖像权与商标使用仍应由发布者在正式发布前确认。
- 微信公众号编辑器可能过滤部分 CSS；模板因此采用以内联样式为主的排版方式。

## License

[MIT](LICENSE)
