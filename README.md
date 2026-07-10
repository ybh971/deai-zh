# deai-zh: 降文字AI率工具

一个全面的中文文本去AI化工具，将AI生成或AI风格过重的文本改写为符合人类思维和表达逻辑的自然文本。

适用场景：学术论文降AI率、发言稿去AI味、作文人类化、通用文本改写。

## 特性

- **四层处理管线**：领域确认 → 结构人性化 → 语言人性化 → 质检评分
- **多领域适配**：学术论文、发言稿、作文、通用文章
- **中文语言自然化**：把字句/被字句控制、标点密度优化、关联词意合化、句式节奏混排
- **检测器优化**：针对知网AIGC检测和格子达检测的专项规避策略
- **质量自检**：知网风格自检 + 格子达风格自检 + 五维人类写作评分

## 安装

### 方法一：npx 一键安装（推荐）

```bash
npx skills add https://github.com/ybh971/deai-zh.git
```

### 方法二：Git 克隆

```bash
# Windows
git clone https://github.com/ybh971/deai-zh.git %USERPROFILE%\.claude\skills\deai-zh

# macOS / Linux
git clone https://github.com/ybh971/deai-zh.git ~/.claude/skills/deai-zh
```

### 方法三：手动安装

1. 下载 ZIP 或克隆到本地
2. 将 `deai-zh` 文件夹复制到：
   - **Windows**: `%USERPROFILE%\.claude\skills\`
   - **macOS/Linux**: `~/.claude/skills/`

3. 确保结构：
   ```
   ~/.claude/skills/deai-zh/
   ├── SKILL.md
   ├── README.md
   └── LICENSE
   ```

## 使用

### 基础用法

在 Claude Code 中调用：

```
/deai-zh
```

然后粘贴需要处理的文本。工具会自动判断领域并请求确认。

### 直接粘贴

```
/deai-zh 请帮我处理以下文本：

[粘贴文本]
```

### 处理文件

```
/deai-zh 请处理 article.md 中的内容
```

## 处理流程

```
输入 → [1.领域确认] → [2.结构人性化] → [3.语言人性化] → [4.质检评分] → 输出 + 质检报告
```

### 第1层：领域确认
分析文本，判断属于学术论文、发言稿、作文或通用文章，并向用户确认。

### 第2层：结构人性化
打破AI的模板化结构，按人类思维方式重组段落逻辑。针对知网语义模板匹配优化。

### 第3层：语言人性化
句子级中文自然化：把字句/被字句、标点密度、关联词意合化、句式节奏混排。针对格子达句式规律检测优化。

### 第4层：质检与评分
知网风格自检 + 格子达风格自检 + 五维人类写作评分（自然度/节奏感/具体性/人性化/领域适配，总分50）。

## 检测的AI模式类型

### 结构层面
- 过度强调意义和遗产
- 公式化的"挑战与展望"
- 三段式法则
- 虚假范围
- 列表式结构
- 知网语义模板匹配规避

### 语言层面
- AI高频词汇
- 系动词回避
- 否定式排比
- 刻意换词
- 肤浅分析短语
- 宣传广告语
- 模糊归因
- 填充短语
- 关联词密度过高
- 句式均匀节奏

## 目标检测器

### 知网 AIGC 检测
- 检测原理：语义片段模板匹配
- 准确率：~99%（中文）
- 适用场景：高校毕业论文、核心期刊投稿
- 安全线：多数院校要求 ≤15%

### 格子达
- 检测原理：句式规律识别
- 准确率：90%+
- 适用场景：高校毕业论文、学术审核
- 安全线：多数院校要求 ≤15%

## 许可

MIT License

## 参考

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- [blader/humanizer](https://github.com/blader/humanizer)
- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)
