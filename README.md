# PII-Sentinel-Ensuring-Sensitive-Data-Never-Reaches-AI-Models

# PII Sentinel  
**A Local, Privacy-Preserving PII Detection & Sanitization Pipeline for Enterprise Data**

Modern organizations handle large volumes of **unstructured data** — PDFs, emails, chat logs, HR records, financial statements, support messages, and more.

These documents frequently contain **Personally Identifiable Information (PII)** such as:

- Names & email addresses  
- Phone numbers & physical addresses  
- Bank account & routing numbers  
- Credit card numbers (PCI-DSS regulated)  
- Social Security Numbers & government IDs  
- Salary & financial records  

Manual review or redaction is:

- **Error-prone**
- **Slow and expensive**
- **Inconsistent across compliance rules**
- **Not scalable for real-time AI workflows**

---

## 🧠 **Problem Statement**

Organizations want to adopt **LLMs** (ChatGPT, Bedrock, Claude, Qwen) for summarization, analytics, automation, etc.  
But **sending raw documents to AI models risks leaking sensitive PII**, leading to:

- Legal fines (GDPR, HIPAA, PCI, CCPA)
- Financial loss
- Reputational damage

**Enterprises need a reliable, automated, local pipeline to detect and sanitize PII _before_ any data is used by AI systems.**

---

## ✅ **Solution Overview**

**PII Sentinel** is a **local, agentic PII protection layer** that runs *before* LLM inference.

It automatically:

1. **Extracts text** from PDFs / logs / chat records
2. **Detects PII** using deterministic rules + ML-based context validation
3. **Classifies sensitivity**
4. **Masks sensitive spans** using enterprise-safe policies (asterisk masking)
5. **Outputs sanitized text that is safe for LLMs**
6. *(Optional)* Sends only the **sanitized text** to **Amazon Bedrock** for summarization / reasoning

📌 **Private data never leaves your machine.**

---

## 🎯 **Key Features**

| Feature | Description |
|--------|-------------|
| Local Processing | No data leaves your environment |
| PDF + Text Support | Works with unstructured enterprise documents |
| Deterministic + ML Hybrid | Regex → NER → Local SLM context validation |
| Asterisk Masking | Fully replace sensitive text without data leakage |
| Audit Trail | JSONL logs support traceability & compliance |
| Bedrock Safe | Sends only sanitized text to LLMs |

---

## 🖥️ **Demo UI (Streamlit)**

- Upload a PDF or paste text
- Click **Detect & Sanitize**
- View:
  - Sanitized text
  - **Redacted Spans JSON**
  - **Under Review JSON**
- Download sanitized text or sanitized PDF
- Fully local, lightweight, hackathon-ready

---

## 📦 **Tech Stack**

| Layer | Tools |
|------|------|
| PII Detection | Regex, Luhn Validation |
| Context Model | Qwen 1.7B / Phi-mini / Local SLM |
| Text Extraction | PyMuPDF (fitz) |
| UI | Streamlit |
| Optional LLM Processing | Amazon Bedrock (Mistral / Claude / Llama) |
| Audit Logging | JSONL |

---

## 🚀 **Run Locally**

```bash
git clone <repo-url>
cd pii-sentinel

pip install -r requirements.txt

streamlit run app.py

---

## 🏛️ **Architecture Pipeline**
