# M3 - Multi-stage Training Framework

## 基本信息
- 图片编号: M3
- 目标文件路径: figures/architecture/training_framework.png
- 对应章节: sec04.tex (Multi-stage Training Framework)
- 建议分辨率: 1264×848 (横版)

## 图片内容描述

三阶段渐进式训练时间线图，从左到右，色彩由浅到深渐进：

**阶段一 - Low-Resolution Pre-training：**
- 浅蓝背景色块
- 分辨率：256×256
- 数据：ImageNet-1K
- 关键技术：Rectified Flow, Dual Encoder (CN-CLIP + Qwen3), Logit-Normal Sampling
- 硬件：56-node Sugon K100, 30K steps
- 优化：Feature Pre-computation

**阶段二 - Progressive Resolution Increasing：**
- 中蓝背景色块
- 分辨率渐进：256 → 512 → 1024（用阶梯图表示）
- 数据切换：ImageNet-1K → 9M Chinese Image-Text Pairs
- 关键技术：2D RoPE Interpolation, Dynamic Shift Factor
- 硬件：56-node K100, 150K steps

**阶段三 - Inference Step Compression：**
- 深蓝背景色块
- 步数压缩：28 → 4 steps
- 方法：DMD2 + Real-world Sample Anchors
- 结果：7× latency reduction

三个阶段之间用粗渐变箭头连接。每个阶段下方标注关键超参数（lr, batch size, steps）。

## Caption
"The multi-stage training framework of JuZhou. Stage 1 establishes foundational visual representations at 256×256 using ImageNet-1K with Rectified Flow and a dual text encoder. Stage 2 progressively scales resolution to 1024×1024 while transitioning to 9M Chinese image-text pairs. Stage 3 compresses the inference trajectory from 28 to 4 steps via DMD2 distillation, achieving 7× latency reduction."

## ERNIE-Image 提示词

```
一张学术论文训练框架流程图，白色干净背景，从左到右三个渐进色深蓝色色块区域，颜色由浅蓝逐渐过渡到深蓝。

第一个区域浅蓝色背景，顶部大标题 "Stage 1: Low-Res Pre-training"。内部元素：
- 中心大方块标注 "256×256"
- 左侧小方块 "ImageNet-1K"
- 右侧小方块 "Rectified Flow"
- 下方一行小标签 "CN-CLIP + Qwen3 | Logit-Normal | 30K steps"

第一个区域右侧用渐变色粗箭头连接到第二个区域。

第二个区域中蓝色背景，顶部大标题 "Stage 2: Progressive Resolution"。内部元素：
- 中心一个从低到高的阶梯图形，标注三个刻度 "256 → 512 → 1024"
- 左侧方块 "ImageNet-1K" 上面有一个叉号，右侧方块 "9M Chinese Pairs" 上面有勾号，表示数据切换
- 下方小标签 "RoPE Interpolation | Dynamic Shift | 150K steps"

第二个区域右侧用渐变色粗箭头连接到第三个区域。

第三个区域深蓝色背景，顶部大标题 "Stage 3: Step Compression"。内部元素：
- 中心大方块标注 "28 steps" 向右箭头指向 "4 steps"，箭头上方标注 "DMD2"
- 下方红色高亮标签 "7× Speedup"
- 小标签 "Real-world Anchors | 4-step Inference"

最右侧输出区域标注 "Mobile-Ready Model"。

整体渐进式色彩变化暗示能力从低到高递进，标注使用英文无衬线字体。
```
