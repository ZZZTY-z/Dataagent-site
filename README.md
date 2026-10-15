# DataAgent · 在线演示与项目介绍

个人项目 **DataAgent（自主数据分析智能体）** 

> 🔗 在线访问：<https://zzzty-z.github.io/Dataagent-site/>
> 💻 项目源码：<https://github.com/ZZZTY-z/DataAgent>

## 项目介绍

跑在本机（无需服务器）的 LLM 数据分析 Agent：上传 CSV/Excel 后，自动完成
**数据画像 → 质量诊断 → 分析方向 → 多模型对比 → 中文结论与报告**，
并支持用中文对话指定分析方向（线性 / 非线性 / 随机森林 / 梯度提升 / 神经网络）。

页面里可以看到 Agent 对一份客户流失数据集（2,012 行 × 16 列，含缺失与重复行）
**全自动生成**的完整报告：自动识别目标列为「是否流失」，对比 4 个模型后判定随机森林最优
（交叉验证 ROC-AUC **0.8864**，测试集 0.8686，基线 0.5）。

## 目录结构

```
index.html          作品集主页（单文件，无构建依赖）
demo-report.html    Agent 全自动生成的完整分析报告（图表已内嵌，可离线打开）
charts/             15 个交互式图表（Plotly 交互版：可缩放、悬停查看数值）
images/             从报告中抽出的静态图（离线可看）
qr.png / qr.svg     项目二维码（容错级别 H，SVG 为矢量版，打印不糊）
```

## 技术栈

`Python 3.10+` · `Flask` · `pandas` · `scikit-learn` · `statsmodels` · `scipy` ·
`Plotly` / `Matplotlib` · `DeepSeek Function Calling` · `SSE 流式推送` · `原生 JavaScript`

## 关于演示数据

页面中的数据集由 `make_samples.py` **程序合成**，仅用于演示，不含任何真实业务数据。

## 说明

本仓库只包含静态展示页。若要查看实现代码、自行运行或了解 token 成本优化细节，
请访问源码仓库：<https://github.com/ZZZTY-z/DataAgent>

---

**Zhang Mengliang** · HKU · CS · 2026 · <u3684244@connect.hku.hk>
