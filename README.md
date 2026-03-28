# Agent 自我进化与记忆丢失解决方案

> 一行代码解决 AI 助手"每次都要纠正"的问题

## 核心问题

你是否遇到过：

- AI 说"记住了"，但下次还是犯同样的错
- 纠正了3-4次，同样的问题还在出现
- Context 被清理后，AI 完全失忆，不知道你们之前做了什么
- 每次都要重新告诉 AI 你是谁、你想要什么

**这不是 AI 的问题，是记忆系统的设计问题。**

---

## 解决方案架构

```
Session 启动 → 读 MEMORY.md + principles.md + 今日日志
     ↓
用户纠正 → incidents.md 记录 → 判断是否升格为 principle
     ↓
Principle 验证 → 状态更新（new → verifying → verified）
     ↓
下次遇到同类场景 → 自动触发原则 → 不再犯
     ↓
Heartbeat 每4小时 → 后台双重保险
```

---

## 文件说明

| 文件 | 作用 |
|------|------|
| `principles.md` | 触发式行为准则，带触发条件声明 |
| `incidents.md` | 事件记录，根因分析，对应原则 |
| `MEMORY.md` | 长期记忆，项目状态，用户偏好 |
| `memory/日志/YYYY-MM-DD.md` | 每日摘要，上下文恢复用 |
| `HEARTBEAT.md` | 心跳检查逻辑，每4小时执行 |
| `AGENTS.md` | Session 启动流程配置 |
| `SOUL.md` / `USER.md` | AI 身份与用户信息 |

---

## 快速开始

### 1. 创建文件结构

```
~/.openclaw/workspace/
├── MEMORY.md
├── principles.md
├── incidents.md
├── HEARTBEAT.md
├── AGENTS.md
└── memory/日志/
    └── YYYY-MM-DD.md
```

### 2. 配置 Session Startup

在 `AGENTS.md` 中添加：

```markdown
## Session Startup

Before doing anything else:
1. Read `MEMORY.md` — projects, configs, active principles
2. `memory/日志/YYYY-MM-DD.md` — 今日工作摘要
3. `principles.md` — scan and match trigger conditions
```

### 3. 配置 Heartbeat

在 OpenClaw config 中设置：

```json
{
  "agents": {
    "defaults": {
      "heartbeat": {
        "every": "4h",
        "target": "last"
      }
    }
  }
}
```

---

## 核心设计原则

1. **你的判断是最终标准** — Principle 的验证和降级都由你决定
2. **Trigger > Memory** — 知识要有触发条件，不是存着等用
3. **双重保险** — 每次对话处理 + Heartbeat 后台兜底
4. **防失忆** — Daily log 确保上下文清理后能恢复

---

## License

MIT
