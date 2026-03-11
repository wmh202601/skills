# Claw CAMP 品牌系统

## 品牌定位

- **品牌名**：Claw CAMP
- **母品牌**：AI CAMP 出品
- **核心吉祥物**：🦞 小龙虾
- **slogan 方向**：Stop Chatting. Start Doing. / 让 AI 替你干活
- **Powered by**：OpenClaw

## 配色系统

```css
:root {
    /* 主色 */
    --claw-orange: #FF6D3A;   /* 主品牌色，CTA、高亮、badge */
    --claw-deep:   #E84D1A;   /* 深橙，渐变终点、hover */

    /* Google 调色盘（辅助色，体现 Google AI Studio 基因） */
    --g-blue:   #4285F4;
    --g-red:    #EA4335;
    --g-yellow: #FBBC05;
    --g-green:  #34A853;
    --g-purple: #A142F4;

    /* 中性色 */
    --bg-white:    #FFFFFF;
    --bg-gray:     #F8F9FA;
    --text-primary:   #202124;
    --text-secondary: #5F6368;
    --text-tertiary:  #9AA0A6;
    --border-light:   #E8EAED;
}
```

## 彩色顶条（必须元素）

所有海报顶部必须有 5px 的四色渐变条：

```css
.color-bar {
    height: 5px;
    background: linear-gradient(90deg,
        var(--claw-orange) 25%,
        var(--g-red)    25%, var(--g-red)    50%,
        var(--g-yellow) 50%, var(--g-yellow) 75%,
        var(--g-green)  75%);
}
```

## 字体

```css
font-family: "Inter", "Noto Sans SC", -apple-system, BlinkMacSystemFont, sans-serif;
```

- 加载：Google Fonts（Inter + Noto Sans SC）
- 标题：font-weight 800–900
- 正文：font-weight 400–600

## 视觉风格规范

- **整体风格**：Google Material 启发，干净、模块化、信息层次清晰
- **卡片**：`border-radius: 13–16px`，`border: 1px solid var(--border-light)`，白底
- **Chip/Badge**：`border-radius: 100px`（胶囊形），灰底或橙底
- **course-tag**：橙底实色，`letter-spacing: 1.5px`，全大写
- **图标**：Font Awesome 6（CDN 引入）
- **不允许**：深色 hero（深色背景仅限底部 CTA footer）、随意紫色渐变、Inter 以外的英文字体

## 顶部导航结构

```html
<nav class="top-nav">
    <div class="brand-left">
        <span>🦞</span>
        <div>
            <div class="brand-name">Claw CAMP</div>
            <div class="brand-sub">AI CAMP 出品</div>
        </div>
    </div>
    <div class="nav-right">
        <div class="session-badge">第 X 期 实 验 班</div>
        <div class="powered-by">Powered by <strong>OpenClaw</strong></div>
    </div>
</nav>
```

## 底部 CTA Footer

- 背景：`var(--text-primary)` (#202124 深色)
- CTA 按钮：橙色实底
- 退款承诺：`🛡️ 不满意 · 课后全额退款`
- 二维码：白底 padding:8px，`height: auto`（保持原始比例，不强制正方形）

## 资产路径（ClawCAMP 文件夹）

```
/Users/aicamp/Desktop/ClawCAMP/
├── 梦浩微信.jpg      ← 创始人二维码（默认通用渠道）
├── Jenny 微信.jpg   ← Jenny 渠道
├── angel 微信.jpg   ← Angel 渠道
└── logo.png / logo2.png
```

二维码按渠道替换，在 HTML 注释中标注：`<!-- 替换为对应渠道二维码 -->`
