# 🤖 Multilingual Chatbot for Low-Resource Languages

This project focuses on building a multilingual chatbot tailored for low-resource languages, specifically **Urdu**, by leveraging **cross-lingual transfer learning** from **Hindi**. We implemented and compared two approaches: a fine-tuned **mT5 transformer** and a custom **Seq2Seq model with LSTM + Bahdanau Attention**.

---

## 🚀 Project Objectives

- Design a chatbot that can generate context-aware Urdu responses.
- Leverage high-resource Hindi data to improve performance in low-resource Urdu settings.
- Compare performance between a pretrained multilingual model (mT5) and a custom LSTM-based model.
- Evaluate results using BLEU scores and human judgment.

---

## 🧠 Methodology

### Approach 1: mT5 Transformer Fine-Tuning
1. **Phase 1** – Fine-tune `google/mt5-small` on 100K Hindi dialogue pairs.
2. **Phase 2** – Further fine-tune on 1.5K Urdu dialogue samples to adapt the model.

### Approach 2: Custom Seq2Seq Model with Attention
1. Train a **stacked LSTM encoder-decoder** on Hindi dialogues.
2. Fine-tune the same model on Urdu dialogues using a separate tokenizer.
3. Integrate **Bahdanau-style attention** for better context preservation.

---

## 📊 Evaluation

| Model        | BLEU Score (Urdu) | Improvement |
|--------------|------------------|-------------|
| Zero-shot mT5 | 0.0082           | –           |
| Fine-tuned mT5 | **0.0255**       | +211%       |
| LSTM Seq2Seq | 0.0017           | —           |

- **Qualitative evaluation** confirmed that the mT5 model generates more coherent and fluent Urdu responses.
- The LSTM model struggled with vocabulary mismatch and repetition due to limited Urdu data.

---

## 📁 Dataset

**Source:** [IndicDialogue](https://huggingface.co/datasets/ai4bharat/IndicDialogue)  
- 7.7K subtitle files across 10 Indic languages  
- ~100K Hindi pairs used for high-resource training  
- ~1.5K Urdu pairs used for low-resource adaptation  

---

## 🔧 Tools & Technologies

- Python, PyTorch, Keras
- Hugging Face Transformers (`mT5`)
- SentencePiece Tokenizer
- BLEU Score Evaluation
- Jupyter/Google Colab

---

## 📌 Key Highlights

- ✅ Demonstrated effective cross-lingual transfer from Hindi to Urdu
- ✅ Achieved **3x BLEU score improvement** with fine-tuned mT5
- ✅ Compared Transformer and LSTM architectures in low-resource settings

---

## 👩‍💻 Team Contributions

- **Sri Padmavathi**: Designed and implemented the LSTM Seq2Seq model, tokenizer handling, Urdu inference, and BLEU-based evaluation.
- **Harshithavalli**: Fine-tuned the mT5 model and evaluated model outputs.
- **Monisha Raju**: Managed data preprocessing, cleaning, and test prompt setup.

---

## 📄 Final Report

[📑 NLP Final Report (PDF)](link_to_your_report_here)

---

## 💬 Sample Prompt

```text
Q: کیا آپ میری مدد کرسکتے ہیں؟  
A: جی ہاں، براہ کرم بتائیں آپ کو کس چیز کی مدد چاہیے۔
