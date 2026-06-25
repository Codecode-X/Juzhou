# M4 - GenEval Quantitative Comparison

## 基本信息
- 图片编号: M4
- 目标文件路径: figures/architecture/geneval_comparison.png
- 对应章节: sec07.tex (Experiments - Quantitative Results)
- 建议分辨率: 848×1264 (竖版)

## 图片内容描述

分组柱状图，比较 JuZhou、SDv2.1、SDXL 在 GenEval 各子项上的得分：

**横轴（6 个子项）：**
- Position
- Color
- Color Attribution
- Counting
- Object
- Overall

**纵轴：** 得分 0.0 - 0.7

**三组柱体颜色：**
- JuZhou (0.4B): 深蓝色，Overall = 0.52
- SDv2.1 (1.9B): 灰色，Overall = 0.50
- SDXL (3.0B): 浅蓝色，Overall = 0.55

**顶部图例：** 三个模型名称 + 参数量

**关键标注：**
- Overall 子项上标注具体数值
- JuZhou 和 SDv2.1 的 Overall 柱体高度接近，用箭头标注 "0.4B vs 1.9B"

## Caption
"Quantitative evaluation on the GenEval benchmark. Despite operating with only 0.4B parameters, JuZhou achieves an overall score of 0.52, surpassing the 1.9B-parameter SDv2.1 (0.50) and remaining competitive with the 3.0B-parameter SDXL (0.55)."

## ERNIE-Image 提示词

```
一张学术论文风格的分组柱状图（信息图风格），白色干净背景。

标题位于图片顶部，写着 "GenEval Benchmark Evaluation"。

图表区域：
- 横轴（X轴）有 6 个刻度标签，从左到右分别是："Position"、"Color"、"Color Attri."、"Counting"、"Object"、"Overall"
- 纵轴（Y轴）刻度从 0.0 到 0.7，每隔 0.1 一条浅灰色水平网格线

每个横轴刻度上有三根并排的柱体：
- 第一根（左侧）深蓝色柱体，标注 "JuZhou (0.4B)"
- 第二根（中间）灰色柱体，标注 "SDv2.1 (1.9B)"
- 第三根（右侧）浅蓝色柱体，标注 "SDXL (3.0B)"

柱体高度（近似值）：
Position 组：深蓝 0.56, 灰 0.50, 浅蓝 0.60
Color 组：深蓝 0.70, 灰 0.65, 浅蓝 0.72
Color Attri. 组：深蓝 0.45, 灰 0.38, 浅蓝 0.50
Counting 组：深蓝 0.45, 灰 0.48, 浅蓝 0.52
Object 组：深蓝 0.60, 灰 0.55, 浅蓝 0.65
Overall 组：深蓝 0.52, 灰 0.50, 浅蓝 0.55

在 "Overall" 组的三根柱体上方，分别标注数字 "0.52"、"0.50"、"0.55"。

右上角有图例区域，三个色块分别标注模型名称和参数量。

整体风格简洁现代，柱体带圆角顶部，使用学术信息图风格，无衬线英文字体。
```
