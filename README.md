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

## 🌟 这套模式的与众不同

- **民主不是摆设** — 团队可以投票否决老板，真的会
- **角色有性格** — 不是四个工具人，是四个有脾气的队友
- **说真话是规矩** — 第9条规矩明文规定，阿审负责监督
- **即开即用** — 5分钟配置，马上能跑

---

*版本：v1.0 | 发布：2026-03-20 | 维护：阿总*
