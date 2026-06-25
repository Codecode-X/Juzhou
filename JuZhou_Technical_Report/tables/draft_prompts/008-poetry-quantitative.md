# Table 008: Poetry-to-Image Quantitative Evaluation

## 基本信息

- **表格编号**：T005（新增，关键）
- **Label**：`tab:poetry_quantitative`
- **目标文件**：`sections/sec08.tex`
- **插入位置**：`\subsubsection{Quantitative Results}` 内，正文描述前
- **状态**：待插入（修复断裂引用 `\ref{tab:poetry_quantitative}`）

## Caption

Quantitative evaluation of poetry-to-image generation. CN-CLIP Score measures text-image semantic alignment with the original Chinese poetry; FID evaluates visual quality against the curated poetry dataset.

## 表格内容

对比 JuZhou（28 步基础模型和 4 步蒸馏模型）与英文基线模型（SDv2.1、SDXL）在古诗词文生图任务上的定量表现。英文基线通过 LLM 翻译古诗词后再生成。

### 列定义

| 列名 | 说明 |
|------|------|
| Model | 模型名称 |
| Steps | 推理步数 |
| CN-CLIP Score (up arrow) | 中文 CLIP 语义对齐分数（越高越好） |
| FID (down arrow) | Frechet Inception Distance（越低越好） |

### 数据

| Model | Steps | CN-CLIP Score | FID |
|-------|-------|---------------|-----|
| SDv2.1 | 50 | [Score] | [FID] |
| SDXL | 50 | [Score] | [FID] |
| **JuZhou (Ours)** | 28 | **[Score]** | **[FID]** |
| **JuZhou (Ours, distilled)** | 4 | **[Score]** | **[FID]** |

> 注：所有数值当前为占位符 `[Score]` / `[FID]`，待实验数据填入。

## 数据来源

- sec08.tex `\subsubsection{Quantitative Results}`（lines 127-136）中的 prose 描述
- 实验数据待补充：CN-CLIP Score 和 FID 均为占位符

## 关键问题

此表格的 label `tab:poetry_quantitative` 在 sec08.tex 第 132 行已被引用（`Table~\ref{tab:poetry_quantitative}`），但表格从未定义，导致编译后显示为 "Table ??"。插入此表格将修复该断裂引用。
