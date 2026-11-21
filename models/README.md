# models/ — 模型副本区

## 铁律

**这里只放副本。** 原件永远在 `E:\comsol\COMSOL63\Multiphysics\applications\`，只读，不碰。

## 命名

```
<案例名>-<YYYYMMDD>.mph
```

例：

- `microwave-oven-20261121.mph`
- `rf-heating-20261122.mph`

同一案例改第二个版本：`microwave-oven-20261121-v2.mph`。

## 每个副本必须配一个同名 `.md` 说明

```markdown
# microwave-oven-20261121

- 来源：E:\comsol\COMSOL63\Multiphysics\applications\RF_Module\Microwave_Heating\microwave_oven.mph
- 原始大小：1.85 MB
- 改了什么：<相对原件改了哪些节点>
- 为什么改：<目的>
- 结果：<跑出来什么>
```

**不写来源 = 这份副本不可追溯，等于废文件。**

## 复制命令（PowerShell）

```powershell
Copy-Item -LiteralPath 'E:\comsol\COMSOL63\Multiphysics\applications\RF_Module\Microwave_Heating\microwave_oven.mph' `
          -Destination 'D:\微波\ai工作区\models\microwave-oven-20261121.mph'
```

`Copy-Item` 只读源、只写目标，不修改原件。
