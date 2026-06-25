# Table 005: Multi-stage Training Configuration

## 基本信息

- **表格编号**：T002（新增）
- **Label**：`tab:training_config`
- **目标文件**：`sections/sec04.tex`
- **插入位置**：开头概述段落后，`\subsection{Low-Resolution Pre-training}` 前
- **状态**：待插入

## Caption

Training configuration for each stage of the JuZhou multi-stage training framework. All stages are conducted on the Sugon K100 AI cluster.

## 表格内容

汇总 JuZhou 三阶段训练流程的核心超参数，便于读者快速掌握训练配置，提升可复现性。

### 列定义

| 列名 | 说明 |
|------|------|
| Stage | 训练阶段名称 |
| Resolution | 训练分辨率 |
| Dataset | 使用的数据集 |
| Nodes x GPUs | 计算节点数 x 每节点 GPU 数 |
| Global Batch Size | 全局批次大小 |
| Steps | 训练步数 |
| Learning Rate | 学习率 |
| Optimizer | 优化器 |

### 数据

| Stage | Resolution | Dataset | Nodes x GPUs | Global Batch Size | Steps | Learning Rate | Optimizer |
|-------|-----------|---------|-------------|-------------------|-------|---------------|-----------|
| 1: Low-Res Pre-training | 256x256 | ImageNet-1K | 56 x 4 | 114,688 | 30K | 3e-4 | AdamW |
| 2: Progressive Resolution | 512x512 -> 1024x1024 | 9M Chinese pairs | 56 x 4 | 2,688 | 150K | 1e-4 | AdamW |
| 3: Step Compression (DMD2) | 1024x1024 | [Dataset] | [Nodes x GPUs] | [Batch Size] | [Steps] | [LR] | [Optimizer] |

> 注：Stage 3（DMD2 蒸馏）的详细训练参数在正文中未完全披露，使用占位符标记。

## 数据来源

- Stage 1 数据：sec04.tex `\subsection{Low-Resolution Pre-training}` 第 18 行
- Stage 2 数据：sec04.tex `\subsection{Progressive Resolution Increasing}` 第 26 行
- Stage 3 数据：sec04.tex `\subsection{Inference Step Compression}` 中仅描述了 28->4 步压缩和 DMD2 方法，未给出具体超参数
