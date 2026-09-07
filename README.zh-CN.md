# CryoMethViz——第 7 组课程项目

[English](README.md) · 简体中文

这是 PKU-EMBL **Data Visualization and Analysis Methods** 课程仓库的 fork，包含第 7 组“冰冻圈湖泊甲烷排放温度依赖性”项目。项目组合了 R 分析脚本、处理后研究数据、生成图表与报告，以及静态 HTML/CSS/JavaScript 查看器。

上游课程材料与许可证归属于 [PKU-EMBL/Data-Visualization-and-Analysis-Methods](https://github.com/PKU-EMBL/Data-Visualization-and-Analysis-Methods)。第 7 组成果是学生课程项目，不是同行评议论文或业务气候模型。

## 研究问题

项目分析湖泊温度与三类甲烷通量路径的关系：

- 扩散甲烷通量（`dCH4`）；
- 鼓泡甲烷通量（`eCH4`）；
- 总甲烷通量（`tCH4`）。

分析使用 Arrhenius 风格回归、混合效应模型、空间相关方法，以及湖泊面积和深度对比，探索表观温度敏感性及其异质性。

## 数据来源

项目文档标注的数据源为 **Cryosphere Lake Greenhouse Gases Database 2025**，DOI [`10.6084/m9.figshare.29146295`](https://doi.org/10.6084/m9.figshare.29146295)。数据来源、引用方式和复用条款应以数据集页面为准。

## 目录

| 路径 | 用途 |
|---|---|
| `group7-dvam-viewer/index.html` | 静态项目查看器 |
| `group7-dvam-viewer/css/` | 页面样式 |
| `group7-dvam-viewer/js/` | 页面交互 |
| `group7-dvam-viewer/assets/code/main.R` | R 分析流程 |
| `group7-dvam-viewer/assets/data/` | 处理后分析表 |
| `group7-dvam-viewer/assets/images/` | 生成图表 |
| `group7-dvam-viewer/assets/pdfs/` | 项目报告 |
| `DVAM_Contribution_Sheet.pdf` | 课程贡献记录 |

## 查看页面

建议通过 HTTP 提供静态页面，避免浏览器对 `file://` 请求的限制：

```powershell
cd group7-dvam-viewer
npx http-server -p 8000
```

随后打开 `http://localhost:8000/`。

## 重新运行 R 分析

脚本依赖较多 R 地理空间和统计包，包括 `sf`、`spatialreg`、`spdep`、`nlme`、`lme4`、`lmerTest`、`tidyverse`、`ggplot2` 等。

```powershell
cd group7-dvam-viewer
Rscript assets/code/main.R
```

当前复现并非开箱即用：脚本包含机器专用库路径，并假设本地数据与输出目录。换机运行前需要检查并替换这些路径，且仓库未锁定 R 包版本。

## 解释边界

- 结果是对所引数据集的探索性课程分析；
- 拟合得到的表观活化能不能直接证明普适生物机制；
- 空间结构、缺失值、预处理、模型选择和分组阈值都可能改变估计；
- 仓库不声称完成独立复现、同行评议或观测范围之外的预测验证。

## 许可证与署名

仓库保留上游 [MIT License](LICENSE)。数据集、图片、报告和其他第三方材料可能具有独立条款；使用时应同时引用上游课程仓库和源数据集。