# HTML转PPT Skill

这是一个用于“一键生成 HTML + 可编辑 PPTX”的 ChatGPT / Codex skill。

核心目标：先用 HTML 承载高质量视觉排版，再从同一套页面规格生成同版式 PowerPoint，尽量保留文字、表格、图表、箭头、标签等可编辑元素，同时把复杂图片、设备图、科学示意图作为独立可移动/可替换的图片或 SVG 对象放入 PPT。

默认风格是白底、深海军蓝 `#12355B`、高密度投研/投委会风格。对外或跨平台使用时，中文默认微软雅黑，英文和数字默认 Arial，整套文件尽量不超过两种字体；只有明确限定为用户本人 Mac/Keynote 使用时，中文才切换为苹方，英文和数字仍使用 Arial。

## 适合什么场景

- 想让大模型一次性输出一个自包含 `.html` 和一个同版 `.pptx`
- 想用 HTML 做视觉设计，但最终仍需要可编辑 PowerPoint
- 需要图像丰富、逻辑清楚、适合投资建议书/行业研究/技术路线/市场空间/竞争格局的页面
- 不希望 PPT 只是整页截图、PDF 转换或纯文本卡片

## 仓库结构

```text
.
├── README.md
├── .gitignore
└── html-to-ppt/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── assets/
    │   ├── base-slide.html
    │   └── icon.svg
    └── references/
        ├── content-visual-standard.md
        ├── cross-platform-compatibility.md
        ├── design-system.md
        ├── html-ppt-contract.md
        └── universal-model-prompt.md
```

`html-to-ppt/` 是真正的 skill 文件夹。上传 GitHub 时请保留这个目录结构。

## 安装方式

把 `html-to-ppt/` 这个文件夹作为 skill 安装到你的 ChatGPT / Codex skills 目录或通过支持的 Skills 导入入口安装。

如果你用的是本地 Codex 环境，通常可以把整个 `html-to-ppt/` 文件夹复制到个人 skills 目录中，然后在新对话里用：

```text
@html-to-ppt
```

或直接描述任务，例如：

```text
使用 @html-to-ppt，根据我上传的行业材料，生成一个自包含 HTML 和同版式可编辑 PPTX。风格沿用白底、深海军蓝、高密度投研风格。
```

## 使用要求

调用这个 skill 时，模型应当一次性完成两个文件：

1. 一个自包含 HTML 演示稿
2. 一个同版式、尽可能可编辑的 PPTX

不要只输出 HTML 后停下来确认，也不要把 HTML 截图整页塞进 PPT。复杂图片可以作为独立图片对象存在，但标题、正文、表格、图表、箭头、标签、结论条等应尽量保持 PowerPoint 原生可编辑。

## 给其他模型使用

如果朋友使用的不是 ChatGPT / Codex，而是 GLM、Claude、Gemini 等，可以打开：

```text
html-to-ppt/references/universal-model-prompt.md
```

复制其中的通用提示词，粘贴给对应模型使用。该提示词已经把“同时生成 HTML 和 PPTX、保持编辑性、使用高密度蓝白投研风格、不要省略视觉资产”等核心要求写进去。

## 注意事项

- PPT 的可编辑性和视觉还原度取决于执行环境是否真的能创建并渲染 `.pptx`。
- 科学装置图、设备图、产品图等复杂视觉不建议强行拆成大量 PowerPoint 原生形状；更稳妥的做法是保留为独立图片/SVG，再用可编辑标签和箭头叠加。
- 这个 skill 默认追求“视觉质量 + 关键内容可编辑”的混合方案，而不是 100% 原生形状还原。
- 默认以 PowerPoint → Keynote 打开后的版式变化最小为目标，具体规则见 `html-to-ppt/references/cross-platform-compatibility.md`。
