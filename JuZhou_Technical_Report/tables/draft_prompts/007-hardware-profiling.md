# Table 007: On-Device Hardware Performance Profiling

## 基本信息

- **表格编号**：T004（新增）
- **Label**：`tab:hardware_profiling`
- **目标文件**：`sections/sec07.tex`
- **插入位置**：`\subsection{Quantitative Results}` 内，GenEval 图表前
- **状态**：待插入（基于 sec07 注释中已有的两个草稿版本整合）

## Caption

On-device hardware profiling of the denoising network at $1024\times1024$ resolution across flagship mobile platforms. Mainstream models (SD~1.5, SDv2.1) fail to execute on mobile devices due to excessive memory requirements or impractical latency.

## 表格内容

展示 JuZhou 在两个旗舰移动平台上的 UNet 硬件性能数据，并与 SD 系列基线对比（基线标记为 "--" 表示无法运行），突出 JuZhou 是唯一可在移动端实际运行的模型。

### 列定义

| 列名 | 说明 |
|------|------|
| Model | 模型名称 |
| Params | 参数量 |
| Platform (SoC) | 测试平台和芯片 |
| Precision | 推理精度 |
| Peak Mem (MB) | 峰值内存 |
| Step Latency (s) | 单步去噪延迟 |
| Total 4-step (s) | 4 步总推理时间 |

### 数据

| Model | Params | Platform (SoC) | Precision | Peak Mem (MB) | Step (s) | Total 4-step (s) |
|-------|--------|----------------|-----------|---------------|----------|-------------------|
| SD 1.5 | ~1.0B | iPhone 15 (A16) | FP16 | -- | -- | -- |
| SD 1.5 | ~1.0B | OnePlus 13 (SD 8 Elite) | INT8 | -- | -- | -- |
| SDv2.1 | 1.9B | iPhone 15 (A16) | FP16 | -- | -- | -- |
| SDv2.1 | 1.9B | OnePlus 13 (SD 8 Elite) | INT8 | -- | -- | -- |
| **JuZhou (Ours)** | **0.4B** | iPhone 15 (A16) | FP16 | ~373 | ~0.71 | ~2.84 |
| **JuZhou (Ours)** | **0.4B** | OnePlus 13 (SD 8 Elite) | INT8 | ~200 | ~0.40 | ~1.60 |

> 注："--" 表示因显存需求过高或延迟不可接受而无法在移动端执行。JuZhou 指标仅覆盖去噪网络（不含 CLIP 和 VAE 开销）。

## 数据来源

- JuZhou 数据：sec07.tex 注释中的两个草稿版本（lines 19-54）
- 基线模型标记为 "--"：因 VRAM 需求过大无法在移动端执行
- MACs: 579.65G, FLOPs: 1161.82G（来自注释版本 1）
