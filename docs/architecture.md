# 架构与目录契约

## 一、一句话

**一个写区（`D:\微波\ai工作区`）+ 一个只读区（`E:\comsol`）。** 所有产出只在写区生长，只读区只被引用。

## 二、目录表

| 目录 | 放什么 | 不放什么 | owner |
|---|---|---|---|
| `docs/` | 架构、外部路径索引、ADR 决策 | 笔记、模型、临时文件 | 任一 AI（ADR 追加制） |
| `docs/adr/` | 决策记录，编号递增，只追加 | 修改已接受的结论 | 提出决策的 AI |
| `docs/reference/` | 外部只读资源的真实路径与索引 | 副本、截图堆积 | 维护索引的 AI |
| `notes/` | 学习笔记，一个案例一篇 | 代码、`.mph` | 学习的人 |
| `models/` | 从案例库复制出来的 `.mph` 副本 | 原件、超大中间文件 | 建模的人 |
| `tasks/active/` | 进行中任务，`TASK-YYYYMMDD-NNN-短描述/` | 已完成的（移走） | 接任务的 AI |
| `tasks/completed/` | 已归档任务，保留可追溯 | — | — |

根目录只允许 5 个文件：`AGENTS.md` `README.md` `STATUS.md` `HANDOFF.md` `CHANGELOG.md`。

## 三、数据流

```
E:\comsol\COMSOL63\...\Microwave_Heating\microwave_oven.mph   （只读原件）
                    │
                    │ 复制
                    ▼
        models\microwave-oven-20261121.mph                     （可改副本）
                    │
      ┌─────────────┼─────────────┐
      ▼             ▼             ▼
  D:\微波\学习案例\   COMSOL 求解     notes\
  *.pdf（步骤）      （GUI/批处理）   第一份笔记
      │                             │
      └──────────┬──────────────────┘
                 ▼
            STATUS.md 更新（进度）
                 ▼
            HANDOFF.md 更新（交接）
```

## 四、边界

| 区域 | 权限 | 说明 |
|---|---|---|
| `E:\comsol\` 全部 | **只读** | 含安装体、案例库、教程、许可证目录 |
| `D:\微波\学习案例\` | 只读 | 两份 PDF 文档 |
| `D:\微波\ai工作区\` | 读写 | 唯一写区 |

违反边界的操作在 `AGENTS.md` §5 已列为「必须先问 / 永远不做」。

## 五、命名

- 目录与文件：`kebab-case`；中文名允许（历史资料是中文，保持一致）
- 任务目录：`TASK-YYYYMMDD-NNN-短描述`（NNN 当天递增，从 001）
- 模型副本：`<案例名>-<YYYYMMDD>.mph`，例：`microwave-oven-20261121.mph`
- 笔记：`<案例名>-<主题>.md`，例：`microwave-oven-第一遍复现.md`
- ADR：`NNNN-<决策标题>.md`，从 0001 起

## 六、深度与禁止

- 目录深度 ≤ 4 层
- 禁止同名嵌套（`docs/docs/`）
- 禁止根目录新增散落文件
- 归档不删除：完成的 `tasks/active/xxx` 移到 `tasks/completed/`
