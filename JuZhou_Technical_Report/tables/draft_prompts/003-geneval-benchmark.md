# Table 003: GenEval Benchmark Quantitative Evaluation

## 基本信息

- **表格编号**：E3（已有）
- **Label**：`tab:geneval_performance`
- **所在文件**：`sections/sec07.tex`，第 357-373 行
- **状态**：已完成，数据完整

## Caption

Quantitative evaluation on the GenEval benchmark.

## 表格内容

在 GenEval 基准上对比 JuZhou（0.4B）与 SDXL（3.0B）和 SDv2.1（1.9B）的语义对齐能力，涵盖单物体、双物体、计数、颜色、位置和颜色属性绑定 6 个子任务。

### 列定义

| 列名 | 说明 |
|------|------|
| Method | 模型名称 |
| # Total Params | 总参数量 |
| Single Obj. | 单物体生成准确率 |
| Two Obj. | 双物体生成准确率 |
| Counting | 计数准确率 |
| Colors | 颜色生成准确率 |
| Position | 空间位置准确率 |
| Color Attri. | 颜色属性绑定准确率 |
| Overall (up arrow) | 总体得分 |

### 数据

| Method | # Total Params | Single Obj. | Two Obj. | Counting | Colors | Position | Color Attri. | Overall |
|--------|---------------|-------------|----------|----------|--------|----------|-------------|---------|
| SDXL | 3.0B | 0.98 | 0.74 | 0.39 | 0.85 | 0.15 | 0.23 | 0.55 |
| SDv2.1 | 1.9B | 0.98 | 0.51 | 0.44 | 0.85 | 0.07 | 0.17 | 0.50 |
| **Ours** | **0.4B** | 0.90 | 0.65 | **0.48** | 0.69 | 0.14 | **0.23** | **0.52** |

## 数据来源

GenEval 基准评估实测数据，已填入完整数值。JuZhou 使用 28 步英文基础模型以确保公平对比。
