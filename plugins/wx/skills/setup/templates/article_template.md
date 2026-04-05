# 微信公众号文章模板 (HTML)

## HTML 结构模板

```html
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>{文章标题}</title>
    <style>
      /* ========================================
         基础色板 - 中性色阶
         ======================================== */
      :root {
        --neutral-950: #0f0f0f;
        --neutral-900: #1a1a1a;
        --neutral-700: #404040;
        --neutral-600: #525252;
        --neutral-500: #737373;
        --neutral-400: #a3a3a3;
        --neutral-300: #d4d4d4;
        --neutral-200: #e5e5e5;
        --neutral-100: #f5f5f5;
        --neutral-50: #fafafa;
        --white: #ffffff;

        /* 强调色 */
        --accent-amber: #d97706;
        --accent-amber-light: #fffbeb;
        --accent-amber-border: #f59e0b;
        --accent-pink: #db2777;

        /* ========================================
           功能语义变量
           ======================================== */
        /* 背景 */
        --bg-body: var(--white);
        --bg-summary: var(--neutral-100);
        --bg-quote: var(--neutral-100);
        --bg-key-point: var(--accent-amber-light);
        --bg-tag: var(--neutral-100);
        --bg-cta: var(--neutral-900);

        /* 文字 */
        --text-primary: var(--neutral-900);
        --text-secondary: var(--neutral-600);
        --text-tertiary: var(--neutral-500);
        --text-on-dark: var(--white);
        --text-accent: var(--accent-amber);
        --text-highlight: var(--accent-pink);

        /* 边框 */
        --border-quote: var(--neutral-900);
        --border-key-point: var(--accent-amber-border);

        /* 间距 */
        --space-xs: 0.5rem;
        --space-sm: 0.75rem;
        --space-md: 1rem;
        --space-lg: 1.5rem;
        --space-xl: 2.5rem;
      }

      /* ========================================
         基础样式
         ======================================== */
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      body {
        font-family:
          -apple-system, BlinkMacSystemFont, "Segoe UI", "PingFang SC",
          "Hiragino Sans GB", "Microsoft YaHei", "Helvetica Neue", sans-serif;
        font-size: 17px;
        line-height: 1.75;
        letter-spacing: 0.01em;
        color: var(--text-primary);
        background: var(--bg-body);
        max-width: 680px;
        margin: 0 auto;
        padding: 24px 20px;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
      }

      /* 标题层级 */
      h1 {
        font-size: 28px;
        font-weight: 700;
        line-height: 1.4;
        margin-bottom: var(--space-sm);
        letter-spacing: -0.01em;
      }

      h2 {
        font-size: 22px;
        font-weight: 600;
        line-height: 1.4;
        margin: var(--space-xl) 0 var(--space-md) 0;
        padding-bottom: var(--space-xs);
        border-bottom: 1px solid var(--neutral-200);
      }

      h3 {
        font-size: 19px;
        font-weight: 600;
        line-height: 1.4;
        margin: var(--space-lg) 0 var(--space-sm) 0;
        color: var(--neutral-700);
      }

      /* 元信息 */
      .subtitle {
        color: var(--text-secondary);
        font-size: 16px;
        line-height: 1.6;
        margin-bottom: var(--space-sm);
      }

      .meta {
        color: var(--text-tertiary);
        font-size: 14px;
        margin-bottom: var(--space-lg);
        display: flex;
        gap: var(--space-xs);
        align-items: center;
      }

      .meta::before {
        content: "";
        display: inline-block;
        width: 4px;
        height: 4px;
        background: var(--neutral-400);
        border-radius: 50%;
        margin-right: var(--space-xs);
      }

      /* 封面图 */
      .cover-image {
        width: 100%;
        height: auto;
        border-radius: 8px;
        margin-bottom: var(--space-lg);
        object-fit: cover;
      }

      /* 正文段落 */
      p {
        margin-bottom: var(--space-md);
        text-align: justify;
        text-justify: inter-ideograph;
      }

      /* 列表 */
      ul,
      ol {
        margin-bottom: var(--space-md);
        padding-left: 1.75em;
      }

      li {
        margin-bottom: var(--space-xs);
        line-height: 1.7;
      }

      li::marker {
        color: var(--neutral-500);
      }

      /* 强调与标记 */
      strong {
        font-weight: 600;
        color: var(--neutral-950);
      }

      em {
        font-style: italic;
        color: var(--neutral-700);
      }

      .highlight {
        color: var(--text-highlight);
        font-weight: 500;
        background: linear-gradient(
          transparent 60%,
          rgba(219, 39, 119, 0.15) 60%
        );
        padding: 0 2px;
      }

      /* ========================================
         内容区块
         ======================================== */

      /* 文章摘要 */
      section.summary {
        background: var(--bg-summary);
        padding: var(--space-md) var(--space-lg);
        margin-bottom: var(--space-lg);
        border-radius: 6px;
        font-size: 15px;
        line-height: 1.7;
        color: var(--text-secondary);
        border-left: 3px solid var(--neutral-400);
      }

      /* 引用块 - 保持规则：使用 blockquote 标签 */
      blockquote {
        background: var(--bg-quote);
        border-left: 4px solid var(--border-quote);
        padding: var(--space-md) var(--space-lg);
        margin: 0 0 var(--space-md) 0;
        border-radius: 0 8px 8px 0;
        font-style: italic;
        color: var(--text-secondary);
      }

      blockquote p {
        margin-bottom: 0;
      }

      blockquote cite {
        display: block;
        margin-top: var(--space-sm);
        font-size: 14px;
        color: var(--text-tertiary);
        font-style: normal;
      }

      /* 重点提示 - 保持规则：使用 section 标签 */
      section.key-point {
        background: var(--bg-key-point);
        padding: var(--space-md) var(--space-lg);
        border-radius: 8px;
        border: 1px solid var(--border-key-point);
        margin-bottom: var(--space-md);
      }

      section.key-point .key-point-title {
        font-weight: 600;
        color: var(--text-accent);
        margin-bottom: var(--space-xs);
        display: flex;
        align-items: center;
        gap: 6px;
        font-size: 15px;
      }

      section.key-point .key-point-title::before {
        content: "◆";
        font-size: 10px;
      }

      section.key-point p {
        margin-bottom: 0;
        font-size: 15px;
        color: var(--text-secondary);
      }

      /* 标签 */
      .tags {
        margin: var(--space-xl) 0 var(--space-md) 0;
        display: flex;
        flex-wrap: wrap;
      }

      .tag {
        display: inline-flex;
        align-items: center;
        background: var(--bg-tag);
        color: var(--text-secondary);
        padding: 4px 12px;
        border-radius: 20px;
        font-size: 13px;
        font-weight: 500;
        transition: all 0.2s ease;
        margin-right: 8px;
      }

      .tag:hover {
        background: var(--neutral-200);
        color: var(--text-primary);
      }

      /* 行动号召 - 保持规则：使用 section 标签 */
      section.cta {
        background: var(--bg-cta);
        color: var(--text-on-dark);
        text-align: center;
        padding: var(--space-xl) var(--space-lg);
        margin: var(--space-xl) 0 var(--space-md) 0;
        border-radius: 12px;
      }

      section.cta .cta-title {
        font-size: 18px;
        font-weight: 600;
        margin-bottom: var(--space-xs);
        display: block;
      }

      section.cta .cta-text {
        font-size: 14px;
        opacity: 0.75;
        display: block;
      }

      /* 分隔线 */
      hr {
        border: none;
        height: 1px;
        background: var(--neutral-200);
        margin: var(--space-xl) 0;
      }

      /* 代码 */
      code {
        font-family: "SF Mono", Monaco, "Cascadia Code", monospace;
        font-size: 0.9em;
        background: var(--neutral-100);
        padding: 2px 6px;
        border-radius: 4px;
        color: var(--accent-pink);
      }

      pre {
        background: var(--neutral-900);
        color: var(--white);
        padding: var(--space-md);
        border-radius: 8px;
        overflow-x: auto;
        margin-bottom: var(--space-md);
      }

      pre code {
        background: transparent;
        color: inherit;
        padding: 0;
      }
    </style>
  </head>
  <body>
    <h1>{文章标题}</h1>
    <p class="subtitle">{副标题}</p>
    <p class="meta">{日期} · {阅读时长}</p>

    <!-- 封面图占位 -->
    <!-- <img class="cover-image" src="{封面图URL}" alt="{图片描述}"> -->
    <!-- 封面图片提示词占位 -->

    <!-- 文章摘要 - 保持规则：使用 section 标签，文字直接写在内，不额外包裹 -->
    <section class="summary">
      {文章摘要 50-100字，直接写在这里，不需要额外标签包裹}
    </section>

    <h2>章节标题</h2>
    <p>正文内容...</p>

    <!-- 引用块 - 保持规则：使用 blockquote 标签 -->
    <blockquote>
      <p>引用内容...</p>
      <cite>—— 引用来源</cite>
    </blockquote>

    <!-- 重点提示 - 保持规则：使用 section 标签 -->
    <section class="key-point">
      <span class="key-point-title">重点提示</span>
      <p>重点内容描述...</p>
    </section>

    <h2>下一章节</h2>
    <p>更多内容...</p>

    <!-- 标签 -->
    <div class="tags">
      <span class="tag">标签1</span>
      <span class="tag">标签2</span>
      <span class="tag">标签3</span>
    </div>

    <!-- 行动号召 - 保持规则：使用 section 标签 -->
    <section class="cta">
      <span class="cta-title">觉得有收获？</span>
      <span class="cta-text">点赞、在看、留言、关注，任选其一</span>
    </section>
  </body>
</html>
```

---

## 样式规则

### 背景/边框元素（保持不变）

**只有引用使用 `<blockquote>` 标签，其他带背景或边框的容器使用 `<section>` 标签。**

```html
<!-- 正确示例 -->
<section class="summary">文章摘要内容...</section>
<section class="key-point">
  <span class="key-point-title">重点提示</span>
  <p>重点内容...</p>
</section>
<section class="cta">
  <span class="cta-title">引导标题</span>
  <span class="cta-text">引导内容...</span>
</section>

<blockquote>
  <p>引用内容...</p>
  <cite>引用来源</cite>
</blockquote>

<!-- 错误示例 -->
<blockquote class="summary">文章摘要内容...</blockquote>
<div class="quote">引用内容...</div>
```

### 文字内容容器（保持不变）

**文字内容不能直接写在 `div`、`blockquote`、`section`等容器标签内，必须包裹在语义化标签中。**

```html
<!-- 正确示例 -->
<section class="summary">直接写摘要内容</section>
<p>这是正文内容</p>
<h2>章节标题</h2>
<span class="highlight">高亮文字</span>
<code>代码片段</code>

<blockquote>
  <p>引用内容...</p>
  <cite>引用来源</cite>
</blockquote>

<!-- 错误示例 -->
<div>直接放在div里的文字</div>
<blockquote>直接放在blockquote里的文字</blockquote>
<section class="summary"><span>多余包裹</span></section>
```

---

## 配色方案说明

| 用途          | 颜色               | 色值    | 说明               |
| ------------- | ------------------ | ------- | ------------------ |
| 主文字        | neutral-900        | #1a1a1a | 纯黑偏暖，阅读舒适 |
| 副标题        | neutral-600        | #525252 | 中灰，层级分明     |
| 元信息        | neutral-500        | #a3a3a3 | 浅灰，弱化处理     |
| 高亮          | accent-pink        | #db2777 | 玫红，醒目但不刺眼 |
| 重点标题      | accent-amber       | #d97706 | 琥珀色，温暖专业   |
| 重点背景      | accent-amber-light | #fffbeb | 极浅琥珀，柔和提示 |
| 引用/标签背景 | neutral-100        | #f5f5f5 | 浅灰，不抢内容风头 |
| CTA背景       | neutral-900        | #1a1a1a | 深色，形成视觉锚点 |

---

## 配图建议

| 位置       | 比例 | 描述                 |
| ---------- | ---- | -------------------- |
| 封面图     | 16:9 | 有视觉冲击，吸引点击 |
| 正文配图1  | 4:3  | 辅助说明内容         |
| 正文配图2  | 1:1  | 细节展示             |
| 结尾引导图 | 16:9 | 引导关注             |

---
