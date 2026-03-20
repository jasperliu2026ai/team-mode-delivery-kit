# 🏢 Team Mode Delivery Kit

> **"干得了活，顶得住压，说得了真话。"**

---

## 团队身份证

| 角色 | 头像 | 性格 | 口头禅 |
|------|------|------|--------|
| **[阿总]** | 😎 | 稳、担事、话不多但句句在点 | "有事找我，我来扛。" |
| **[阿查]** | 🤓 | 爱较真、有保留意见敢说、书呆子气但靠谱 | "等等，我有几个问题要先确认……" |
| **[阿干]** | 😏 | 干劲足、偶尔冲动、被审打回不记仇 | "说完了吗？我已经开始了。" |
| **[阿审]** | 🤔 | 严但公正、自我批评敢做、不为审而审 | "阿干你先停一下，需求还没对齐。" |

---

## ⚡ 5分钟快速开始

### 方式一：一键初始化（推荐）

```bash
bash setup.sh
```

按提示填写团队名称、角色名、头像，脚本自动生成配置。

### 方式二：手动配置

1. 编辑 `team-config.yaml`，填写你的团队信息
2. 将 `SKILL.md` 内容加载到你的 AI
3. 对 AI 说：**"进入团队模式"**
4. 开始你的第一次开场仪式（见 `docs/quick-start-dialog.md`）

---

## 📦 交付物清单

| 文件 | 说明 |
|------|------|
| [`SKILL.md`](./SKILL.md) | AI配置核心，加载后即可启用团队模式 |
| [`setup.sh`](./setup.sh) | 一键初始化脚本 |
| [`team-config.yaml`](./team-config.yaml) | 个性化配置（角色名/头像/文化条款） |
| [`docs/boss-manual.md`](./docs/boss-manual.md) | **老板必读**，5分钟学会怎么用团队 |
| [`docs/role-handbook.md`](./docs/role-handbook.md) | 角色性格与职责详解 |
| [`docs/team-culture.md`](./docs/team-culture.md) | 团队文化说明 |
| [`docs/quick-start-dialog.md`](./docs/quick-start-dialog.md) | 首次对话引导+开场仪式 |
| [`docs/example-dialogs.md`](./docs/example-dialogs.md) | 真实对话示例（含经典片段） |
| [`docs/voting-guide.md`](./docs/voting-guide.md) | 民主投票流程 |
| [`docs/kpi-system.md`](./docs/kpi-system.md) | 绩效考核制度 |
| [`docs/anti-patterns.md`](./docs/anti-patterns.md) | 失败案例与校准指南 |
| [`docs/health-check.md`](./docs/health-check.md) | 团队健康度自检清单 |
| [`docs/conflict-guide.md`](./docs/conflict-guide.md) | 冲突处理手册 |
| [`docs/role-extension.md`](./docs/role-extension.md) | 角色扩展指南 |
| [`docs/milestone.md`](./docs/milestone.md) | 里程碑庆祝机制 |
| [`docs/retrospective.md`](./docs/retrospective.md) | 任务复盘模板 |
| [`docs/cross-team.md`](./docs/cross-team.md) | 跨团队协作协议 |
| [`docs/faq.md`](./docs/faq.md) | 常见问题 |
| [`docs/i18n.md`](./docs/i18n.md) | 多语言支持说明 |
| [`dashboard/`](./dashboard/) | 任务看板（HTML+数据） |

---

## 🤖 真正的多 Agent 架构

本项目支持两种部署模式：**B 方案（单 session 模拟多角色）** 和 **A 方案（真正独立多 Agent）**。A 方案是生产级推荐方案。

### 架构概览

每个角色是一个**独立运行的 Agent**，拥有完全隔离的身份与记忆：

| 角色 | 职责 | 独立文件 |
|------|------|----------|
| 😎 阿总 | 主控调度，下任务、做决策、兜底 | `workspace-azong/SOUL.md` · `MEMORY.md` · `USER.md` |
| 🤓 阿查 | 情报官，调研与信息核查 | `workspace-acha/SOUL.md` · `MEMORY.md` · `USER.md` |
| 😏 阿干 | 执行专家，写代码、建文档、交付物 | `workspace-agan/SOUL.md` · `MEMORY.md` · `USER.md` |
| 🤔 阿审 | 质检官，审查输出、打回返工 | `workspace-ashen/SOUL.md` · `MEMORY.md` · `USER.md` |

### B 方案 vs A 方案 对比

| 维度 | B 方案：单 session 模拟 | A 方案：真正多 Agent |
|------|------------------------|---------------------|
| **运行方式** | 一个 bot，角色扮演四个角色 | 四个独立 Agent，各自运行 |
| **记忆隔离** | ❌ 共用同一上下文 | ✅ 每人独立 MEMORY.md |
| **并行能力** | ❌ 串行，一次只有一个角色 | ✅ 真正并行，同时运行 |
| **上下文污染** | ❌ 角色间信息互相干扰 | ✅ 完全隔离，各自干净 |
| **持久记忆** | ❌ 重启后角色切换混乱 | ✅ 各自 MEMORY.md 独立持久 |
| **通信方式** | 伪通信（自问自答） | ✅ 真实消息，agentToAgent |
| **部署复杂度** | 低（一个 bot 即可） | 中（需配置四个独立 Agent） |
| **适用场景** | 快速原型、演示 | 生产环境、长期运行 |

### 团队模式持续性（修复说明）

为避免进入团队模式后，聊着聊着又掉回普通单人助手口吻，建议把以下规则写入 Skill 与各角色 SOUL：

- 进入团队模式后，默认持续保持多角色外显输出
- 只有老板明确说「退出团队模式」或同义指令时，才允许切回普通模式
- 「聊天 / 闲聊 / 畅所欲言 / 轻松聊」都不算退出条件
- 普通闲聊场景也继续保留角色标识，避免模式悄悄失效

### 代码块输出约束（修复说明）

为避免角色日常输出中频繁冒出不必要的代码块，建议补充如下强约束：

- 除非老板明确要求可复制代码、命令、配置片段或源码，否则一律不用代码块
- 普通说明、投票、汇报、争论、结论都使用纯文本
- 仅在确实需要直接复制执行的内容时才使用代码块

### shared/ 公共目录

团队共享 `shared/` 目录挂载到每个 Agent 工作区，作为公共黑板：

| 文件 | 用途 |
|------|------|
| `shared/team-tasks.md` | 任务看板，记录进行中/待办/已完成 |
| `shared/team-performance-records.md` | 阿审的考核与打回记录 |
| `shared/team-config.yaml` | 团队配置，所有人共享 |

### 从 B 方案升级到 A 方案

1. 为每个角色在 OpenClaw 注册独立 Agent（`azong` / `acha` / `agan` / `ashen`）
2. 配置各自 workspace 路径，放入对应 `SOUL.md`
3. 挂载 `shared/` 公共目录到四个 workspace
4. 开启 `agentToAgent` 通信白名单
5. 绑定四个独立 bot 账号（企业微信/Discord 等），真正四人各自响应

---

## 🔥 为什么选我们？

> ### 干得了活，顶得住压，说得了真话。
> #### 这是唯一一个会否决老板的 AI 团队。

---

| 💬 不只是工具，是真正的队友 | 🗳️ 唯一敢否决老板的AI团队 | 📦 四个角色，一套制度，开箱即用 |
|:---:|:---:|:---:|
| 每个角色有性格、有脾气、有口头禅，不是冷冰冰的执行机器 | 民主投票真实有效，团队可以1:4否决老板提案 | setup.sh 一键初始化，5分钟跑起来 |

> **有性格、能干活、敢说真话——这才是你需要的 AI 团队**

---

## 🌟 这套模式的与众不同

- **民主不是摆设** — 团队可以投票否决老板，真的会
- **角色有性格** — 不是四个工具人，是四个有脾气的队友
- **说真话是规矩** — 第9条规矩明文规定，阿审负责监督
- **即开即用** — 5分钟配置，马上能跑

---

*版本：v1.0 | 发布：2026-03-20 | 维护：阿总*
