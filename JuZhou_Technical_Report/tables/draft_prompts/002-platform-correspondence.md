# Table 002: Cross-Platform Deployment Component Correspondence

## 基本信息

- **表格编号**：E2（已有）
- **Label**：`tab:correspondence_android_ios`
- **所在文件**：`sections/sec06.tex`，第 68-86 行
- **状态**：已完成，数据完整

## Caption

Correspondence between Android and iOS deployment components.

## 表格内容

对比 Android 和 iOS 两个平台上各管线组件的实现方式，包括推理框架、执行设备、量化精度和模型交付方式。

### 列定义

| 列名 | 说明 |
|------|------|
| Pipeline component | 管线组件名称 |
| Android implementation | Android 平台实现方式 |
| iOS implementation | iOS 平台实现方式 |

### 数据

| Pipeline component | Android implementation | iOS implementation |
|---|---|---|
| Prompt refinement (Qwen3-1.7B) | MNN, CPU, 4-bit compressed model | Not included in current validated iOS setup |
| CLIP text encoder | MNN, CPU, 8-bit quantization | Core ML, FP16 |
| UNet denoiser | QNN, NPU, 8-bit quantization | Core ML, FP16 |
| VAE decoder | QNN, NPU, 8-bit quantization | Core ML, FP16 |
| Model delivery | Remote download into app sandbox | Loaded by the Swift app through Core ML model packages |
| Orchestration layer | Native C++ Android application | Swift iOS application with Core ML inference |

## 数据来源

实际部署架构描述，已填入完整信息。
