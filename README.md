# HEMOGLYPH

### Next-Generation Clinical Decision Support & Multi-System Laboratory Intelligence Suite

[![License: Commercial / Node-Locked](https://img.shields.io/badge/License-Proprietary%20%2F%20Node--Locked-blue.svg)](#licensing-and-activation)
[![Platform: Windows 10 / 11 (64-bit)](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011%20(64--bit)-0078D6.svg?logo=windows)](#system-requirements)
[![Privacy: Zero-Medical Telemetry](https://img.shields.io/badge/Privacy-Zero--Medical--Data%20Telemetry-10B981.svg)](#privacy-policy--data-governance)
[![Architecture: 100% On-Device CDS](https://img.shields.io/badge/Architecture-100%25%20On--Device%20Core-emerald.svg)](#core-clinical-capabilities)
[![AI Engine: Local LLM](https://img.shields.io/badge/AI%20Engine-Local%20Ollama%20(Offline)-purple.svg)](#100-on-device-conversational-ai)

**Author & System Architect:** Sobhan Bahrami  
**Inquiries & Licensing:** [sobahramisamani@gmail.com](mailto:sobahramisamani@gmail.com)

---

## 1. Executive Summary & Clinical Philosophy

Routine clinical laboratory testing accounts for over 70% of downstream diagnostic decisions, yet laboratory data is routinely reported and interpreted in fragmented silos. Clinicians are presented with disconnected analyte lists—CBC, comprehensive metabolic panels, lipid profiles, liver chemistry, renal biomarkers, and arterial blood gases—where each parameter is judged solely against a static population reference range. 

**HEMOGLYPH** fundamentally shifts laboratory evaluation from passive threshold-checking to active, multi-parametric pathophysiological synthesis. Engineered as an executive Clinical Decision Support System (CDSS), HEMOGLYPH synthesizes routine laboratory biomarkers into a unified diagnostic picture. It calculates over 100 peer-reviewed, scientifically validated clinical risk equations, performs multi-organ cross-analyte correlation, screens for subtle and subclinical patterns, and delivers grounded pathophysiological insights directly at the point of care.

HEMOGLYPH is built from the ground up on a **strict privacy-preserving, air-gapped architecture**: all clinical algorithms, patient database storage, and artificial intelligence reasoning execute locally on your physical workstation.

---

## 2. Core Clinical Capabilities

HEMOGLYPH operates as a multi-specialty clinical consilium across eight major physiological domains:

### A. Over 100 Peer-Reviewed Disease Risk & Physiological Models
* **Cardiology & Atherosclerosis:**  
  AHA PREVENT 2023 Equations (10-year and 30-year total CVD risk with eGFR and UACR integration), Framingham 30-Year Cardiovascular Risk, ACC/AHA 2013 ASCVD Pooled Cohort Equations, European SCORE2 & SCORE2-OP (Older Persons), Reynolds Risk Score (high-sensitivity CRP-integrated), and atherogenic ratios (AIP, Castelli I & II, Non-HDL-C, Chol/HDL).
* **Nephrology & Renal Hemodynamics:**  
  2021/2024 KDIGO CKD-EPI Creatinine-Cystatin C refitted equations, Bedside CKiD Schwartz Pediatric eGFR, Kidney Failure Risk Equation (KFRE 4-Variable 2-Year & 5-Year probability of ESRD), and Fractional Excretion of Sodium/Urea (FENa, FEUrea) for acute kidney injury discrimination.
* **Hepatology & Hepatic Fibrosis:**  
  FIB-4 Index, NAFLD Fibrosis Score (NFS), AST-to-Platelet Ratio Index (APRI), De Ritis Ratio (AST/ALT), Model for End-Stage Liver Disease (MELD 3.0 & MELD-Na), and ALBI (Albumin-Bilirubin) Grade for hepatocellular function.
* **Endocrinology & Metabolic Syndrome:**  
  HOMA2-IR (Homeostatic Model Assessment of Insulin Resistance via non-linear computer model approximation), Quantitative Insulin Sensitivity Check Index (QUICKI), Triglyceride-Glucose (TyG) Index with BMI and waist adaptations, and Finnish Diabetes Risk Score (FINDRISC).
* **Hematology & Hemoglobinopathy Screening:**  
  Multi-parametric differentiation of Iron Deficiency Anemia versus Beta-Thalassemia Trait using Mentzer Index, Srivastava Index, Green & King Index, Ricerca Index, and Red Cell Distribution Width Index (RDWI).
* **Critical Care, Acid-Base & Electrolyte Balance:**  
  Albumin-Corrected Anion Gap (Figge-Jabor-Kazda-Fencl formula), Serum Osmolar Gap, Delta-Delta ($\Delta\text{AG}/\Delta\text{HCO}_3^-$) Ratio for mixed acid-base disorders, and Winter’s Formula for respiratory compensation assessment.
* **Systemic Inflammation & Immuno-Oncology:**  
  Neutrophil-to-Lymphocyte Ratio (NLR), Platelet-to-Lymphocyte Ratio (PLR), and Systemic Immune-Inflammation Index (SII).

### B. Adaptive Physiological Guardrails
Reference ranges and mathematical models dynamically adapt based on physiological context:
* **Pediatric Gating:** Enforces pediatric-specific validation routines (e.g., preventing inappropriate adult CKD-EPI usage in pediatric patients, automatically substituting bedside Schwartz equations).
* **Trimester-Specific Obstetric Adaptations:** Automatically accounts for maternal hemodilution, gestational alkaline phosphatase production, and trimester-specific thyroid-stimulating hormone (TSH) dynamics during pregnancy.

### C. Pre-Analytical Quality Interceptors
Before executing clinical reasoning, HEMOGLYPH evaluates sample integrity by screening for physiological plausibility thresholds (e.g., potassium concentrations incompatible with life without immediate notification) and highlighting potential in-vitro artifacts, including hemolysis, gross lipemia, and hyperbilirubinemic optical interference.

### D. 100% On-Device Conversational AI
HEMOGLYPH incorporates an integrated diagnostic assistant powered by local large language models (via Ollama). The assistant receives the complete, non-truncated clinical matrix—calculated indices, triage levels, and patient demographics—and produces structured clinical summaries grounded in authoritative medical references (KDIGO, ADA Standards of Care, AHA/ACC guidelines, Tietz Textbook of Clinical Chemistry).

---

## 3. Privacy Policy & Data Governance

Patient confidentiality, medical ethics, and data sovereignty are fundamental design imperatives of HEMOGLYPH. The system conforms to the highest standards of clinical privacy, including the principles of HIPAA, GDPR, and medical air-gap protocols.

### Strict Zero-Medical-Data Telemetry Guarantee
HEMOGLYPH enforces an absolute architectural separation between application licensing and clinical data:

| Data Category | Transmitted to Server? | Storage Location | Description / Purpose |
| :--- | :---: | :---: | :--- |
| **Patient Identification** (Name, National ID, Phone, MRN) | **NEVER** | Local Machine Only | Stored exclusively inside your local, encrypted workstation database (`hemoglyph.db`). |
| **Laboratory Test Results** (CBC, CMP, Hormones, Analytes) | **NEVER** | Local Machine Only | Remains in local volatile memory and encrypted local storage during clinical review. |
| **Calculated Clinical Scores** (AHA PREVENT, FIB-4, eGFR, etc.) | **NEVER** | Local Machine Only | Computed entirely by local algorithms on your CPU. Never transmitted externally. |
| **Clinical Notes & Diagnostic Impressions** | **NEVER** | Local Machine Only | Private clinical work notes remain strictly on your physical hard drive. |
| **Hardware Machine ID Token** | **YES** (Authorization Only) | Sentinel License Server | Non-reversible cryptographic hash (e.g., `HG-7636-06B5-79A7-4E40`) bound to physical hardware to authenticate your software license. |
| **Heartbeat Ping & App Version** | **YES** (Authorization Only) | Sentinel License Server | Periodic ping containing the machine token, software version (e.g., `1.0.0`), and license state to verify active subscription and enforce emergency administrative kill-switches if a device is reported lost or stolen. |
| **Network IP Address** | **Standard Web Log Only** | Sentinel License Server | Captured solely by standard networking protocols for connection routing and rate-limiting brute-force attacks. |

> **Summary:** Under no circumstance does HEMOGLYPH collect, transmit, inspect, or store patient health information (PHI), diagnostic observations, or clinical numbers on any central server.

---

## 4. Optical Lab Report Extraction (Groq Vision API)

To assist clinical staff in rapidly transcribing paper laboratory documents, printed reports, and scanned PDF forms into structured data without laborious manual typing, HEMOGLYPH features an optional, high-speed Vision OCR pipeline powered by the **Groq Cloud Vision API** (`llama-3.2-11b-vision-preview`).

Because medical images require rigorous scrutiny, the vision pipeline is engineered with specific security, privacy, and architectural controls:

### A. End-to-End Encrypted Transit (TLS 1.3)
When you choose to digitize a paper lab sheet via the Vision tool, the document image is transmitted directly from your workstation to Groq’s high-performance inference engine over an encrypted HTTPS connection utilizing Transport Layer Security (TLS 1.3). No intermediary proxy, mirror, or unauthorized relay handles your data.

### B. Ephemeral Processing (Zero Data Retention)
Groq’s developer inference endpoints operate on an **ephemeral processing model**:
* The uploaded image exists in high-speed Tensor Processing memory solely for the duration of inference (typically under 1.5 seconds).
* The model transcribes the visual tabular layout into structured numerical tokens (analyte names, numerical values, measurement units, and reference ranges).
* Once the structured text output is returned to your local HEMOGLYPH review screen, the image is immediately purged from memory. **Images are not saved to disk, archived, or retained in persistent storage.**

### C. Zero Machine Learning Model Training
Under standard developer API terms of service, customer inputs and images submitted via the Groq API are **never used to train, retrain, or fine-tune artificial intelligence models**. Your clinical workflow remains proprietary to your practice.

### D. Direct Workstation-to-API Architecture
HEMOGLYPH does not route your images through any custom third-party cloud. You provide your own private Groq API key (stored securely in your local configuration). Communication occurs exclusively between your computer and the API endpoint.

### E. 100% Optional & Air-Gap Alternative
The Groq Vision integration is **completely optional**:
* If your clinical facility operates under strict air-gap constraints or forbids external internet access, you can leave the Vision API key unconfigured.
* All clinical calculations, scoring engines, database archiving, and conversational AI features remain **100% functional without an internet connection**. Lab results can be inputted manually or imported via structured local files at any time.

---

## 5. System Architecture & Requirements

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       HEMOGLYPH WORKSTATION (LOCAL)                         │
│                                                                             │
│  ┌───────────────────────┐              ┌────────────────────────────────┐  │
│  │   PySide6 / QML GUI   │ ◄──────────► │    Clinical Decision Core      │  │
│  │ (Executive Dark Mode) │              │  (100+ Scientific Equations)   │  │
│  └──────────┬────────────┘              └───────────────┬────────────────┘  │
│             │                                           │                   │
│             ▼                                           ▼                   │
│  ┌───────────────────────┐              ┌────────────────────────────────┐  │
│  │  Local Patient DB     │              │ Local AI Diagnostic Assistant  │  │
│  │  (hemoglyph.db)       │              │ (Ollama / Qwen2.5 / Air-Gapped)│  │
│  └───────────────────────┘              └────────────────────────────────┘  │
│             ▲                                                               │
│             │ Cryptographic Verification (RSA-2048 Public Key)               │
│             ▼                                                               │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │ License Engine (Anti-Tamper, Machine-Bound, Registry Integrity Checks)│  │
│  └──────────────────────────────────┬────────────────────────────────────┘  │
└─────────────────────────────────────┼───────────────────────────────────────┘
                                      │ Zero Medical Data Heartbeat Ping
                                      │ (Hardware Token HG-XXXX only)
                                      ▼
             ┌─────────────────────────────────────────────────┐
             │       HEMOGLYPH SENTINEL (ADMIN PLATFORM)       │
             │     Asymmetric RSA-2048 Digital Licensing       │
             │      PBKDF2 Password Gate & Kill-Switch         │
             └─────────────────────────────────────────────────┘
```

### Minimum Workstation Specifications
* **Operating System:** Microsoft Windows 10 (64-bit) or Windows 11 (64-bit).
* **Processor (CPU):** Intel Core i3 (6th Gen or newer) / AMD Ryzen 3 or equivalent.
* **Memory (RAM):** 4 GB RAM minimum (8 GB recommended when running local Ollama simultaneously).
* **Disk Space:** 500 MB free storage for the core application and clinical registries.
* **Display Resolution:** $1280 \times 720$ minimum ($1920 \times 1080$ Full HD recommended).

---

## 6. Licensing & Activation Guide

HEMOGLYPH is distributed under an authorized node-locked enterprise license. To activate your installation:

### Step 1: Launch the Application
Double-click `Hemoglyph.exe` (or run `python app.py` if running from source in an authorized environment).

### Step 2: Obtain Your Machine ID
On initial startup, the **License Gate** will display your workstation's unique hardware identifier:
```text
Hardware Machine ID: HG-XXXX-XXXX-XXXX-XXXX
```
Click **"📋 Copy ID"** to copy the identifier to your clipboard.

### Step 3: Request an Activation Key
Send your Machine ID, along with your name and clinical facility details, to:
* **Contact Email:** [sobahramisamani@gmail.com](mailto:sobahramisamani@gmail.com)

### Step 4: Permanent Node-Locked Activation
You will receive an authentic, digitally signed cryptographic key:
```text
HGLIC-RSA-eyJtIjoiSEct...-XXXXXX
```
Paste this token into the activation field and click **"Activate HEMOGLYPH"**. The license is validated via an asymmetric RSA-2048 public-key signature verification engine and locked to your machine's physical hardware.

---

## 7. Optional Enhancements Setup

### Local Offline AI Setup (Ollama)
For completely offline, zero-latency clinical explanations:
1. Download and install Ollama from [ollama.com](https://ollama.com).
2. Open Windows Command Prompt or Terminal and pull the recommended high-velocity clinical model:
   ```cmd
   ollama pull qwen2.5:1.5b
   ```
3. Keep Ollama active. HEMOGLYPH connects directly to the local daemon at `http://127.0.0.1:11434`.

### Groq Vision OCR Setup (Paper Lab Digitization)
To enable instantaneous digitization of photographed paper lab sheets:
1. Obtain a free API key from the Groq Developer Console: [console.groq.com](https://console.groq.com).
2. In HEMOGLYPH, navigate to **Settings** → **AI & Vision OCR**.
3. Paste your API key (`gsk_...`) and click **"Save Key"**.

---

## 8. Clinical Disclaimer & Regulatory Notice

> **IMPORTANT CLINICAL NOTICE:**  
> HEMOGLYPH is an advanced Clinical Decision Support System (CDSS) and educational analytics suite designed specifically to augment the cognitive workflow of licensed medical practitioners, pathologists, clinical biochemists, and healthcare researchers.
>
> 1. **Not an Autonomous Diagnostic Device:** Calculations, risk stratifications, cross-system inferences, and conversational AI summaries provided by HEMOGLYPH do not constitute definitive medical diagnoses, automated prescriptions, or autonomous treatment plans.
> 2. **Clinical Correlation Required:** All algorithmic outputs, derived ratios, and probability estimates must be corroborated against comprehensive patient histories, physical examinations, specialized diagnostic modalities, and validated institutional clinical protocols.
> 3. **Attending Responsibility:** Final diagnostic judgment, therapeutic management, and patient care decisions remain the exclusive professional responsibility of the attending licensed clinician.

---

## 9. Author & Inquiries

For institutional licensing, research partnerships, academic collaborations, or technical support, please contact:

* **Author & Architect:** Sobhan Bahrami
* **Email:** [sobahramisamani@gmail.com](mailto:sobahramisamani@gmail.com)
* **Project Repository:** [github.com/sobahramisamani-droid/2222222](https://github.com/sobahramisamani-droid/2222222)

---
*Copyright © 2024–2026 Sobhan Bahrami. All rights reserved.*
