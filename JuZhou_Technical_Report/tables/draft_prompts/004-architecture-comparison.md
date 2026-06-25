# Table 004: Architecture Comparison

## 基本信息

- **表格编号**：T001（新增）
- **Label**：`tab:architecture_comparison`
- **目标文件**：`sections/sec03.tex`
- **插入位置**：`\subsection{0.4B Denoising Network}` 前
- **状态**：待插入

## Caption

Architectural comparison between JuZhou and mainstream text-to-image diffusion models. JuZhou achieves an 85\% parameter reduction in the denoising network and 98\% in the VAE decoder through systematic architectural simplification.

## 表格内容

对比 JuZhou 与 Stable Diffusion 系列 4 个基线模型的架构规格，突出 JuZhou 在参数效率和移动端可部署性方面的优势。

### 列定义

| 列名 | 说明 |
|------|------|
| Model | 模型名称 |
| Total Params | 总参数量 |
| UNet Params | 去噪网络参数量 |
| VAE Dec. Params | VAE 解码器参数量 |
| Attention | 注意力机制类型 |
| Pos. Encoding | 位置编码方式 |
| Mobile Deploy. | 是否可在移动端部署 |

### 数据

| Model | Total Params | UNet Params | VAE Dec. Params | Attention | Pos. Encoding | Mobile Deploy. |
|-------|-------------|-------------|-----------------|-----------|---------------|----------------|
| SD 1.5 | ~1.0B | ~860M | ~50M | MHSA | Sinusoidal | No |
| SDv2.1 | ~1.9B | ~865M | ~50M | MHSA | Sinusoidal | No |
| SDXL | ~3.0B | ~2.6B | ~50M | MHSA | Sinusoidal | No |
| SD 3.5-L | ~8.1B | [Params] | [Params] | MHSA + MMDiT | 2D RoPE | No |
| **JuZhou (Ours)** | **~0.4B** | **~0.4B** | **~1M** | **MQA** | **2D RoPE** | **Yes** |

> 注：SD 3.5-L 的部分参数数据需确认后补充，当前使用占位符 `[Params]`。

## 数据来源

- JuZhou 数据：sec03 正文（0.4B UNet, 1M VAE, MQA, 2D RoPE, 去除高分辨率 Self-Attention）
- SD 1.5/SDv2.1/SDXL 数据：公开论文和模型卡
- SD 3.5-L 数据：部分需从参考文献确认
