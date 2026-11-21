# HANDOFF — 交接头

```
commit:  b66a28f（main，已推送 origin）
remote:  git@github.com:2984613441-wq/weibo.git  （weibo = 微波）
updated: 2026-11-21 17:30 (Asia/Shanghai)
by:      lead (DSH / DeepSeek Harness)
status:  阶段 0 完成 + 阶段 1 第 1 步完成（文档已提取，模型尚未开始）
next:    阶段 1 第 2 步 —— 复制 microwave_oven.mph 到 models/ 并对照 txt 核对设置
```

## 一、已完成

**阶段 0 · 共享状态底座**

- `AGENTS.md` §0 的 12 问由用户口述确认并记录
- 新建 `STATUS.md` / `HANDOFF.md` / `CHANGELOG.md` / `README.md`
- 新建 `docs/architecture.md`、`docs/adr/0001`、`docs/adr/0002`、`docs/reference/{external-paths,ai-onboarding}.md`
- 新建 `notes/笔记模板.md`、`models/README.md`、`tasks/` 结构

**阶段 1 第 1 步 · 案例文档提取**

- 两份 PDF → 文本（862 行 / 604 行），工具 `pdftotext`（MiKTeX）
- 产出 `notes/两个案例对照-20261121.md`
- 确认 COMSOL 6.3 已安装、批处理入口 `comsolbatch.exe` 存在（未执行）

**没有改动 `E:\comsol` 任何内容**（顶层 mtime 仍为 11-18 / 2024）。

## 二、给下一个 AI 的三条硬规则

1. **先读 `STATUS.md`，再读本文件**。不要从对话里猜进度，对话不在你的上下文里。
2. **`E:\comsol` 只读**。要改 `.mph`，先复制到 `models/`，在副本上改。
3. **交付 = 产物 + 证据**。说"完成"必须附路径、命令、输出，并列出没做到的。

## 三、接手时先确认的三件事

1. `STATUS.md` 的 `updated` 是不是你这次会话之前的？是就说明有人改过，先读 `CHANGELOG.md`。
2. 有没有别的 AI 正在写同一个文件？见 `docs/adr/0002` 的文件所有权表。
3. 用户当前的「问题」有没有变？`AGENTS.md` §0 只记了方向（微波加热专项），具体对象仍未定。

## 四、已知未做 / 留给后面

- **未做任何实际求解**——COMSOL 能否跑通仍只有用户口述
- 未复制任何 `.mph`，案例库保持原样
- 土豆等材料的介电常数具体数值未抄录
- 文档插图（图 1~4）是图片，文本中只有图注
- 未启用 git
- 用户自己的建模对象未定义（阶段 1 不阻塞，阶段 2 需要）

## 五、当前置信度

| 项 | 置信度 | 依据 |
|---|---|---|
| `E:\comsol` 结构 | 0.95 | 实测 4667 文件、目录树、日志时间戳 |
| COMSOL 已安装 | 0.95 | `comsol.exe` + `comsolsetup.log` |
| COMSOL 可求解 | 0.60 | 仅用户口述，无求解记录 |
| microwave_oven 复现路径 | 0.90 | 文档正文已提取，参数与案例路径确认 |
| 跑出「60% 吸收功率」 | 0.70 | 有官方目标值，但模型设置是否与文档一致未验证 |
| 「改成自己的对象」 | 0.30 | 对象未定义 |
