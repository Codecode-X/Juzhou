# M5 - Edge Deployment Architecture

## 基本信息
- 图片编号: M5
- 目标文件路径: figures/architecture/deployment_architecture.png
- 对应章节: sec06.tex (Edge Device Deployment)
- 建议分辨率: 1264×848 (横版)

## 图片内容描述

双平台对比架构图，上下或左右分栏：

**上半区 - Android 部署（绿色主题）：**
- 标题 "Android Deployment"
- 输入：用户诗歌输入 → LoRA Qwen3-1.7B（Prompt Refinement）
- 中间模块分配：
  - CPU 路径：MNN 引擎 → Qwen3-1.7B (4-bit) + CLIP (8-bit)
  - NPU 路径：QNN SDK → UNet (8-bit) + VAE (8-bit)
- 三款设备：Xiaomi 17 Pro Max / iQOO Neo11 / Redmi K60
- 输出：生成图像

**下半区 - iOS 部署（蓝色主题）：**
- 标题 "iOS Deployment"
- 统一运行时：Core ML
- 三个模块：CLIP (FP16) → UNet (FP16) → VAE (FP16)
- 设备：iPhone 15 Pro (A16)
- 标注 "No quantization needed"

**中间分隔线标注：**
- "Same Model Architecture, Different Runtime"

## Caption
"Heterogeneous deployment architecture across Android and iOS platforms. On Android, the pipeline is partitioned between CPU (MNN engine for language model and text encoding) and NPU (QNN for UNet and VAE decoding). On iOS, all diffusion modules run on Core ML in FP16 precision without additional quantization."

## ERNIE-Image 提示词

```
一张学术论文风格的双平台部署架构对比图，白色干净背景，分为上下两个区域。

上方区域用浅绿色背景，左上角标题 "Android Deployment"。内部从左到右流程：
- 最左侧方块 "Poem Input"
- 箭头连接方块 "LoRA Qwen3-1.7B"（标注 "Prompt Refinement"）
- 分叉为上下两条路径：
  - 上面路径标注 "CPU"，内部包含两个方块 "MNN Engine"，分别标注 "Qwen3-1.7B (4-bit)" 和 "CLIP (8-bit)"
  - 下面路径标注 "NPU"，内部包含方块 "QNN SDK"，下方两个方块分别标注 "UNet (8-bit)" 和 "VAE (8-bit)"
- 两条路径汇聚到右侧方块 "Generated Image"
- 右下角小字标注设备 "Xiaomi 17 Pro / iQOO Neo11 / Redmi K60"

下方区域用浅蓝色背景，左上角标题 "iOS Deployment"。内部从左到右流程：
- 最左侧方块 "Text Input"
- 箭头连接三个并排方块，统一在方框 "Core ML" 内：依次标注 "CLIP (FP16)"、"UNet (FP16)"、"VAE (FP16)"
- 右侧方块 "Generated Image"
- 右下角小字标注 "iPhone 15 Pro (A16)" 和 "No Quantization"

上下两个区域中间有一条虚线分隔，虚线中央标签 "Same Model, Different Runtime"。

整体风格简洁学术，Android 用绿色系，iOS 用蓝色系，模块间用带箭头线条连接，无衬线英文字体标注。
```
