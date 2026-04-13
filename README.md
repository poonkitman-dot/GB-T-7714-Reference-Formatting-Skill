
# 📚 GB/T 7714 Reference Formatting Skill
一个基于 **GB/T 7714-2015《信息与文献 参考文献著录规则》** 的智能参考文献生成工具，支持自动识别文献类型、处理不确定性，并可扩展输出 APA / Chicago 格式。
---
claude编写，chatgpt修改和gemini测试，目的是输入一个网址或者一些必要信息可以生成参考文献。

## ✨ Features

* ✅ 自动识别文献类型（M / J / EB / R 等）
* ✅ 强化电子资源判定（EB/OL vs R/OL）
* ✅ 日期与字段自动标准化（YYYY-MM-DD）
* ✅ 不确定性处理机制（解释 + 置信度）
* ✅ 多标准输出（GB/T 7714 + APA + Chicago）
* ✅ 支持不完整输入（自动补全与提示）

---

## 🧠 Core Concept

本项目不仅是一个“格式化工具”，而是一个：

> **基于规则的参考文献结构化生成与不确定性处理系统**

其核心流程为：

```
Input → Type Detection → Field Extraction → Normalization → Output
```

---

## ⚙️ How It Works

### 1. 文献类型判定（关键）

优先级逻辑：

* 有 URL → 电子资源

  * 期刊 → J/OL
  * 图书 → M/OL
  * 政府/机构网页 → EB/OL（默认）
  * 研究报告 → R/OL

### 2. 字段标准化

* 日期统一为 `YYYY-MM-DD`
* 删除“来源：”等自然语言
* URL 原样保留

### 3. 输出生成

示例：

```
国家数据局. 高质量数据集建设指引[EB/OL]. (2025-08-28)[2026-04-13]. URL.
```

---

## ⚠️ Uncertainty Handling

当文献存在歧义时：

* 输出最可能正确结果
* 提供类型判断说明
* 给出备选类型
* 标注置信度（高 / 中 / 低）

示例：

```
说明：该文献为政府网页，优先判定为 EB/OL；亦可能视为 R/OL。
置信度：中
```

---

## 🔄 Multi-Format Support

支持输出：

* GB/T 7714（默认）
* APA
* Chicago

示例：

```
【GB/T 7714】
...

【APA】
...

【Chicago】
...
```

---

## 🚀 Usage

### 输入示例

```
标题：高质量数据集建设指引
作者：国家数据局
日期：2025.08.28
引用日期：2026年4月13日
URL：https://www.nda.gov.cn/sjj/swdt/xwfb/0830/20250830210000366789341_pc.html
```

### 输出

```
国家数据局. 高质量数据集建设指引[EB/OL]. (2025-08-28)[2026-04-13].https://www.nda.gov.cn/sjj/swdt/xwfb/0830/20250830210000366789341_pc.html.
```

---

## 📦 Use Cases

* 学术论文写作
* 自动参考文献生成工具
* AI Agent 工具链
* 数字人文 / 档案研究

---

## 🧩 Future Work

* 引用知识图谱（Citation Knowledge Graph）
* 不确定性量化模型
* 多语言支持（中 / 英）
* 与 Zotero / EndNote 集成


---

## 👤 Author

Developed for academic and research purposes.
