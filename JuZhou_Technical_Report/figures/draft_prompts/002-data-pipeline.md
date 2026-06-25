# M2 - Data Curation Pipeline

## 基本信息
- 图片编号: M2
- 目标文件路径: figures/architecture/datapipeline.png
- 对应章节: sec02.tex (Data Curation)
- 建议分辨率: 1264×848 (横版)

## 图片内容描述

三阶段从左到右的流程图，每阶段用不同颜色的大色块区分：

**阶段一 - Data Synthesis（绿色系）：**
- 输入：Chinese-Poetry Repository（55K Tang + 260K Song + 21K Song Lyrics）
- 筛选：330K representative poems
- 处理：OpenCC 简繁转换 → Style Augmentation（14种风格：landscape, ink wash, cyberpunk, ukiyo-e 等）
- 生成：Qwen-Image-2512 (1024×1024, 28 steps)
- 输出：1,773,880 poem-image pairs

**阶段二 - Data Filtering（蓝色系）：**
- 三层过滤：Source Level → Semantic Level → Generation Level
- Source: 简繁统一
- Semantic: 保留核心视觉元素，去除冗余修饰
- Generation: Positive/Negative prompt engineering
- 输出：高质量 poem-image 对

**阶段三 - Data Recaption（橙色系）：**
- 工具：Qwen3-235B-A22B-Instruct-2507
- 功能：Poetry → Comma-separated Chinese keywords
- 规则：提取视觉实体、去除重复、避免同义修饰
- 输出：最终训练数据

各阶段之间用粗箭头连接，标注数据量变化。

## Caption
"Overview of the three-stage data curation pipeline for classical Chinese poetry image-text pairs: (1) Data Synthesis expands ~330K poems with 14 stylistic descriptors and generates images via Qwen-Image-2512, yielding 1,773,880 pairs; (2) Data Filtering applies source-level, semantic-level, and generation-level quality controls; (3) Data Recaption converts each poem into compact keyword sequences via Qwen3-235B for Stable-Diffusion-style prompting."

## ERNIE-Image 提示词

```
一张学术论文数据流程图，白色干净背景，扁平化矢量风格，从左到右三个大色块区域。

第一个区域用浅绿色背景，顶部大标题 "Stage 1: Data Synthesis"。区域内部从上到下排列：
- 一个浅色方块标注 "Chinese-Poetry Corpus" 和小字 "55K Tang + 260K Song + 21K Lyrics"
- 向下箭头连接一个方块标注 "330K Representative Poems"
- 向下箭头连接一个方块标注 "OpenCC + Style Augmentation"，右侧列出小标签 "ink wash, cyberpunk, ukiyo-e, pixel art, ..." 
- 向下箭头连接一个方块标注 "Qwen-Image-2512 (1024×1024)"
- 底部输出标签 "1,773,880 Pairs"

第一个区域右侧用粗灰色箭头连接到第二个区域。

第二个区域用浅蓝色背景，顶部大标题 "Stage 2: Data Filtering"。区域内部三个并排的小色块：
- 左方块 "Source Level" 写着 "Simplified Chinese"
- 中间方块 "Semantic Level" 写着 "Visual Elements Only"
- 右方块 "Generation Level" 写着 "Pos/Neg Prompt"
- 下方有汇聚箭头

第二个区域右侧用粗灰色箭头连接到第三个区域。

第三个区域用浅橙色背景，顶部大标题 "Stage 3: Data Recaption"。区域内部：
- 一个方块标注 "Qwen3-235B"
- 向下箭头连接标注 "Poetry → Keywords"
- 底部标签 "Training-Ready Pairs"

整体风格简洁学术，线条清晰，每个阶段用不同底色区分，标注使用英文无衬线字体。
```
