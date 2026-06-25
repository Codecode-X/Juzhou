# Table 001: Android Deployment Results

## 基本信息

- **表格编号**：E1（已有）
- **Label**：`tab:andoid_deployment_results`
- **所在文件**：`sections/sec06.tex`，第 38-53 行
- **状态**：已完成，数据完整

## Caption

Android deployment results.

## 表格内容

对比三款 Android 旗舰设备上的端到端生成时间与内存占用，分别测试有无 Prompt Refinement（Qwen3-1.7B）的场景。

### 列定义

| 列名 | 说明 |
|------|------|
| Device | 设备型号 |
| SoC | 芯片型号 |
| OS | 操作系统版本 |
| Generation Time (w/o refinement) | 不含 Prompt Refinement 的生成时间 |
| Generation Time (w refinement) | 含 Prompt Refinement 的生成时间 |
| Memory (w/o refinement) | 不含 Prompt Refinement 的内存占用 |
| Memory (w refinement) | 含 Prompt Refinement 的内存占用 |

### 数据

| Device | SoC | OS | Gen Time (w/o) | Gen Time (w/) | Mem (w/o) | Mem (w/) |
|--------|-----|----|----------------|---------------|-----------|----------|
| Xiaomi 17 Pro Max | SM8850 | Android 16 | 2.9s | 4.5s | 200MB | 1.3GB |
| iQOO Neo11 | SM8750 | Android 16 | 3.5s | 5.1s | 200MB | 1.3GB |
| Redmi K60 | SM8475 | Android 15 | 9.5s | 12.7s | 180MB | 1.3GB |

## 数据来源

实际设备测试数据，已填入完整数值。
