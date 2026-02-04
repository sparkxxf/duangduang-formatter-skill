---
name: duangduang-formatter
description: 专业文档排版专家 (Universal Document Formatter)。专门用于将 AI 输出内容转化为优化过的 HTML 格式，以便直接“复制-粘贴”到 Microsoft Word 中并保留完美的学术/商务排版。支持处理 PDF、DOCX、XLSX、Markdown 和纯文本输入。
---

# duangduang排版专家 (Universal Document Formatter)

该 Skill 解决了从 AI 助手向 Microsoft Word 转移内容时的“最后一公里”排版问题。它通过生成符合特定样式的 HTML 5 代码块，确保内容在粘贴到 Word 时自动对标学术和商务规格。

## 核心逻辑

1. **内容提取**：针对 PDF、DOCX 或 XLSX 输入，优先调用内置的 `pdf`、`docx` 或 `xlsx` Skill 提取原始文本和结构。
2. **结构化处理**：将提取的内容或输入的纯文本/Markdown 映射到标准的 HTML 结构中。
3. **样式注入**：应用定义的 CSS 样式以确保 Word 兼容性。

## 样式定义规范 (CSS Design)

在输出 HTML 时，必须包含以下内嵌样式：

- **H1 (主标题)**: 居中, 18pt, 'Microsoft YaHei' (微软雅黑), 行距 35pt。
- **H3 (多级标题)**: 左对齐, 15pt, 加粗, 使用中文数字编号 (如：一、(一))。
- **P (正文)**: 12pt, 行距 25pt, 两端对齐。
- **Strong (强调)**: 颜色设为红色 (#FF0000)。
- **通用约束**: 全面移除所有 Emoji，保持专业严肃的学术/商务色调。

## 使用流程

1. **识别输入**：判断用户提供的是文件路径还是直接文本。
2. **读取内容**：
    - 如果是 `.pdf`，使用 `pdf` Skill。
    - 如果是 `.docx`，使用 `docx` Skill。
    - 如果是 `.xlsx`，使用 `xlsx` Skill。
    - 如果是文本，直接处理。
3. **生成输出**：输出一个包含完整样式定义的 HTML 5 代码块。

## 输出模板示例

```html
<!DOCTYPE html>
<html>
<head>
<style>
    body { font-family: 'Microsoft YaHei', sans-serif; line-height: 25pt; font-size: 12pt; text-align: justify; }
    h1 { text-align: center; font-size: 18pt; line-height: 35pt; font-weight: normal; }
    h3 { text-align: left; font-size: 15pt; font-weight: bold; margin-top: 15pt; }
    strong { color: #FF0000; }
</style>
</head>
<body>
    <h1>文档标题</h1>
    <h3>一、 核心结论</h3>
    <p>这是正文内容，其中包含<strong>红色重点标注</strong>的内容。</p>
</body>
</html>
```

## 注意事项

- 不要使用 Markdown 代码块嵌套，直接输出 HTML 内容。
- 确保所有尺寸单位使用 `pt` (磅)，这是 Word 最兼容的单位。
- 严禁在输出中出现任何表情符号 (Emoji)。
