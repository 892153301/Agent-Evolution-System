# HEARTBEAT.md

## 心跳检查（每4小时一次）

检查完成后，发送简短报告到活跃 session。

---

### 检查项目

1. **每日日志** — 检查 memory/日志/今天 是否存在，无则创建
2. **Principles 状态** — 扫描 verifying 状态，记录待验证项
3. **Incidents** — 扫描未处理项
4. **Incidents 归档** — 扫描已关闭 + 创建超过 15 天的项，移动到 `incidents/YYYY-MM.md`
5. **原则管理三查** — 新建原则前是否执行了三查（MEMORY/现有原则/分类）
6. **异常** — 检查有没有需要立即处理的问题

---

### 报告格式

```
[心跳] 系统正常 | principles: X verified, Y verifying | 待处理: Z
```

如果有异常需要你关注，报告具体问题，不要发送 HEARTBEAT_OK。

---

如果一切正常，发送上面的简短报告即可。
