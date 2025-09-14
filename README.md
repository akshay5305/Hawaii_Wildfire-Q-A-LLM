
---

# 🦙 Fine-Tuning Llama-2-7B-Chat on Hawaii Wildfire Data

This repository contains a **Google Colab notebook** for fine-tuning **Meta’s Llama-2-7B-Chat** model on custom text datasets related to the **2023 Hawaii Wildfires**.
The goal is to adapt the base Llama-2 model into a **domain-specific Q\&A assistant** capable of answering wildfire-related questions (e.g., agencies, timelines, media coverage, and geographic impact).

---

## 🚀 Features  

* **LoRA Fine-tuning (PEFT):** Efficient parameter-efficient fine-tuning with low-rank adapters.
* **Quantization with BitsAndBytes:** 4-bit (NF4) quantization for memory-efficient training on Colab T4 GPU.
* **Custom Dataset:** 11 wildfire-related text files tokenized using `LlamaTokenizer`.
* **Training Pipeline:** Uses Hugging Face `Trainer` with logging, checkpointing, and evaluation.
* **Backup & Deployment:** Automated checkpoint zipping and saving to Google Drive.

---

## 📂 Repository Structure

```
📁 Fine-tuning-LLMs-Hawaii
│── Hawaii_Llama2_Finetune.ipynb   # Main Colab notebook
│── README.md                      # Project documentation
```

---

## ⚡ Requirements

* Python 3.9+
* Hugging Face `transformers`, `peft`, `datasets`
* `bitsandbytes` (for 4-bit quantization)
* Google Colab (T4 GPU recommended)

Install dependencies (if running locally):

```bash
pip install transformers peft accelerate bitsandbytes datasets GPUtil
```

---

## 🏋️‍♂️ Training Workflow

1. Clone the repo and open the notebook in Colab.
2. Install required libraries inside Colab.
3. Load **Llama-2-7B-Chat** with 4-bit quantization.
4. Tokenize wildfire dataset and apply **LoRA adapters**.
5. Fine-tune the model using Hugging Face Trainer.
6. Save checkpoints, logs, and backup to Google Drive.

---

## 🎯 Example Usage

After fine-tuning, the model can answer wildfire-related queries:

**Input:**

```text
Tell me about the role of Maui Emergency Management Agency (MEMA) in the 2023 wildfires?
```

**Output (sample):**

```text
MEMA coordinated emergency response, managed evacuation efforts, and worked with local and federal agencies to ensure public safety during the 2023 Hawaii wildfires.
```
---

## 📦 Checkpoints & Logs

* I have been facing some issues with uplaoding checkpoints and logs so for time being access the ones from 
    (https://drive.google.com/file/d/1M0NhFGn16SMf_4ck2ijnra3QxoxpG_98/view?usp=sharing)
* Saved under `./finetunedModel/` with multiple training steps.
* Logs stored in `./logs/` for monitoring loss and performance.

---

## 📌 Notes

* This repo is for **educational purposes only**.
* Model weights (Meta’s Llama-2) require access approval via Hugging Face.

---