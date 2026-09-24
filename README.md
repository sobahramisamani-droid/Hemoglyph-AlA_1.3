# HEMOGLYPH

### Clinical Decision Support & Multi-System Laboratory Intelligence Suite
**Author & Lead Architect:** Sobhan Bahrami  
**Contact / Inquiries:** [sobahramisamani@gmail.com](mailto:sobahramisamani@gmail.com)

---

## 1. Overview

**HEMOGLYPH** is an offline, research-grade Clinical Decision Support System (CDSS) built for medical practitioners, laboratory scientists, and clinical biochemists. Routine blood reports (CBC, comprehensive metabolic panels, lipid profiles, liver and renal function, blood gases, and electrolytes) are often analyzed in isolation. HEMOGLYPH synthesizes these fragmented data points into a unified pathophysiological picture, computing over 100 validated multi-parametric clinical risk equations and screening for complex clinical patterns across multiple organ systems.

The software is engineered with a strict **privacy-first, air-gapped architecture**: all clinical reasoning, database storage, and AI conversational summaries execute locally on your physical machine. No patient records, laboratory values, or diagnostic conclusions ever leave your workstation.

---

## 2. Key Capabilities & What Makes Hemoglyph Different

Most laboratory viewers merely compare a number against a static reference interval and color it red if it is high or low. HEMOGLYPH operates as a multi-specialty clinical consilium:

* **100 Validated Disease Risk Models:**  
  Includes validated scientific equations across cardiology (AHA PREVENT 2023, Framingham 30-Year, ASCVD Pooled Cohort, European SCORE2/SCORE2-OP, Reynolds Risk), nephrology (KDIGO 2024 eGFR, CKiD Schwartz, KFRE 4-Variable 2-Year & 5-Year kidney failure risk), hepatology (FIB-4, NAFLD Fibrosis Score, APRI, De Ritis Ratio, MELD 3.0, ALBI grade), metabolism (HOMA2-IR, QUICKI, Triglyceride-Glucose TyG Index, FINDRISC), hematology/thalassemia screening (Mentzer, Srivastava, Green & King, RDW Index), critical care electrolytes (Albumin-Corrected Anion Gap, Osmolar Gap, Delta-Delta ratio, Winter's formula), and systemic oncology/inflammation indices (NLR, PLR, SII).

* **Multi-Population Physiological Gating:**  
  Prevents erroneous adult reference ranges from being applied to children via pediatric-specific formulas (e.g., bedside Schwartz eGFR). Includes trimester-specific obstetric adaptations that account for normal gestational hemodilution, alkaline phosphatase elevations, and physiological TSH changes during pregnancy.

* **Pre-Analytical Quality Interceptors:**  
  Actively checks for physiological plausibility (e.g., serum potassium > 10 mmol/L or pH < 6.8) and warns of specimen artifacts such as hemolysis, lipemia, and icterus before clinical reasoning takes place.

* **100% On-Device AI Diagnostic Assistant:**  
  Runs a local large language model via Ollama directly on your CPU or GPU. Summaries and interactive explanations cite authoritative clinical guidelines (KDIGO, ADA, AHA/ACC, Tietz) with zero artificial context truncation and zero cloud latency.

* **Cryptographic Hardware-Locked Security:**  
  Node-locked offline licensing binds each installation to the physical motherboard, processor, and system firmware via HMAC-SHA256 digital signatures, ensuring tamper-proof offline operation.

---

## 3. How to Set Up & Activate

Hemoglyph runs as a standalone desktop application on **Windows 10 and 11 (64-bit)**.

### Step 1: Launching the Application
* If you received the compiled portable binary, double-click **`Hemoglyph.exe`**.
* If running from source in a Python 3.10–3.12 environment:
  ```cmd
  .venv\Scripts\activate
  pip install PySide6 brotli
  python app.py
  ```

### Step 2: One-Time Hardware License Activation
When you open Hemoglyph for the first time, the **Security Gate** will appear:
1. You will see your computer's unique **Hardware Machine ID** (e.g., `HG-FFB6-0AC8-568F-DA7F`).
2. Click **"📋 Copy ID"**.
3. Send this Machine ID via email to **`sobahramisamani@gmail.com`**.
4. You will receive your signed cryptographic activation key (`HGLIC-...`).
5. Paste the key into the input box and click **"Activate HEMOGLYPH"**.
6. The software unlocks permanently on your machine. You will never need to re-enter this key on that computer.

---

## 4. Optional Integrations & Setup

While Hemoglyph works out-of-the-box for manual laboratory entry and local clinical calculations, two optional integrations enhance the workflow:

### A. Automatic Vision OCR for Paper & Photo Reports
If you frequently photograph or scan paper laboratory sheets (CBC, biochemistry panels, PDFs), you can enable cloud-assisted high-precision Vision extraction:
1. Visit the free Groq developer portal: **[console.groq.com](https://console.groq.com)**
2. Create an account and generate a free API key (starts with `gsk_...`).
3. In Hemoglyph, open **Settings** → **AI & Vision OCR** tab.
4. Paste your key into the **Vision API Key** field and click **"Save Key"**.
5. The software will use `llama-3.2-11b-vision-preview` to digitize table layouts, analytes, units, and flags directly from image files into the review interface.

### B. Local Offline AI Assistant (Ollama)
For completely offline medical explanations:
1. Download and install **Ollama** from: **[ollama.com](https://ollama.com)**
2. Open your terminal or Command Prompt and pull the recommended fast clinical model:
   ```cmd
   ollama pull qwen2.5:1.5b
   ```
3. Keep Ollama running in the background. Hemoglyph connects directly to `http://127.0.0.1:11434` with zero configuration needed.

---

## 5. Contact, Support & Licensing Inquiries

For license requests, institutional partnerships, feedback, bug reports, or research inquiries, contact the author directly:

* **Author:** Sobhan Bahrami
* **Email:** [sobahramisamani@gmail.com](mailto:sobahramisamani@gmail.com)

When emailing for an activation key, please include:
1. Your **Hardware Machine ID** (copied from the software).
2. Your name or clinical institution name.

---

## 6. Clinical & Regulatory Notice

> **DISCLAIMER:**  
> HEMOGLYPH is an advanced clinical decision-support and educational tool designed to assist licensed physicians, pathologists, and laboratory specialists. The calculated scores, multi-system patterns, and AI explanations must be correlated with the complete patient history, physical examination, and institutional laboratory protocols. Diagnostic and therapeutic decisions remain the sole responsibility of the attending clinician.

---

*Copyright © 2024–2026 Sobhan Bahrami. All rights reserved.*
