#  English–Swahili Machine Translation for Agricultural PSAs

This project builds a **machine translation pipeline** to convert agricultural **Public Service Announcements (PSAs)** from **English** to **Swahili**.  
It uses the **Helsinki-NLP MarianMT model** and the **CRISP-DM framework** for data preparation, modeling, evaluation, and deployment.

---

## 🚜 Problem Statement
Many agricultural PSAs are only available in English.  
Rural communities in East Africa often rely on Swahili, which creates a **language barrier**.  
This project provides an **automated translation system** that increases accessibility and supports inclusive decision-making for farmers.

---

## 🏗️ Project Workflow (CRISP-DM)

1. **Business Understanding**  
   - Translate English PSAs into Swahili to improve agricultural knowledge access.  

2. **Data Understanding**  
   - Dataset: `Agriculture PSAs.csv`  
   - Columns: `Title`, `Description`, `Topic`, `Language`, `Translation_swahili`, etc.  

3. **Data Preparation**  
   - Removed duplicates and unnamed columns  
   - Standardized categories (`Topic`, `Format`, `Language`)  
   - Added `status` column to track translation coverage  

4. **Modeling**  
   - Pretrained Model: `Helsinki-NLP/opus-mt-en-sw`  
   - Fine-tuned using HuggingFace `Seq2SeqTrainer`  
   - Evaluated with BLEU score  

5. **Evaluation**  
   - **BLEU Score**: ~61.1 (very good for machine translation)  
   - Manual inspection of samples confirms quality  

6. **Deployment (Future Work)**  
   - API for real-time translation  
   - Integration into mobile/web apps  

---

## 📊 Example Results

| English (PSA) | Machine Translation | Human Reference |
|---------------|---------------------|-----------------|
| Farmers are advised to store maize in dry containers. | Wakulima wanashauriwa kuhifadhi mahindi kwenye vyombo kavu. | Wakulima wanashauriwa kuhifadhi mahindi kwenye vyombo kavu. |
| Use certified seeds to improve your harvest. | Tumia mbegu zilizoidhinishwa ili kuboresha mavuno yako. | Tumia mbegu zilizothibitishwa ili kuongeza mavuno yako. |

---

## 📈 BLEU Score Visualization

![BLEU Score](results/bleu_score.png)

> BLEU = 61.1 → This indicates strong alignment between machine translations and human references.


