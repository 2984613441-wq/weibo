# ai工作区

> 这个仓库只做一件事：**把「微波加热 / COMSOL」这件事的共享状态存下来，让人和多个 AI 共用同一份真相。**

## 为什么需要它

2026-11-21 之前，材料散在三处，状态只活在对话里：

| 位置 | 内容 | 问题 |
|---|---|---|
| `E:\comsol\COMSOL63\` | COMSOL 6.3 安装体 + 987 个 `.mph` 案例 | 太大（21.6 GB），且只读 |
| `E:\comsol\00-学习工作区\` | 4 份 md 笔记 | 写于装机之前，部分已过期 |
| `D:\微波\学习案例\` | 2 份官方模型文档 PDF | 只有文档，没有笔记 |

后果：换一个 AI 就要从头讲一遍；四份笔记互相打架；没人知道"现在做到哪"。

## 三块资产

| 资产 | 位置 | 权限 |
|---|---|---|
| COMSOL 6.3 安装体 | `E:\comsol\COMSOL63\Multiphysics\` | **只读** |
| 微波加热案例库（7 个 `.mph`） | 同上 `applications\RF_Module\Microwave_Heating\` | **只读**，改动先复制 |
| 案例文档 PDF（2 份） | `D:\微波\学习案例\` | 只读 |

## 怎么用

### 人（29845）

1. 打开 `STATUS.md` 看现在做到哪
2. 打开 `notes/` 看积累的笔记
3. 要做模型：把 `.mph` 复制到 `models/`，在副本上改

### 新 AI（Gemini / Claude / Codex）接入三步

1. 读 `AGENTS.md`（尤其 §0 的 12 问和 §5 边界）
2. 读 `STATUS.md` + `HANDOFF.md`
3. 读 `docs/architecture.md` + `docs/reference/external-paths.md`

三步读完就能接上，**不需要问用户"我们之前在做什么"**。

## 目录

```
ai工作区/
├─ AGENTS.md      契约（12 问已填）
├─ README.md      本文件
├─ STATUS.md      唯一进度真相
├─ HANDOFF.md     交接头
├─ CHANGELOG.md   交付清单
├─ docs/
│  ├─ architecture.md
│  ├─ reference/external-paths.md
│  └─ adr/        决策记录
├─ tasks/
│  ├─ active/
│  └─ completed/
├─ notes/         学习笔记（5 行格式）
└─ models/        自己改过的 .mph 副本
```

## 铁律

- `E:\comsol` 只读，永不写入
- 许可证文件永不读取、不打印、不复制
- 交付 = 产物 + 证据；自述不算
- 开工前置信度 ≥ 0.9，不够就先问
