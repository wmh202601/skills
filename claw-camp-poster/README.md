# 🎨 claw-camp-poster Skill

> 为 Claw CAMP 课程设计和迭代 HTML 海报

---

## 功能

- 生成**首发海报**（9:16，420×747px）——适合微信群 / 朋友圈直接转发
- 生成**详情长图**（可滚动）——适合感兴趣后发送完整信息
- 自动应用品牌规范（无需每次解释）
- 支持无价格版本（Jenny / Angel 渠道用）
- 内置 Checklist，防止常见错误

## 品牌规范

| 项目 | 值 |
|---|---|
| 主色 | `#FF6D3A`（Claw 橙）|
| 深橙 | `#E84D1A` |
| 彩条 | 橙 / Google红 / Google黄 / Google绿（各 25%）|
| 字体 | Inter + Noto Sans SC（Google Fonts）|
| 首发海报尺寸 | 420 × 747px（9:16）|
| QR 码 | `height: auto`（不强制正方形）|

## Eval 结果

| 测试 | 得分 |
|---|---|
| with-skill（首发海报）| 7 / 7 ✅ |
| without-skill（首发海报）| 2 / 4 ❌ |
| with-skill（长图）| 5 / 5 ✅ |

## 使用方法

将本仓库加入 OpenClaw `extraDirs` 或 Claude Code `CLAUDE.md`，然后直接说：

```
帮我做一张第1期首发海报，4月18-19日深圳，已满8/12席，不含价格
```

Skill 会自动触发，按规范输出到 `ClawCAMP/` 目录。

## 定制

替换以下内容适配你的品牌：
- `references/brand.md` — 品牌色、字体、布局规范
- `references/poster-types.md` — 海报类型和 Checklist
- 触发 description 里的 `Claw CAMP` → 你的品牌名

---

🦞 Made with [ClawCAMP](https://github.com/wmh202601) · MIT License
