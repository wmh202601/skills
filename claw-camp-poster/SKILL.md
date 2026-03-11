---
name: claw-camp-poster
description: 为 Claw CAMP / ClawCAMP 设计和迭代招生传播用的 HTML 海报与宣传图。凡涉及 Claw CAMP 的视觉物料都应触发：包括首发海报、短图、长图、朋友圈传播图、招生宣传图、微信群转发图，以及对现有海报的任何迭代（改期次、改席位、改二维码、改渠道、改价格、改文案）。输出固定尺寸 9:16 首发海报（420×747px）或可滚动长图，严格遵循 Claw CAMP 品牌规范（橙色系、四色彩条、Google 配色辅助、白底卡片）。
---

# Claw CAMP 海报技能

为 Claw CAMP 设计和迭代 HTML 海报的专属技能。

## 快速开始

**读这两个文件，再动手：**
- `{baseDir}/references/brand.md` — 品牌系统（配色/字体/组件规范）
- `{baseDir}/references/poster-types.md` — 海报类型规范 + review checklist

---

## 工作流程

### Step 1：明确需求

开始前确认以下信息（从对话上下文提取，不确定时才询问）：

| 信息 | 选项 |
|------|------|
| 海报类型 | 首发海报（9:16）/ 详情长图 |
| 期次 | 第 X 期实验班 |
| 时间地点 | 日期 · 城市 |
| 席位情况 | 总数 / 已满数 |
| 是否含价格 | 是 / 否 |
| 输出渠道 | 默认（梦浩微信）/ Jenny / Angel / 其他 |
| 特殊要求 | 文案调整 / 模块增减 |

### Step 2：读品牌和类型规范

```
Read {baseDir}/references/brand.md
Read {baseDir}/references/poster-types.md
```

严格按规范执行，不要自由发挥配色或字体。

### Step 3：生成 HTML

**文件命名规则：**
- 首发海报：`claw-camp-poster-v{N}.html`（N 为版本号）
- 详情长图：`claw-camp-poster.html`
- 无价格版：在文件名加 `-no-price`

**输出目录：** `/Users/aicamp/Desktop/ClawCAMP/`

**HTML 模板结构（首发 9:16）：**

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Noto+Sans+SC:wght@400;500;700;900&display=swap" rel="stylesheet">
    <style>
        /* 使用 brand.md 中的 CSS 变量 */
        /* 固定卡片尺寸：width:420px; height:747px; */
    </style>
</head>
<body>
    <!-- 结构顺序见 poster-types.md -->
</body>
</html>
```

### Step 4：自我 Review

生成后，对照 `poster-types.md` 的 **Review Checklist** 逐条检查：

- 比例和尺寸是否正确
- "带电脑和手机"（不只是手机）
- 二维码 `height: auto` 不裁剪
- 右上 nav-right 不大片空白
- 席位数字准确
- 渠道 QR 已标注注释

### Step 5：报告产出

告诉用户：
1. 文件路径
2. 本次改了什么（用简洁的变更列表）
3. 是否有需要用户确认的信息（如席位数字、二维码路径）

---

## 迭代修改

当用户提出修改意见时：

1. **精确修改**：只改被点名的地方，不要顺手改其他
2. **保留原版**：改动前先备份（`cp poster.html poster-backup.html`）或递增版本号
3. **解释改动**：用一句话说清楚改了什么、为什么

---

## 常见场景

**场景 A：从零新建首发海报**
→ 确认期次/时间/地点/席位 → 读 brand.md + poster-types.md → 按 9:16 模板生成

**场景 B：在现有海报基础上迭代**
→ 先读现有文件 → 精确修改 → 对照 checklist → 递增版本号

**场景 C：制作无价格版**
→ 复制现有版本 → 删除 `.price-row` 整块 → 命名加 `-no-price`

**场景 D：渠道适配**
→ 修改 QR 图片路径 → 保留注释说明渠道

---

## 注意事项

- **不要**在 `aicamp_cc/` 或其他 AI CAMP 文件夹里改文件，只在 `ClawCAMP/` 目录操作
- **不要**强制 QR 图片为正方形（`height: auto` 保持原比例）
- **不要**在首发海报里放详细模块列表（那是长图的内容）
- **不要**只写"带手机"，必须是"带电脑和手机"
- 英文 slogan 传播力弱，优先用中文金句
