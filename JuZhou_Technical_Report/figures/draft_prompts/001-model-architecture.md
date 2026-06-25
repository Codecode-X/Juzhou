# M1 - Model Architecture Overview

## 基本信息
- 图片编号: M1
- 目标文件路径: figures/architecture/model.png
- 对应章节: sec03.tex (Ultra-Lightweight Architecture Design)
- 建议分辨率: 1264×848 (横版)

## 图片内容描述

整体框架架构图，从左到右的流水线布局：

**左侧 - 文本编码（Text Encoding）：**

- 两个分支：CN-CLIP（中文语义）和 Qwen3（语言理解）
- Prompt -> Qwen3 -> CN-CLIP
- Prompt 先经过 Qwen3 润色之后 再给 Chinese Clip
- 最终有一个箭头到 conditioning pathway（指向我们的模型）

**中间 - 去噪网络（0.4B Denoising U-Net）：**
- 核心模块标注：MQA (Multi-Query Attention)、2D RoPE、Separable Conv
- 高分辨率阶段标注"No Self-Attention"
- 输入：噪声 latent + timestep + text embedding
- Rectified Flow 箭头标注训练范式

**右侧 - 解码（1M VAE Decoder）：**

- 极简结构，标注"No Attention Layers"
- 输出：1024×1024 生成图像

**底部 - 蒸馏路径：**
- DMD2 蒸馏箭头：28 steps → 4 steps
- 标注 "7× speedup"

配色：深蓝主色调，白色背景，浅灰辅助线。各模块用圆角矩形框，连接用带箭头的线条。

## Caption
"Overview of the JuZhou framework architecture. The dual text encoder (CN-CLIP + Qwen3) feeds into a 0.4B-parameter denoising U-Net optimized with MQA, 2D RoPE, and separable convolutions, followed by an ultra-compact 1M-parameter VAE decoder. DMD2 distillation compresses inference from 28 to 4 steps."

## ERNIE-Image 提示词

```
一张学术论文级别的技术架构图，白色干净背景，深蓝色主色调，扁平化矢量风格。

从左到右的流程布局，包含三个主要区域：

左侧区域标题 "Text Encoders"，包含两个并排的深蓝色圆角矩形方块，分别标注文字 "CN-CLIP" 和 "Qwen3-1.7B"，两个方块下方各有一个小标签分别写着 "Chinese Semantics" 和 "Language Understanding"。两个方块的右侧有汇聚箭头指向中间区域。

中间区域是一个大的圆角矩形，标题标注 "0.4B Denoising U-Net"，内部包含三个小方块分别标注 "MQA"、"2D RoPE"、"Sep. Conv"，右下角有一个红色小标签写着 "No Attn at Hi-Res"。大矩形左侧有输入箭头标注 "Noisy Latent + t"，上方有输入箭头标注 "Rectified Flow"。大矩形内部还有一个浅蓝色标签 "Parameters reduced by ~85%"。

右侧区域是一个小的圆角矩形，标题标注 "1M VAE Decoder"，内部简洁标注 "No Attention Layers"，右下角有浅灰色标签 "Compressed by 98%"。右侧输出箭头标注 "1024×1024 Image"。

底部有一条从中间区域出发的虚线箭头，指向右侧，标注 "DMD2 Distillation: 28 steps → 4 steps (7× speedup)"。

整体风格简洁专业，类似 CVPR/NeurIPS 论文中的架构图，线条清晰，配色统一，标注文字使用无衬线英文字体。
```
