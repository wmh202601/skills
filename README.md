# 🦞 ClawCAMP Skills Library

> OpenClaw + Claude Code 通用 Skills 库 · 欢迎 Fork 和 PR

由 [ClawCAMP](https://github.com/wmh202601) 开发维护。

---

## 什么是 Skill？

**Skill = 把你的业务知识编码进 AI 的工作手册。**

不是给 AI 的临时指令，而是把你团队的 SOP、品牌规范、质量 Checklist 沉淀成 AI 可以反复调用的能力。

```
没有 Skill：每次都要向 AI 解释一遍业务规则
有了 Skill：一句话，AI 按规范执行，结果一致
```

---

## 当前 Skills

### 🎨 [claw-camp-poster](./claw-camp-poster/)

为 **Claw CAMP** 课程设计和迭代 HTML 海报。

- **支持格式**：首发海报（9:16，420×747px）/ 详情长图
- **品牌规范**：橙色系（#FF6D3A）、四色彩条、白底卡片
- **Eval 通过率**：100%（7/7 assertions）
- **适合场景**：微信群 / 朋友圈传播

> ⚠️ 品牌细节（二维码、活动信息）需替换为你自己的内容

---

## 如何使用

### OpenClaw

在 `openclaw.json` 里配置 `extraDirs`：

```json
{
  "skills": {
    "load": {
      "extraDirs": ["/path/to/this/repo"]
    }
  }
}
```

重启 OpenClaw 后，在对话中直接触发即可（Skill 会自动注入）。

### Claude Code

在 `~/.claude/CLAUDE.md` 里添加：

```markdown
## Custom Skills Library

Skills are located at: /path/to/this/repo/
When starting any task, check if a skill exists in that directory for the task type.
If a matching SKILL.md is found, read it first and follow its workflow exactly.
```

---

## Skill 结构

每个 Skill 遵循标准结构：

```
skill-name/
├── SKILL.md              # 触发条件 + 工作流（必须）
├── references/           # 业务知识参考文件
│   ├── brand.md
│   └── guidelines.md
└── evals/
    └── evals.json        # 测试用例
```

---

## 创建自己的 Skill

参考 [skill-creator](./skill-creator/) 和 [anthropics/skills](https://github.com/anthropics/skills)。

**核心步骤**：
1. 找到你反复重复、每次都要解释的任务
2. 拆解业务知识：品牌规范 / 格式要求 / 防错 Checklist
3. 写 `SKILL.md`（description + 工作流 + references）
4. 用 `evals.json` 测试，用数据说话
5. 优化 description：**英中混合触发率更高**（机器跑出的结论）

> 💡 **发现**：纯中文 description recall≈0%；英文概念词 + 中文场景词混合后覆盖更广。  
> 原因：Claude 的语义推理在英文概念空间更精准，英文 `posters` 能覆盖「海报/长图/宣传图/传播图」等多种说法。

---

## Contributing

欢迎提交 PR！特别欢迎：
- 新 Skill（通用业务场景）
- 改进现有 Skill 的 description 或 Checklist
- 增加 evals 测试用例

---

## License

MIT © 2026 ClawCAMP

🦞 _如果这个库帮到了你，欢迎来 [ClawCAMP](https://github.com/wmh202601) 分享你的 Skill！_
