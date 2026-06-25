# M6 - Inference Latency Comparison

## 基本信息
- 图片编号: M6
- 目标文件路径: figures/architecture/latency_comparison.png
- 对应章节: sec06.tex (Edge Device Deployment)
- 建议分辨率: 1264×848 (横版)

## 图片内容描述

分组柱状图，展示各设备端到端推理延迟：

**横轴（4 个设备）：**
- Xiaomi 17 Pro Max (SM8850)
- iQOO Neo11 (SM8750)
- Redmi K60 (SM8475)
- iPhone 15 Pro (A16)

**纵轴：** 延迟（秒）0 - 14s

**每组两个柱体：**
- 蓝色：w/o Prompt Refinement（仅 CLIP+UNet+VAE）
- 橙色：w/ Prompt Refinement（含 Qwen3 重写）

**数值标注：**
| 设备 | w/o | w/ |
|------|-----|-----|
| Xiaomi 17 Pro Max | 2.9s | 4.5s |
| iQOO Neo11 | 3.5s | 5.1s |
| Redmi K60 | 9.5s | 12.7s |
| iPhone 15 Pro | 4.25s | N/A |

**iPhone 标注：** "FP16, no prompt refinement"

## Caption
"End-to-end inference latency across mobile platforms. On flagship Android devices (Xiaomi 17 Pro Max), the full pipeline with prompt refinement completes in 4.5 seconds. The iPhone 15 Pro runs the CLIP-UNet-VAE branch in 4.25 seconds under FP16 precision without quantization."

## ERNIE-Image 提示词

```
一张学术论文风格的分组柱状图，白色干净背景，现代信息图风格。

标题位于图片顶部中央，写着 "End-to-End Inference Latency"。

图表区域：
- 横轴（X轴）有 4 个刻度标签，从左到右："Xiaomi 17 Pro Max"、"iQOO Neo11"、"Redmi K60"、"iPhone 15 Pro"
- 纵轴（Y轴）刻度从 0 到 14 秒，每隔 2 秒一条浅灰色水平网格线，轴标签 "Latency (seconds)"

前三个设备（Android）每个刻度上有两根并排柱体：
- 浅蓝色柱体标注 "w/o Refinement"
- 橙色柱体标注 "w/ Refinement"

柱体高度：
Xiaomi 17 Pro Max 组：浅蓝 2.9s, 橙色 4.5s
iQOO Neo11 组：浅蓝 3.5s, 橙色 5.1s
Redmi K60 组：浅蓝 9.5s, 橙色 12.7s

每根柱体顶部标注具体秒数。

iPhone 15 Pro 组只有一根浅蓝色柱体，高度 4.25s，上方标注 "FP16, No Quantization"。

右上角图例区域：蓝色色块 "w/o Prompt Refinement"，橙色色块 "w/ Prompt Refinement"。

柱体带圆角顶部，整体风格简洁，无衬线英文字体。
```
