# M7 - Parameter-Efficiency Scatter Plot

## 基本信息
- 图片编号: M7
- 目标文件路径: figures/architecture/parameter_efficiency.png
- 对应章节: sec07.tex (Experiments)
- 建议分辨率: 1024×1024 (正方)

## 图片内容描述

气泡散点图，横轴参数量、纵轴 GenEval Overall 得分：

**横轴（对数刻度）：** Parameters (B) 0.1B - 10B
**纵轴：** GenEval Overall Score 0.3 - 0.7

**数据点：**
| 模型 | 参数量 | GenEval | 气泡大小 | 颜色 |
|------|--------|---------|---------|------|
| SD 1.5 | 1.5B | 0.43 | 中 | 灰色 |
| SDv2.1 | 1.9B | 0.50 | 中 | 浅蓝 |
| **JuZhou** | **0.4B** | **0.52** | **小** | **深蓝（高亮）** |
| SDXL | 3.0B | 0.55 | 大 | 浅蓝 |
| SD 3.5-L | ~8B | ~0.60 | 最大 | 浅蓝 |

**关键标注：**
- JuZhou 数据点用红色圆圈高亮，标注 "JuZhou (0.4B) → 0.52"
- 虚线对角趋势线
- JuZhou 点位于趋势线上方，表示效率优于平均

## Caption
"Parameter efficiency comparison on the GenEval benchmark. JuZhou (0.4B, highlighted) achieves competitive performance against models 5-20× larger, demonstrating the effectiveness of the proposed architectural and training co-design."

## ERNIE-Image 提示词

```
一张学术论文风格的气泡散点图，白色干净背景。

标题位于图片顶部中央，写着 "Parameter Efficiency on GenEval"。

图表区域：
- 横轴（X轴）标注 "Parameters (Billions)"，对数刻度，刻度标签从左到右 "0.1"、"1"、"10"
- 纵轴（Y轴）标注 "GenEval Overall Score"，刻度从 0.3 到 0.7，每隔 0.1 一条浅灰色水平网格线

数据点（气泡）位置和大小：
- 左下区域一个中等灰色圆球，标注 "SD 1.5 (1.5B)" 坐标大约 (1.5, 0.43)
- 中间偏左一个中等浅蓝色圆球，标注 "SD v2.1 (1.9B)" 坐标大约 (1.9, 0.50)
- 左侧区域一个小的深蓝色圆球，用红色圆环高亮，标注 "JuZhou (0.4B)" 坐标大约 (0.4, 0.52)
- 中间偏右一个大浅蓝色圆球，标注 "SDXL (3.0B)" 坐标大约 (3.0, 0.55)
- 右侧区域一个很大浅蓝色圆球，标注 "SD 3.5-L (8B)" 坐标大约 (8, 0.60)

图表中有一条从左下到右上的虚线趋势线穿过数据点。

JuZhou 的数据点特别用红色虚线圆环高亮，因为它位于趋势线上方（同等参数量下得分更高）。

气泡大小与参数量成正比。整体风格学术简洁，无衬线英文字体标注。
```
