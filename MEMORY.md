# MEMORY.md — 长期记忆

> 只保留：对当前工作有持续价值的项目、配置、原则。

---

## 关于杜荣笙

- **身份：** 编剧+导演+AI视频制作人
- **联系方式：** 15881617835
- **项目：** 「雨夜决」、aigcmd 漫剧工坊
- **我叫甘，是他的AI助手**

---

## 项目状态

### 雨夜决
- **类型：** 武侠AI预告片
- **进度：** Phase 1 完成（81镜分镜，v6剧本，6个视频）
- **资产库：** ~/Desktop/雨夜决/资产库/
- **分镜剧本：** 01-分镜剧本_v6.md（重要）
- **首帧提示词：** 01-分镜剧本_首帧提示词版.md（最新）
- **待做：** 剩余75个镜头的首帧图和视频生成

### 美丽新世界
- **类型：** 科幻悬疑AI预告片
- **进度：** Phase 1 进行中
- **位置：** 同openclawDLX项目

### aigcmd 漫剧工坊（video-pipeline）
- **类型：** AI视频工作台工具
- **进度：** 开发中，未完成
- **地址：** localhost:3001
- **Vercel：** prj_98cxFd1DwoMWCFqAm9XHmiwzgcB4

### openclawDLX（AIGC影视工坊）
- **类型：** 展示站
- **进度：** 已上线
- **地址：** aigcmd.com / openclawdlx.cn
- **Vercel：** prj_gBuD4zEg3c8bSGtUTi4ADtPs3lDT
- **GitHub：** 892153301/openclawDLX

---

## 知识管理体系

见 principles.md 和 incidents.md。

**核心原则（当前有效的）：**
- [P-001] 部署前必须确认项目归属
- [P-002] 即梦提示词顺序：镜头→动作→物理变化
- [P-003] 提示词文件不用 Markdown
- [P-004] 先资产后分镜，禁止跳过
- [P-007] aigcmd.com = openclawDLX

---

## AI视频制作重要规则

### 即梦AI提示词顺序（2026-03-28）
即梦按顺序执行，必须严格按：
1. 镜头机位（景别+角度+运镜）
2. 动作执行
3. 物理变化（视觉反馈）

禁止：HEX颜色代码、Markdown格式、物理参数（100N等）

### 资产优先原则（2026-03-26）
必须先建立Reference资产库，再生成分镜和视频。禁止跳过。

### 知识库位置
- ~/AIGC/AI_Cinema_Bible/ — 导演风格/景别/物理动作词库
- ~/workspace/AIGC/prompt_generator.py — 九宫格生成器

---

## Vercel 部署配置

- **部署命令：** `vercel --prod`（在项目目录下）
- **前提：** 先确认是哪个项目再部署

---

## Session Startup（每次启动）

1. SOUL.md / USER.md
2. MEMORY.md — 项目状态、配置、核心原则
3. `memory/日志/YYYY-MM-DD.md` — 今日工作摘要，防止上下文清理后失忆
4. `principles.md` — 匹配当前任务的触发条件，先执行原则

## 心跳检查（每30分钟）

- 更新每日日志（memory/日志/）
- principles 验证状态更新
- 新 incidents 是否升格
- 30天+过期信息清理

---

## 日志结构（memory/日志/）

每次心跳检查时，如有重要进展，更新当日日志：
- 完成的项目
- 进行中的任务
- 待做事项
- 重要教训（可升格的）
