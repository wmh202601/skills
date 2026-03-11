# Skills Library

共享技能库，同时供 **OpenClaw** 和 **Claude Code** 使用。

维护一次，两边共用。

## 使用方式

| 工具 | 加载方式 |
|------|----------|
| OpenClaw | `skills.load.extraDirs` 自动发现，根据 description 触发 |
| Claude Code | `~/.claude/CLAUDE.md` 指引，按需 read SKILL.md |

## 目录结构

```
skills/
├── README.md           ← 本文件
├── <skill-name>/
│   ├── SKILL.md        ← 必须，含 YAML frontmatter
│   ├── scripts/        ← 可选，辅助脚本
│   ├── references/     ← 可选，参考文档
│   └── assets/         ← 可选，静态资源
└── ...
```

## 现有技能

<!-- 新增 skill 后在这里更新 -->
| Skill | 描述 |
|-------|------|
| [skill-creator](./skill-creator/) | 创建、测试、迭代和优化 Skills 的元技能 |

## 添加新技能

1. 建目录 `skills/<skill-name>/`
2. 写 `SKILL.md`（参考 AgentSkills 规范）
3. 更新本 README 的技能列表
4. `git add . && git commit -m "add: <skill-name>"`

## 同步

```bash
cd ~/skills
git pull   # 拉取更新
git push   # 推送到远程（配置好 remote 后）
```
