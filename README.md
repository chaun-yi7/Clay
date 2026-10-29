# Clay — Typora 主题(明 / 暗)

> A warm, paper-textured Typora theme (light + dark), inspired by the claude.ai design language.

[![License](https://img.shields.io/badge/License-MIT-d97757)](./LICENSE)
[![LINUX DO](https://img.shields.io/badge/LINUX%20DO-社区-f5a623?logo=discourse&logoColor=white)](https://linux.do)

一对以 **claude.ai 官网设计语言**为蓝本的 Typora 主题:暖白纸感的浅色 `clay` 与暖灰深底的深色 `clay-dark`。配色对齐官网实测色板(陶土橙 Clay `#d97757` + 暖灰中性色),标题与正文统一走**随主题打包的霞鹜文楷 LXGW WenKai**,所有功能区块明暗**结构完全对称**(209 对规则逐条配对、零单边差异)。

- 适配环境:**Typora 1.13.x / Windows**(1.13.4、1.13.6 实测;1.5+ 版本的语法块均有覆盖;含 macOS seamless 兼容规则)
- **内置中文字体**:附带霞鹜文楷 Regular / Medium / Mono 三款 woff2,明暗两版一致,无需另行安装字体
- 零网络依赖:字体为本地自托管,不发起任何在线请求,离线 / 弱网 / 大陆网络环境下无渲染阻塞
- 中英混排优化:文楷统一覆盖中英文与标点;未命中时按宋体系 / 苹方 / 雅黑 / 更纱黑体逐级回退

---

## 预览

**浅色 · Clay**

![Clay 浅色预览](screenshots/clay-light.png)

**深色 · Clay Dark**

![Clay 深色预览](screenshots/clay-dark.png)

> 上图为主题渲染效果预览;实际以 Typora 中体验为准(建议配合「一体化」窗口样式)。

---

## 一、安装

### 文件构成

| 文件 / 目录 | 说明 |
|---|---|
| `clay.css` | 浅色主题 |
| `clay-dark.css` | 深色主题(与浅色逐区块对称) |
| `clay/` | 字体目录:霞鹜文楷 3 款 woff2 + `OFL.txt`。**两个 css 都依赖它**,需一起复制 |

### 主题目录

把两个 `.css` **和 `clay/` 目录**一起复制到 Typora 的主题目录:

| 平台 | 路径 |
|---|---|
| Windows | `%APPDATA%\Typora\themes\` |
| macOS | `~/Library/Application Support/abnerworks.Typora/themes/` |
| Linux | `~/.config/Typora/themes/` |

> 在 Typora → 文件 → 偏好设置 → 外观 → **打开主题文件夹**,可直接跳到该目录。

复制完成后,主题目录下应该是这样:

```
themes/
├── clay.css
├── clay-dark.css
└── clay/
    ├── LXGWWenKai-Regular.woff2
    ├── LXGWWenKai-Medium.woff2
    ├── LXGWWenKaiMono-Regular.woff2
    └── OFL.txt
```

> [!IMPORTANT]
> `clay/` 必须与两个 `.css` **同级**——css 里的 `@font-face` 按 `clay/xxx.woff2` 相对寻址。只复制 css 不复制目录,主题依然能用,但会静默回退到系统字体,失去文楷观感。

### 启用 / 更新

- **启用**:Typora → 文件 → 偏好设置 → 外观 → 主题,选择 `Clay` 或 `Clay Dark`
- **窗口样式选「一体化」**(强烈建议):偏好设置 → 外观 → 窗口样式 → **一体化**,标题栏 / 侧栏 / 正文同底融为一体,是本主题的推荐形态;切换后需**重启 Typora** 生效
- **修改 CSS 后生效**:切走主题再切回,或重启 Typora(Typora 不热载主题)
- **改样式前先备份**:编辑前复制一份 `.css`(或用 git 版本管理),便于回滚

> [!TIP]
> 本主题是按**一体化(Seamless)窗口样式**调校的——侧栏、标题栏、正文共用暖色底,窗框细线也随主题走。选「经典」样式同样能用,但一体化观感明显更完整。

---

## 二、设计语言

### 色板(两级强调色体系)

核心原则:**Clay 橙 `#d97757` 只做装饰**(引用条、光标、复选框、悬停底色、标记点),**正文级可读文本一律用加深的 `--accent-text-color`**,保证 WCAG AA(≥4.5:1)。

| 角色 | 浅色 | 深色 |
|---|---|---|
| 页面底色 | `#f8f8f6` 暖白 | `#1f1f1e` 暖黑 |
| 正文 | `#121212` | `#d5d4cb` |
| 装饰强调 `--accent-color` | `#d97757` | `#d97757` |
| 文本强调 `--accent-text-color` | `#ae5630`(4.73:1) | `#d97757`(深底上 4.7:1,可直接作文本) |
| 淡橙底上的文本(侧栏激活 / 标签 / 脚注) | `#9a4a28`(5.35:1) | `#d97757` |
| 引用底 / 侧栏底 | `#efeeeb` | `#262625` / `#171716` |
| 图表面板底 `--diagram-bg-color` | `#faf9f5` 象牙白 | `#262625` |
| Mermaid 节点 / 连线 | `#dde8f3` 浅蓝底 + `#5f93c8` 边 / `#3d3d3a` 细线 | `#2f3b47` 石板蓝 + `#6a9bcc` 边 / `#c2c0b6` 细线 |

### 字体栈(内置霞鹜文楷,全部本地,无网络请求)

栈首是随主题打包的 **霞鹜文楷 LXGW WenKai**(`clay/` 内的 woff2),明暗两版完全一致:

| 用途 | 栈 |
|---|---|
| 标题 `--font-heading` | **LXGW WenKai** → Anthropic Serif → Söhne Serif → ui-serif → Georgia → 宋体 / 思源宋体 |
| 正文 `--font-body` | **LXGW WenKai** → Anthropic Sans → Inter → Söhne → Segoe UI → 苹方 / 微软雅黑 |
| 等宽 `--font-mono` | Anthropic Mono → Fira Code → JetBrains Mono → Consolas → **LXGW WenKai Mono** → 更纱黑体 Mono SC |
| 界面 `--font-ui` | 同正文系(不含文楷),用于菜单 / 对话框 / 表单控件 |

字重按真实字形绑定:`Regular` 绑 `100–450`、`Medium` 绑 `500–900`,所以**加粗与标题用的是真 Medium 字形,而非浏览器伪粗体**。文楷没有真正的 Bold,Medium 只比 Regular 多约 18% 墨量,单靠换字形加粗不够醒目,因此正文加粗在 Medium 之上再叠一道**按 em 计的同色细描边**(浅色 `0.009em`、深色 `0.005em`——浅字压深底本就显粗,深色给得更少),明暗两版加粗墨量都落在约 +29%,随标题 / 小字号等比缩放;此前 0.25px 描边(+37% / +49%)发胀发糊的问题不再出现。想回到纯 Medium:`--strong-stroke-width: 0`。等宽栈把文楷 Mono 放在编程字体之后——装了 Fira Code / JetBrains Mono 的机器仍优先用它们渲染英文代码,文楷 Mono 负责兜底代码块里的中文,保证对齐代码网格。

> 不想要内置字体:把 `--font-heading` / `--font-body` 栈首的 `"LXGW WenKai", ` 删掉即可,其余回退栈原样可用。

### 版式

- 正文列宽 820px 居中(≥1400px 宽屏放宽到 880px;窄窗 ≤768px 收边距),行高 1.8,字距 0.02em(配合文楷偏宽的字面,中文阅读更松弛)
- 数字启用等宽表格数字(`tabular-nums`),表格 / 数据列天然对齐
- 文档首元素顶距收窄(以标题开头时不留大空白)

---

## 三、内容渲染功能

### 标题
- h1 `2.2em / 700` + 下边框;h2 `1.7em` + **陶土色半透明下划线**(浅 22% / 深 28%,`color-mix` 渐进增强);h3–h5 递减 600;h6 小型大写 + 弱化灰,当"眉题"用
- 标题内联代码不放大缩小(`font-size: inherit`)

### 列表
- 无序列表标记点 = Clay 橙(装饰);**有序列表编号 = 深陶土**(可读级);混合嵌套时按**直接父级**取色,互不串染
- **任务列表**:复选框绝对定位、精确对齐条目**首行**(长换行 / 多段 / 粗体连内联代码均不漂移,像素级 delta=0 验证);勾选态陶土橙(`accent-color`);悬停轻微放大不推挤文本
- 列表内图片:块级左对齐、带上下间距,不与文字挤在一行

### 引用块
Clay 4px 左条 + 暖灰底 + 右侧圆角,**直立不斜体**;嵌套引用右内距收平。

### 表格(卡片式)
圆角 + 浅阴影 + 外边框;表头着色 + 2px 强分隔;行悬停淡橙底;末行无底线。
- **长代码不再撑宽表格**:单元格里只有一段内联代码(URL / 路径 / 长标识符)时,其最小宽度封顶 15em——表格放得下就照常单行显示,放不下才在格内折行,不再被撑出正文列、需要左右滚动;短代码(如 `default`)与普通单词永远不会被拦腰截断,含文字的混排单元格不受影响。此规则依赖 Typora 编辑区的 DOM 结构,导出的 HTML / PDF 中表格保持原表现

### 内联代码 / 高亮 / 键帽
- `code`:暖底色块 + 细边框 + 红棕字(600 权重),跨行折行时两端圆角均保留(`box-decoration-break: clone`)
- `==高亮==`:暖棕半透明底(非刺眼默认黄),同样支持跨行
- `<kbd>`:键帽样式(双倍下边框模拟按键立体感);`<abbr>` 虚线底 + help 光标
- **加粗** `**text**`:真 Medium 字形 + em 级同色细描边,与 Regular 正文拉开明确分量差(明暗均约 +29% 墨量),笔画干净不糊;`--strong-stroke-width` 可调,设 `0` 即纯 Medium

### 代码围栏(编辑态 CodeMirror)
- Mac 风格圆角卡片,完整语法配色:关键字紫 / 字符串绿 / 数字橙 / 标签属性蓝 / 注释灰斜体,明暗两套独立调色
- 光标 2px 陶土色;选区用主题选择色;开启行号时行号槽透明底 + 右分隔线
- 围栏内代码不继承内联代码的边框 / 底色 / 加粗(导出 HTML 也不串色)

### 源代码模式(`Ctrl + /`)
- 全区等宽字体(含代码 span / 表格行等 Typora 默认强制通用等宽的 token,统一为主题等宽栈,表格竖线对齐)
- 内容居中成列(820px,与正文一致)
- Markdown token 重着色:标题行陶土、注释灰、字符串绿、数字橙、链接 / HTML 标签蓝(修复 Typora 默认色在深底上 2.5:1 不可读的问题)
- 光标陶土色;当前行淡色高亮

### 其他块级元素
- **GitHub 警告块** `> [!NOTE/TIP/IMPORTANT/WARNING/CAUTION]`:五色左条 + 同色调淡底,明暗两套(深色用 GitHub Dark 色值)
- **YAML Front Matter**:虚线边框面板 + 等宽字体
- **数学公式**:行内公式底色块;公式块工具提示浮层阴影 + 圆角(含官方同款定位修正)
- **Mermaid 图表**:Anthropic 工程博客式的极简画风——象牙白面板(深色为暖灰暗底 `#262625`)、浅蓝圆角节点、近黑细线、连线标签去掉灰底直接落在面板上、子图走燕麦色浅底;覆盖流程图 / 时序图 / 类图 / 状态图,明暗各一套。底层配色仍随主题切换 mermaid 主题(浅色 `default`、深色 `dark`,Typora 渲染时读取 `--mermaid-theme`),其余图种(饼图、甘特、ER 等)沿用该底层配色。图里自己写的 `style` / `classDef` / `linkStyle` 优先级更高,不会被主题覆盖;编辑态面板边框也随主题(`--panel-border-color`)
- **脚注**:上标做成暖底小徽章;脚注区顶部分隔线
- `~~删除线~~` 弱化灰;`<u>` / `<ins>` 陶土色下划线;`#标签` 暖底圆角小片
- 图片:块级居中 + 圆角 + 浮起阴影,悬停轻微放大;上下间距 0.9em,**紧跟标题的图片再收窄到 0.4em**(配图不再与标题脱节);`[TOC]` 目录卡片化

---

## 四、编辑器体验

- **光标**(正文 / 源码 / 围栏)统一陶土色
- **选区**:暖橙底;`Ctrl+F` 搜索命中:更深暖橙底(选中命中单独一档)
- **专注模式(F8)**:非焦点段落整体压暗为弱化灰——**链接 / 内联代码 / 粗体 / 高亮一并压暗**不残留亮色;代码围栏与源码模式同步压暗非活动行;图片 / SVG 降透明度;引用条同步减淡;紧凑列表有防"自灰"保护
- **打字机 / 滚动**:自定义细滚动条(悬停加深),不突兀
- **侧栏**:文件树 / 文件列表 / 大纲激活项 = 淡橙底 + 3px 陶土左条 + 加深文字;悬停淡橙底;全局搜索结果激活行同色系(`--active-file-text-color`)
- **快速打开(Ctrl+P)**:圆角浮层 + 激活行同侧栏色系
- **搜索替换面板**:主题化输入框;选项按钮激活态陶土底白字
- **输入框聚焦边框**(搜索框 / 对话框输入等)= 陶土色(压掉 Typora 默认的 Bootstrap 蓝,`--primary-color`)
- **菜单 / 对话框**:起始页大菜单、右键菜单、下拉菜单、偏好设置、模态框全部主题化;主按钮陶土底白字(官网 CTA 同款),悬停加深
- **窗框细线** `--window-border`:侧栏页签 / 文件行分隔 / 下拉分割线等按主题边框色走(深色下不再露浅色发丝线)
- **起始页 / 窗口标题栏**:起始页「菜单」标题与返回按钮走主题文字色(Typora 底座硬编码的白字在暖白侧栏上不可读);标题栏下沿平齐——右侧按钮条、最大化组与最小化 / 最大化 / 还原 / 关闭 / 取消置顶按钮全部压回 24px(底座按钮 28px,且按钮条继承正文 1.8 行高形成 28.8px 行盒,会把栏色多画出 4–5px 台阶),长按最大化弹出的「全屏 / 置顶」浮层上移贴合按钮,左侧标题区不再多出 1–2px 下沿;悬停底色随主题(深色下不闪浅灰),置顶态与浮层边框在深色下也不再露浅灰
- 表格编辑工具条 / 底部字数统计 / 源码切换按钮激活态 / 工具提示(深底白字)均已主题化
- 编辑期元 token(标题 `{#id}` 属性、HTML 注释)弱化显示

---

## 五、导出与打印

- `@media print`:正文缩至 13px;表格 / 代码块 / 引用 / 图片 / 警告块**不跨页截断**;标题后不孤立分页;段落孤行寡行控制(orphans/widows 3)
- 导出 PDF / 打印时自动去掉图片、表格、代码块阴影(纸面干净)
- 无在线字体引用 → 导出不会卡在网络请求
- Mermaid 的主题配色随导出保留(导出时 Typora 复用编辑区的图表 SVG,主题 CSS 一并写入)
- 深色主题导出 PDF 保持深色(与 Typora 官方 night 主题行为一致,刻意不强制翻白)

---

## 六、对比度与可读性承诺

- 所有**正文级**文本 token ≥ 4.5:1(AA):正文、链接、标题、引用、脚注、标签、侧栏激活文字等均实测达标
- Mermaid 图表同样达标:节点文字 15.1:1 / 7.7:1、连线标签 6.3:1 / 5.9:1、子图标题 5.7:1 / 5.4:1(浅 / 深);节点描边 3.1:1 / 5.2:1、连线 10.3:1 / 8.3:1,满足图形对象 3:1
- 专注模式压暗色 = 弱化灰(浅 `#7b7974` / 深 `#97958c`),**同时定义了 Typora 内部的 `--blur-text-color`**,连 Typora 基础样式自己的压暗规则也走主题灰(修复深色下默认 `#C8C8C8` "越压越亮"的问题)
- 已知惯例值(刻意保留):语法高亮字符串 / 数字在浅色下 3.7–3.9:1(通行的代码高亮密度取舍)、h6 眉题 4.09:1(官网原生 token)、主按钮白字压陶土底(官网同款)

---

## 七、自定义入口(改 `:root` 变量即可)

| 想改什么 | 动哪个变量 |
|---|---|
| 换强调色 | `--accent-color`(装饰)+ `--accent-text-color`(文本级,注意对比度) |
| 换字体 / 关掉内置文楷 | `--font-heading` / `--font-body` / `--font-mono`(删掉栈首的 `"LXGW WenKai", ` 即回到系统字体) |
| 列宽 | `#write { max-width }`(两处:默认 820 与宽屏 880)|
| 代码高亮配色 | `--code-keyword/string/number/symbol/muted-color` |
| 表格 / 引用底色 | `--table-*` / `--quote-*` |
| 侧栏激活色系 | `--active-file-bg/border/text-color` |
| 加粗分量 | `--strong-stroke-width`(浅 `0.009em` / 深 `0.005em`;`0` = 纯 Medium,不叠描边) |
| 图表面板底 | `--diagram-bg-color` |
| Mermaid 画风 | `--mermaid-node-color` / `--mermaid-node-border-color`(节点)、`--mermaid-line-color`(连线)、`--mermaid-text-color` / `--mermaid-label-color`(节点文字 / 连线标签)、`--mermaid-cluster-color` / `--mermaid-cluster-border-color`(子图 / 注释 / 循环框) |
| Mermaid 底层主题 | `--mermaid-theme`(`default` / `dark` / `forest` / `neutral` / `base`,Typora 渲染时读取;**每个 css 里只能出现这一处**——Typora 导出时按纯文本查找这条声明) |

明暗两文件区块顺序完全一致,改动请**成对**进行以维持对称。

---

## 八、质量基线

开发中经过五轮审查:静态分析(括号 / 变量 / 选择器配对)、真实浏览器渲染(Playwright 计算样式 + 截图)、**与 Typora 真实 base.css 同层加载的级联回归测试**、WCAG 对比度实算、对抗式代理复查。当前状态:两文件 215/215 括号平衡、209 对规则逐条同序配对、零单边零属性差、零悬空变量。

2026-10 针对 issue #1–#5 的修复(深色 Mermaid、起始页菜单白字、加粗分量、标题栏台阶、Mermaid 画风、表格长代码撑宽)以 **Typora 1.13.6 的真实样式与脚本**同层复现:bootstrap / mermaid.css / base / base-control / codemirror / window / megamenu 按 window.html 顺序加载,图表用 Typora 自带的 mermaid 11.13.0 与 diagram.min.js,mermaid 初始化参数照搬 Typora 读取 `--mermaid-*` 变量的逻辑;表格按编辑区 DOM(`.td-span` + `[md-inline]`)搭建。逐项验证:标题栏在常规 / 长按浮层 / 最大化 / 置顶四种窗口状态下所有带底色元素的下沿 ≤ 24px;加粗在 1x / 1.5x / 2x 下实测墨量(Regular → Medium +18% → 现 +29%);8 张回归表格逐一检查溢出、整词断裂与代码折行;Mermaid 流程图 / 时序 / 类 / 状态 / ER / 饼图 / Typora 自带时序与流程图明暗全量截图对照,自定义 `style` / `classDef` / `linkStyle` 保持原色。

日常自检:随手用一篇含标题 / 列表 / 任务列表 / 表格 / 代码块 / 引用 / 警告块 / 公式的 Markdown,在明暗两主题下逐项对照(重点看:源码模式配色、对话框无蓝色残留、深色窗框、复选框首行对齐、专注模式压暗方向)。

---

## 九、致谢

感谢 [**LINUX DO**](https://linux.do) 社区的交流与反馈。

> LINUX DO 是一个真诚、友善、团结、专业的技术社区。*Where possible begins.*

---

## License

主题样式(`clay.css` / `clay-dark.css` / 文档):[MIT](./LICENSE)

**内置字体单独授权**:`clay/` 下的霞鹜文楷 LXGW WenKai(Regular / Medium / Mono)版权归 [LXGW](https://github.com/lxgw/LxgwWenKai),以 **SIL Open Font License 1.1** 授权,完整条款见 [`clay/OFL.txt`](./clay/OFL.txt)。本仓库仅以 woff2 形式随主题分发、供 `@font-face` 渲染,未作为可安装的桌面字体提供,符合该字体 OFL 中的附加许可条款。字体本身不适用 MIT。霞鹜文楷衍生自 [Klee One](https://github.com/fontworks-fonts/Klee)(FONTWORKS Inc.,同为 OFL 1.1)。

本主题在视觉上参考了 [claude.ai](https://claude.ai) 的公开设计语言(配色 / 版式),与 Anthropic 无隶属或背书关系。"Claude" 为 Anthropic 的商标,此处仅作事实性引用。

---

*主题文件:`clay.css`、`clay-dark.css` 与 `clay/` 字体目录(三者一并放入 Typora 主题目录) · 基于 Typora 1.13.4 / 1.13.6 验证 · 2026-10*
