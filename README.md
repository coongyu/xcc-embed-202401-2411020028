# 嵌入式实验仓库

| 项目 | 内容 |
| --- | --- |
| 姓名 | 钟嘉豪 |
| 班级 | 1 班（xcc-embed-202401） |
| 学号 | 2411020028 |
| 课程 | 嵌入式系统实验 |
| 开发环境 | STM32CubeIDE + STM32F4xx HAL 库 |
| 目标板 | STM32F407ZETX |

## 仓库说明

本仓库用于存放课程全部嵌入式实验代码、实验文档与现象截图。所有实验统一放在本仓库内，**每个实验一个子文件夹**，不另建新仓库；每完成一个完整实验即 push 一次到本公开仓库。

## 实验目录

| 实验 | 文件夹 | 内容说明 |
| --- | --- | --- |
| 实验 1 | [`0501_LEDWater/`](0501_LEDWater/) | GPIO 输出：GPIOF 控制 LED1~LED8 逐位点亮，实现流水灯（低电平点亮，软件延时约 1 s） |
| 实验 2 | [`0602_MatrixKey/`](0602_MatrixKey/) | 矩阵键盘：3×4 键盘行扫描 + 16 ms 软件消抖，键值 1~12 以 8421BCD 显示在 PF0~PF7 |
| 实验 3 | 待添加 | — |
| 实验 4 | 待添加 | — |

## 各实验目录结构

以 `0501_LEDWater/` 为例，两个实验结构一致：

```
0501_LEDWater/
├── Core/            # 用户代码：main.c、gpio.c、时钟与中断配置
│   ├── Inc/
│   └── Src/
├── Drivers/         # STM32F4xx HAL 驱动与 CMSIS
├── Startup/         # 启动文件 startup_stm32f407zetx.s
├── docs/            # 时序说明脚本与示意图
├── *.ioc            # STM32CubeMX 工程配置
├── .cproject        # STM32CubeIDE 工程配置
└── STM32F407ZETX_FLASH.ld
```

## 关于编译产物

根目录 `.gitignore` 已过滤 Keil / STM32CubeIDE 的编译中间产物，以下内容**不进入仓库**：

- 目标文件与镜像：`*.o`、`*.d`、`*.elf`、`*.hex`、`*.axf`、`*.map`
- 构建目录：`build/`、`Debug/`、`Release/`、`*/Debug/`、`*/Release/`
- IDE 与调试器个人配置：`*.uvgui*`、`*.uvoptx`、`.settings/`、`*.launch`、`.metadata/`、`*.ioc.bak`

因此克隆后需在 STM32CubeIDE 中重新 Build 生成可执行文件。
