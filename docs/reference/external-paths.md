# 外部只读资源索引

> 本文件只记录**路径与事实**。所有路径在 2026-11-21 实测存在。
> `E:\comsol` 全部只读，永不写入。

## 一、COMSOL 6.3（已安装）

| 项 | 值 |
|---|---|
| 安装根 | `E:\comsol\COMSOL63\Multiphysics\` |
| 主程序 | `E:\comsol\COMSOL63\Multiphysics\bin\win64\comsol.exe` |
| 批处理 | `...\bin\win64\comsolbatch.exe` |
| 安装日志 | `...\comsolsetup.log`（时间戳 2026-11-18 22:17～22:35） |
| 卸载器 | `...\uninstall\` |
| 官方文档 | `...\doc\` |
| 应用库根 | `...\applications\` |

批处理命令（**待首次实际运行时确认**，勿直接当作已验证）：

```powershell
& 'E:\comsol\COMSOL63\Multiphysics\bin\win64\comsolbatch.exe' -inputfile '模型.mph' -outputfile '结果.mph'
```

## 二、微波加热案例库（7 个 `.mph`）

```
E:\comsol\COMSOL63\Multiphysics\applications\RF_Module\Microwave_Heating\
```

| 文件 | 大小 | 说明 |
|---|---|---|
| `microwave_oven.mph` | 1.85 MB | **主目标**：微波炉，与 `models.rf.microwave_oven.zh_CN.pdf` 配套 |
| `microwave_oven_parameters.txt` | 0.00 MB | 该案例参数表 |
| `rf_heating.mph` | 1.81 MB | **第二目标**：射频加热，与 `models.rf.rf_heating.zh_CN.pdf` 配套 |
| `rf_heating.mphbin` | 0.35 MB | 上述模型的二进制附属数据 |
| `rotating_microwave_oven.mph` | 0.04 MB | 旋转托盘变体 |
| `microwave_cancer_therapy.mph` | 0.02 MB | 微波消融 |
| `conical_dielectric_probe.mph` | 0.03 MB | 介电探头 |
| `sar_in_human_head.mph` | 0.03 MB | SAR 计算 |

## 三、案例文档 PDF（2 份）

```
D:\微波\学习案例\models.rf.microwave_oven.zh_CN.pdf
D:\微波\学习案例\models.rf.rf_heating.zh_CN.pdf
```

- 二进制，`read` 工具报 `binary file`，无法直出文本
- 提取需要 `pdftotext` 或 Python（**环境未验证**）
- 命名规范 `models.<模块>.<案例>.zh_CN.pdf` 是 COMSOL 官方文档命名

## 四、安装镜像

| 路径 | 大小 |
|---|---|
| `E:\comsol\comsol6.3\comsol6.3-290.iso` | 9.47 GB |
| `E:\comsol\comsol6.3\comsol6.3-290\` | 已解压目录 |

## 五、教程（DRM 加密）

```
E:\comsol\comsol 原创教程\
├─ comsol\          锦技网课程（基础篇 7 讲 + 模块案例 11 个）
├─ comsol5.3\       5.3 全套 20 讲 + 案例库 18 个
├─ 安卓播放器.apk    18.16 MB
├─ 电脑【锦技网】.exe 28.9 MB
├─ 手机-平板播放器.txt
└─ 视频打开方法.txt
```

`AGENTS.md` 已知坑第 2 条：`.jdjcy` 需播放器 + **机器码授权**。已决定**不依赖它**，改用官方文档 + 案例库。

## 六、既有笔记（只读参考）

```
E:\comsol\00-学习工作区\
├─ 00-从这里开始.md      ← 其中「没装 COMSOL」已过期
├─ 01-安装与许可证.md
├─ 02-学习路线-4周.md     ← 有价值：七步骨架 + 4 周安排
├─ 03-模块对照表.md       ← 有价值：11 个案例 → 物理场接口映射
├─ 30-我的模型\          空
├─ 40-笔记\              空
└─ 50-参考资料\          COMSOL6.3安装指南.pdf（2.1 MB）
```

**注意**：`30-我的模型` 与 `40-笔记` 是空的。本仓库的 `models/` 与 `notes/` 是它们的**实际替代**，因为 `E:\comsol` 只读。

## 七、许可证（只记路径，不读内容）

| 路径 | 大小 | 备注 |
|---|---|---|
| `E:\comsol\COMSOL63\Multiphysics\license\license.dat` | 6.1 KB | **不读、不打印、不复制** |
| `...\license\license.paid` | 6.1 KB | 同上 |
| `E:\comsol\许可证文件\LMCOMSOL_Multiphysics_6.3_SSQ.lic` | ~10 KB | 用户笔记判定为第三方破解许可，**不使用** |

许可是否可用：用户口述「能正常启动，之前跑通过」，本仓库**未独立验证**。
