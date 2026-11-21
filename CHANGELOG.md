# CHANGELOG

> 只追加，不改历史。状态去 `STATUS.md`，理由去 `docs/adr/`。

## 2026-11-21 · 阶段 0：共享状态底座

**新建**

- `AGENTS.md` — §0 的 12 问由用户口述确认并记录；§1–§10 按实际项目改写（原文为未填模板）
- `README.md` — 三块资产、AI 接入三步、铁律
- `STATUS.md` — 唯一进度真相（含置信度与风险表）
- `HANDOFF.md` — 交接头（含"给下一个 AI 的三条硬规则"）
- `CHANGELOG.md` — 本文件
- `docs/architecture.md` — 目录契约、数据流、边界
- `docs/reference/external-paths.md` — COMSOL / 案例库 / PDF / 教程 / 许可证的路径索引
- `docs/adr/0001-边界与单一真相.md` — 决策：全部只读 `E:\comsol`，写区收敛到 `D:\微波`
- `docs/adr/0002-多AI协作协议.md` — 决策：单一真相、文件所有权、最新优先、交接五段
- `notes/笔记模板.md` — 5 行笔记 + 七步骨架可勾选清单
- `models/README.md` — 副本命名与来源标注规则
- `docs/reference/ai-onboarding.md` — 给 Gemini / Claude / Codex 的接入提示词（复制即用）
- `tasks/active/TASK-20261121-001-工作区基建/` — 本轮任务目录（含 `metadata.json` 与盘点产物）

**盘点结论（只读，未改动 `E:\comsol`）**

- `E:\comsol`：4667 个文件 / 21.64 GB（深度 ≤5），987 个 `.mph`
- COMSOL 6.3 已安装于 `E:\comsol\COMSOL63\Multiphysics\`（安装日志 11-18 22:17～22:35）
- 微波加热案例库 7 个 `.mph` 定位在 `applications\RF_Module\Microwave_Heating\`
- 既有笔记 `E:\comsol\00-学习工作区\` 4 份，其中「未安装 COMSOL」已过期

**该步未做**

- 未做任何实际求解
- 未启用 git

## 2026-11-21 · 阶段 1 第 1 步：案例文档提取

**新增**

- `tasks/active/TASK-20261121-002-案例文档提取/output/microwave_oven-zh.txt`（31.7 KB / 862 行 / 32 页）
- `tasks/active/TASK-20261121-002-案例文档提取/output/rf_heating-zh.txt`（20.5 KB / 604 行 / 24 页）
- `tasks/active/TASK-20261121-002-案例文档提取/metadata.json`
- `notes/两个案例对照-20261121.md`

**工具**

- `pdftotext`（MiKTeX，参数 `-enc UTF-8 -layout`）退出码 0，中文正常；有 Windows 10 弃用告警，不影响输出

**关键事实（来自文档正文，非推测）**

- `microwave_oven`：2.45 GHz / TE10 / 1 kW（对称减半后 500 W）/ 铜 + 阻抗边界 / 玻璃板 + 球形土豆 / **单向**耦合；官方结论「土豆吸收约 **60%** 输入功率，其余大部分反射」
- `rf_heating`：10 GHz / 100 W / 弯曲波导 / 铝 + 内壁铜涂层 / 介质块 tanδ=0.001(T/300K)、k=0.3(T/300K) / **双向**耦合 / 频域-瞬态 或 频域-稳态；升温需数分钟
- 两案例的差别就是**单向 vs 双向耦合**——这决定了学习顺序：先 oven，后 rf_heating
