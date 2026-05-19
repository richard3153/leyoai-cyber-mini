# 🛡️ LeyoAI Cyber Security Assistant (Mini)

> LeyoAI 网络安全助手（迷你版）

---

## 🇬🇧 English

### Overview

**LeyoAI Cyber Security Assistant (Mini)** — Part of the [LeyoAI](https://leyoai.vercel.app) platform by 杭州市上城区乐友信息服务工作室.

Cyber Security Assistant — Detects vulnerabilities, classifies attacks, extracts security entities.

### Model Details

| Item | Value |
|------|-------|
| Base Model | `Qwen/Qwen2.5-0.5B-Instruct` |
| PEFT Type | LoRA |
| LoRA Rank | 8 |
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

base = AutoModelForCausalLM.from_pretrained("Qwen/Qwen2.5-0.5B-Instruct")
tok = AutoTokenizer.from_pretrained("Qwen/Qwen2.5-0.5B-Instruct")
model = PeftModel.from_pretrained(base, "richard3153/leyoai-cyber-mini")
model.eval()

msgs = [{"role": "user", "content": "Your question"}]
inputs = tok.apply_chat_template(msgs, return_tensors="pt")
out = model.generate(inputs, max_new_tokens=256)
print(tok.decode(out[0]))
```

### HuggingFace

Also available: [FFZwai/leyoai-cyber-mini](https://huggingface.co/FFZwai/leyoai-cyber-mini)

---

## 🇨🇳 中文

### 概述

**LeyoAI 网络安全助手（迷你版）** — [杭州市上城区乐友信息服务工作室](https://leyoai.vercel.app)旗下 [LeyoAI](https://leyoai.vercel.app) 平台。

网络安全助手 — 检测漏洞、分类攻击类型、提取安全实体。

### 模型详情

| 项目 | 值 |
|------|-----|
| 基座模型 | `Qwen/Qwen2.5-0.5B-Instruct` |
| 微调方式 | LoRA |
| LoRA 秩 | 8 |
| LoRA Alpha | 16 |
| 目标模块 | ['k_proj', 'o_proj', 'q_proj', 'v_proj'] |
| 训练设备 | Apple Mac Studio (MPS) |
| 精度 | FP32 |

### 快速使用

```python
from peft import PeftModel
from transformers import AutoModelForCausalLM, AutoTokenizer

base = AutoModelForCausalLM.from_pretrained("Qwen/Qwen2.5-0.5B-Instruct")
tok = AutoTokenizer.from_pretrained("Qwen/Qwen2.5-0.5B-Instruct")
model = PeftModel.from_pretrained(base, "richard3153/leyoai-cyber-mini")
model.eval()

msgs = [{"role": "user", "content": "你的问题"}]
inputs = tok.apply_chat_template(msgs, return_tensors="pt")
out = model.generate(inputs, max_new_tokens=256)
print(tok.decode(out[0]))
```

### HuggingFace

也可在 HuggingFace 获取：[FFZwai/leyoai-cyber-mini](https://huggingface.co/FFZwai/leyoai-cyber-mini)

---

## License

MIT License — 杭州市上城区乐友信息服务工作室

## Links

- 🌐 [LeyoAI](https://leyoai.vercel.app) | 🤗 [HuggingFace](https://huggingface.co/FFZwai) | 💻 [GitHub](https://github.com/richard3153)
