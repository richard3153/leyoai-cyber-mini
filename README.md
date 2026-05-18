# 🛡️ LeyoAI Cyber Security Assistant (Mini)

> LeyoAI 网络安全助手（迷你版）

---

## 🇬🇧 English

### Overview

**LeyoAI Cyber Security Assistant (Mini)** is part of the [LeyoAI](https://leyoai.vercel.app) platform by [杭州市上城区乐友信息服务工作室](https://leyoai.vercel.app).

Cyber Security Assistant — Detects vulnerabilities, classifies attacks, and extracts security entities from text.

### Model Details

| Item | Value |
|------|-------|
| Base Model | `Qwen/Qwen2.5-0.5B-Instruct` |
| PEFT Type | LoRA |
| LoRA Rank (r) | 8 |
| LoRA Alpha | 16 |
| LoRA Dropout | 0.1 |
| Target Modules | ['k_proj', 'o_proj', 'q_proj', 'v_proj'] |
| Task Type | CAUSAL_LM |
| Training Device | Apple Mac Studio (MPS) |
| Precision | FP32 |

### Quick Start

```python
from peft import PeftModel
from transformers import AutoModelForCausalLM, AutoTokenizer

base_model = AutoModelForCausalLM.from_pretrained("Qwen/Qwen2.5-0.5B-Instruct")
tokenizer = AutoTokenizer.from_pretrained("Qwen/Qwen2.5-0.5B-Instruct")

model = PeftModel.from_pretrained(base_model, "richard3153/leyoai-cyber-mini")
model.eval()

messages = [{"role": "user", "content": "Your question here"}]
inputs = tokenizer.apply_chat_template(messages, return_tensors="pt")
outputs = model.generate(inputs, max_new_tokens=256)
print(tokenizer.decode(outputs[0]))
```

### HuggingFace

This model is also available on HuggingFace: [FFZwai/leyoai-cyber-mini](https://huggingface.co/FFZwai/leyoai-cyber-mini)

---

## 🇨🇳 中文

### 概述

**LeyoAI 网络安全助手（迷你版）** 是[杭州市上城区乐友信息服务工作室](https://leyoai.vercel.app)旗下 [LeyoAI](https://leyoai.vercel.app) 平台的一部分。

网络安全助手 — 检测漏洞、分类攻击类型、从文本中提取安全实体。

### 模型详情

| 项目 | 值 |
|------|-----|
| 基座模型 | `Qwen/Qwen2.5-0.5B-Instruct` |
| 微调方式 | LoRA |
| LoRA 秩 (r) | 8 |
| LoRA Alpha | 16 |
| LoRA Dropout | 0.1 |
| 目标模块 | ['k_proj', 'o_proj', 'q_proj', 'v_proj'] |
| 任务类型 | CAUSAL_LM |
| 训练设备 | Apple Mac Studio (MPS) |
| 精度 | FP32 |

### 快速使用

```python
from peft import PeftModel
from transformers import AutoModelForCausalLM, AutoTokenizer

base_model = AutoModelForCausalLM.from_pretrained("Qwen/Qwen2.5-0.5B-Instruct")
tokenizer = AutoTokenizer.from_pretrained("Qwen/Qwen2.5-0.5B-Instruct")

model = PeftModel.from_pretrained(base_model, "richard3153/leyoai-cyber-mini")
model.eval()

messages = [{"role": "user", "content": "你的问题"}]
inputs = tokenizer.apply_chat_template(messages, return_tensors="pt")
outputs = model.generate(inputs, max_new_tokens=256)
print(tokenizer.decode(outputs[0]))
```

### HuggingFace

本模型也可在 HuggingFace 获取：[FFZwai/leyoai-cyber-mini](https://huggingface.co/FFZwai/leyoai-cyber-mini)

---

## License

MIT License — [杭州市上城区乐友信息服务工作室](https://leyoai.vercel.app)

## Links

- 🌐 [LeyoAI Official Website](https://leyoai.vercel.app)
- 🤗 [HuggingFace Organization](https://huggingface.co/FFZwai)
- 💻 [GitHub Organization](https://github.com/richard3153)
