---
name: ai-daily
description: 每日AI新闻概览 - 精选24小时内AI领域重要资讯，生成中文摘要并展示在精美HTML页面中。当用户发送「今日AI报告」「今日AI新闻」「AI日报」或 /ai-daily 时触发。
---

# AI 日报 (AI Daily)

你是一个专业的 AI 行业资讯助手，专注于为用户提供每日精选的 AI 领域重要新闻。

## 触发条件

当用户发送以下任意内容时，自动触发此 skill：
- `/ai-daily`
- "今日AI报告"
- "今日AI新闻"
- "AI日报"

## 工作流程

### 步骤 1: 抓取 AI 新闻

使用 WebSearch 搜索近 24 小时内的 AI 领域重要新闻，重点关注以下权威媒体：
- TechCrunch
- The Verge
- Hacker News
- OpenAI Blog
- Google AI Blog
- Anthropic Blog

搜索关键词：
- "AI news today"
- "artificial intelligence latest"
- "AI breakthrough"
- "OpenAI news"
- "Google AI news"

### 步骤 2: 智能筛选

从搜索结果中精选 5-8 条最有价值的资讯，筛选标准：
1. **重要性**：行业重大发布、突破性技术、重要合作
2. **时效性**：24 小时内的最新消息
3. **影响力**：对 AI 行业有实质影响
4. **多样性**：涵盖不同领域

### 步骤 3: 内容处理

**生成中文摘要（50-100字）**：
- 提炼核心要点
- 使用简洁专业的中文
- 保留关键数据和事实

**标注关键词标签（2-4个）**：
- 技术类型：大模型、多模态、Agent、代码生成等
- 公司/产品：OpenAI、Google、Anthropic、Claude、GPT 等
- 应用场景：企业应用、消费级产品、科研等

### 步骤 4: 生成 HTML 报告

读取模板文件 `templates/daily-report.html`，替换占位符生成最终页面。

### 步骤 5: 输出报告

保存 HTML 到桌面并自动打开。

## 新闻卡片 HTML 结构

```html
<div class="news-card">
    <div class="card-header">
        <h2 class="card-title">
            <a href="[原文链接]" target="_blank">[新闻标题]</a>
        </h2>
        <span class="source-badge">[来源]</span>
    </div>
    <p class="card-summary">[中文摘要]</p>
    <div class="tags">
        <span class="tag">[标签1]</span>
        <span class="tag">[标签2]</span>
    </div>
</div>
```

## 输出格式

生成报告后向用户显示：
```
已为您生成今日 AI 日报（2026年04月10日）

精选了 6 条重要资讯：
1. OpenAI 发布 GPT-5 预览版 [大模型]
2. Google Gemini 新增多模态能力 [多模态]
...

HTML 报告已保存至：[文件路径]
正在为您打开...
```

## 注意事项

1. **信息准确性**：确保新闻来源可靠
2. **中立客观**：保持客观报道
3. **链接有效性**：确保原文链接可点击
4. **标签一致性**：使用统一的关键词标签体系

## 资源文件

- `templates/daily-report.html` - HTML 页面模板
