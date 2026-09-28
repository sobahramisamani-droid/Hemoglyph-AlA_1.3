# HEMOGLYPH CDSS

### Clinical Decision Support & Multi-System Laboratory Intelligence Suite
**Production Release v1.3.1 (Windows x64)**

[![Release: v1.3.1](https://img.shields.io/badge/Release-v1.3.1-blue.svg)](https://github.com/sobahramisamani-droid/Hemoglyph-AlA_1.3/releases)
[![License: Commercial / Node-Locked](https://img.shields.io/badge/License-Proprietary%20%2F%20RSA--4096%20Node--Locked-blue.svg)](#licensing-and-activation)
[![Platform: Windows 10 / 11 (64-bit)](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011%20(64--bit)-0078D6.svg?logo=windows)](#system-requirements)
[![Privacy: Zero-Medical Telemetry](https://img.shields.io/badge/Privacy-Zero--Medical--Data%20Telemetry-10B981.svg)](#privacy-policy--data-governance)
[![Architecture: 100% On-Device CDS](https://img.shields.io/badge/Architecture-100%25%20On--Device%20Core-emerald.svg)](#core-clinical-capabilities)
[![AI Assistant: In Active Development](https://img.shields.io/badge/AI%20Assistant-Under%20Development%20(v1.3.1)-orange.svg)](#conversational-ai-assistant-roadmap)

**Author & System Architect:** Sobhan Bahrami  
**Inquiries & Licensing:** [sobahramisamani@gmail.com](mailto:sobahramisamani@gmail.com)

---

## 1. Executive Summary & Clinical Philosophy

Routine clinical laboratory testing accounts for over 70% of downstream diagnostic decisions, yet laboratory data is routinely reported and interpreted in fragmented silos. Clinicians are presented with disconnected analyte lists—CBC, comprehensive metabolic panels, lipid profiles, liver chemistry, renal biomarkers, and arterial blood gases—where each parameter is judged solely against a static population reference range. 

**HEMOGLYPH** fundamentally shifts laboratory evaluation from passive threshold-checking to active, multi-parametric pathophysiological synthesis. Engineered as an executive Clinical Decision Support System (CDSS), HEMOGLYPH synthesizes routine laboratory biomarkers into a unified diagnostic picture. It calculates over 100 peer-reviewed, scientifically validated clinical risk equations, performs multi-organ cross-analyte correlation, screens for subtle and subclinical patterns, and delivers grounded pathophysiological insights directly at the point of care.

HEMOGLYPH is built from the ground up on a **strict privacy-preserving, air-gapped architecture**: all clinical algorithms, patient database storage, and diagnostic reasoning execute locally on your physical workstation.

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

### D. Conversational AI Assistant (Under Development in v1.3.1)
> ⚠️ **Release Notice (v1.3.1):** The local on-device Conversational AI module is currently under active development and disabled in Release v1.3.1 to guarantee zero runtime setup friction and lightning-fast performance across all standard clinical laptops.
>
> All core diagnostic reasoning engines—including 101 Bayesian Network models, 33,875 evidence rules across 636 guideline sources, and 100 chronic disease risk models—remain 100% active, fully verified, and operational offline. Full on-device conversational AI features are scheduled for an upcoming update.

---

## 3. Privacy Policy & Data Governance

HEMOGLYPH adheres to the highest medical confidentiality and data privacy principles (HIPAA, GDPR, and ISO 27001 medical software guidelines):

1. **Zero External Cloud Telemetry:**  
   The application operates completely offline. No patient identifiers, laboratory values, demographics, or diagnostic calculations are ever transmitted across external networks.
2. **Local Cryptographic Node-Locked Licensing:**  
   Licensing relies strictly on deterministic hardware identifiers (Motherboard BIOS UUID, CPU Serial, Volume Serial Number, and Windows MachineGuid) signed with asymmetric Military-Grade **RSA-4096 / SHA-512** digital signatures.
3. **Local Database Security:**  
   Patient records and test histories are stored exclusively in a local SQLite database with PBKDF2-HMAC-SHA256 authenticated user encryption.

---

## 4. Software Architecture & Security Topology

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│                      HEMOGLYPH CDSS WORKSTATION (v1.3.1)                    │
│                                                                             │
│  ┌───────────────────────────┐              ┌────────────────────────────┐  │
│  │   Presentation Layer      │              │   Clinical Core Engine     │  │
│  │     PySide6 / QML         │              │ (101 Bayesian Models,      │  │
│  │  (Zero Bytecode, Native)  │              │  33,875 Evidence Rules)    │  │
│  └──────────┬────────────────┘              └────────────┬───────────────┘  │
│             │                                            │                  │
│             ▼                                            ▼                  │
│  ┌───────────────────────────┐              ┌────────────────────────────┐  │
│  │    Local Patient DB       │              │  Conversational AI Copilot │  │
│  │   (hemoglyph.db)          │              │  (Under Active Development)│  │
│  └───────────────────────────┘              └────────────────────────────┘  │
│             ▲                                                               │
│             │ Cryptographic Verification (RSA-4096 / SHA-512 Node Lock)      │
│             ▼                                                               │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │    Hardware Security Core (license_engine.py / Native C++ Machine)    │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 5. System Requirements

* **Operating System:** Microsoft Windows 10 (64-bit) or Windows 11 (64-bit).
* **Processor (CPU):** Intel Core i3 (6th Gen or newer) / AMD Ryzen 3 or equivalent.
* **Memory (RAM):** 4 GB RAM minimum (8 GB recommended).
* **Disk Space:** ~500 MB free storage for the core executable and Brotli clinical registries.
* **Display Resolution:** $1280 \times 720$ minimum ($1920 \times 1080$ Full HD recommended).

---

## 6. Licensing & Activation Guide

1. **Launch HEMOGLYPH:** On first launch, the Security Gate displays your workstation's unique **Machine ID** (e.g. `HG-XXXX-XXXX-XXXX-XXXX`).
2. **Copy Machine ID:** Click **Copy ID** and email it to the system architect at [sobahramisamani@gmail.com](mailto:sobahramisamani@gmail.com).
3. **Receive Activation Key:** You will receive a node-locked asymmetric RSA-4096 activation token (`HGLIC4K-...`).
4. **Permanent Offline Activation:** Paste the token and click **Activate HEMOGLYPH**. The clinical engine is permanently unlocked on your hardware.

---

## 7. Conversational AI Assistant Roadmap

The local AI copilot module is being tuned for fast, zero-dependency offline execution on standard clinical hardware. In Release v1.3.1, the Chat section displays an explicit **Under Development** notice. Full local conversational explanations will be enabled in an upcoming release.

---

## 8. Clinical Disclaimer

*HEMOGLYPH CDSS is an analytical decision-support tool designed for healthcare professionals. It does not replace clinical judgment, physical examination, or comprehensive medical evaluation.*

---

## 9. Comprehensive Clinical User Manual & Step-by-Step Tutorial

This operational guide provides clinicians, clinical pathologists, and healthcare personnel with a structured, practical walk-through to maximize diagnostic yields using HEMOGLYPH CDSS v1.3.1.

### Operational Clinical Workflow

```text
┌────────────────────────────────────────────────────────┐
│  Step 1: Launch & Authenticate Session                 │
└───────────────────────────┬────────────────────────────┘
                            │
                            ▼
┌────────────────────────────────────────────────────────┐
│  Step 2: Enter Patient Profile & Guardrails            │
│  (Age, Sex, Height, Weight, Pregnancy Status)          │
└───────────────────────────┬────────────────────────────┘
                            │
                            ▼
┌────────────────────────────────────────────────────────┐
│  Step 3: Laboratory Data Input                         │
│  • Smart Search Manual Entry (19 Panels, Auto-Units)   │
│  • OCR Lab Report Scanner (Vision Table Extraction)    │
└───────────────────────────┬────────────────────────────┘
                            │
                            ▼
┌────────────────────────────────────────────────────────┐
│  Step 4: Execute Real-Time Synthesis Engine            │
│  • 100 Clinical Risk Equations (AHA, KDIGO, MELD, etc.)│
│  • 33,875 Evidence Rules across 636 Global Sources     │
└───────────────────────────┬────────────────────────────┘
                            │
                            ▼
┌────────────────────────────────────────────────────────┐
│  Step 5: Review Differentials & Actionable Next Steps  │
│  • Ranked Differential Diagnoses with Evidence Links   │
│  • Confirmatory Laboratory Tests Suggested             │
└───────────────────────────┬────────────────────────────┘
                            │
                            ▼
┌────────────────────────────────────────────────────────┐
│  Step 6: Longitudinal Trends & Clinical Report Export  │
│  • Track Biomarker Trajectories Across Visits          │
│  • Export Formal Signed PDF / Physical Printout        │
└────────────────────────────────────────────────────────┘
```

---

### Step 1: Launch & Workspace Authentication
1. **Launch the Application:**  
   Double-click the **Hemoglyph CDSS** desktop shortcut (or run `Hemoglyph.vbs` from the root of your release folder). The application opens in a hardware-accelerated, maximized Fusion layout.
2. **First-Time Node Activation:**  
   If launching on a newly licensed workstation, copy the unique **Machine ID** and email it to `sobahramisamani@gmail.com` to receive your RSA-4096 activation key. Paste the key to permanently unlock the CDSS core.
3. **Sign In or Register:**  
   On first use, toggle to **Create Account** to register your clinician profile (Full Name, Clinical Email, and Secure Password). All credentials and patient histories are salted with PBKDF2-HMAC-SHA256 and stored strictly on-device in `hemoglyph.db`.

---

### Step 2: Patient Profile & Physiological Guardrails
Before entering numerical laboratory data, establishing the clinical baseline in the **Patient Profile** panel is vital:
* **Age & Biological Sex:**  
  These parameters govern dynamic reference ranges. In pediatric patients, the system automatically engages pediatric guardrails, blocking invalid adult equations (e.g., CKD-EPI) and substituting the bedside **CKiD Schwartz** formula. Age- and sex-stratified normal ranges for alkaline phosphatase, ferritin, and reproductive hormones are automatically selected.
* **Height & Weight (BMI & BSA):**  
  Essential for calculating Body Surface Area (DuBois formula) and Body Mass Index, required for normalizing renal clearance, adjusted ideal body weight, and cardiovascular risk stratification.
* **Blood Pressure & Waist Circumference:**  
  Required to activate the **AHA PREVENT 2023** and **Framingham 30-Year** cardiovascular risk estimators.
* **Obstetric Guardrail (Pregnancy Status):**  
  Toggling pregnancy activates trimester-specific physiological adjustments. This prevents false-positive alerts caused by normal gestational changes (e.g., plasma volume expansion hemodilution, transient first-trimester TSH reduction, and placental alkaline phosphatase elevation).

---

### Step 3: Laboratory Data Input

HEMOGLYPH provides two flexible, point-of-care data entry modes:

#### Option A: Smart Manual Entry
1. Navigate to the **Manual Entry** tab.
2. Select from 19 comprehensive clinical panels (CBC, Complete Urinalysis, Comprehensive Metabolic Panel, Hepatic Function, Renal Biomarkers, Thyroid Profile, Coagulation, Blood Gas, Cardiac Enzymes, Toxicology, etc.).
3. Use the **Intelligent Search Bar** to quickly locate analytes by clinical name or common abbreviation (e.g., `FBS`, `HbA1c`, `ALT`, `eGFR`, `Troponin-I`, `Ferritin`, `D-Dimer`, `NT-proBNP`).
4. Enter the reported numerical value. The system instantly highlights normal, abnormal, and critical panic values using international clinical color codes.
5. **Automated Unit Conversion:** If your laboratory reports values in different units (e.g., glucose in `mmol/L` vs `mg/dL`, or creatinine in `μmol/L` vs `mg/dL`), HEMOGLYPH executes standard mathematical conversion automatically.

#### Option B: Vision OCR Report Scanner (Image / PDF Upload)
1. Navigate to the **Upload** tab.
2. Select and upload a digital image or scan of the patient's paper report (`.jpg`, `.png`, or `.pdf`).
3. The embedded OCR engine preprocesses the document, isolates tabular boundaries, and extracts analyte names and values.
4. **Pre-Commit Verification Table:** Extracted results are presented in an editable review table. Verify the numbers against the source document and click **Confirm & Import** to transfer values into the analytical pipeline.

---

### Step 4: Multi-System Synthesis & Clinical Risk Engine Execution
Click **Analyze & Generate Report**. Within two seconds, HEMOGLYPH’s multi-layered decision engine delivers comprehensive findings:

1. **Multi-System Organ Radar:**  
   Visualizes the integrity of six primary physiological axes:
   * **Hepatic Integrity:** Hepatocellular necrosis (ALT/AST), cholestatic patterns (ALP/GGT/Bilirubin), and protein synthetic capacity.
   * **Renal Hemodynamics:** Glomerular filtration rate (CKD-EPI 2021/2024), tubular handling, and microalbuminuria staging.
   * **Cardiometabolic Axis:** Atherogenic risk, insulin resistance, and glycemic stability.
   * **Hematopoiesis & Erythrocytes:** Morphological anemia categorization, hemolytic screening, and iron kinetics.
   * **Acid-Base & Fluid Homeostasis:** Albumin-corrected anion gap, delta-delta ratio, and respiratory compensation adequacy.
2. **Validated Risk Scores Calculated On-The-Fly:**  
   * **AHA PREVENT 2023 & ASCVD:** 10-year and 30-year risk of myocardial infarction, stroke, and heart failure with eGFR integration.
   * **FIB-4 & APRI Scores:** Evidence-based staging of hepatic fibrosis without invasive biopsy.
   * **KFRE (Kidney Failure Risk Equation):** 2-year and 5-year statistical probability of end-stage renal disease (dialysis/transplantation).
   * **HOMA2-IR & TyG Index:** Cellular insulin resistance and subclinical metabolic syndrome quantification.

---

### Step 5: Evidence-Based Differential Diagnoses & Actionable Next Steps
Below the multi-system synthesis, the report provides direct clinical guidance:

1. **Ranked Differential Diagnoses:**  
   Conditions are ranked by mathematical likelihood based on Bayesian cross-correlation against 33,875 clinical decision rules. Each entry lists supporting and opposing laboratory evidence.
2. **Actionable Next Steps:**  
   Provides concise recommendations for confirmatory testing (e.g., recommending Serum Free Light Chains and Serum Protein Electrophoresis when unexplained anemia is accompanied by an elevated total protein and ESR).
3. **Peer-Reviewed Reference Citations:**  
   Every diagnostic insight is indexed to authoritative clinical guidelines (UpToDate, CLSI, Tietz Textbook of Clinical Chemistry, KDIGO, ADA Standards of Care, ACC/AHA).

---

### Step 6: Longitudinal Tracking & Clinical Report Export
* **Historical Trajectory Analysis (History Tab):**  
  Access archived visits for the selected patient. Compare past and present values via interactive trend graphs to evaluate therapeutic response (e.g., monitoring eGFR trajectory, lipid reduction under statin therapy, or glycemic control across consecutive quarters).
* **Formal Medical Export (Print / PDF):**  
  Generate an executive, professional clinical report formatted for physical printing or inclusion in the patient’s permanent electronic medical record (EMR).

---

### Step 7: Guideline Explorer & Risk Model Catalog
* **Guidelines Browser:** Search across 636 indexed medical guidelines and diagnostic algorithms.
* **Risk Model Catalog:** Review the mathematical formulas, clinical indications, validation cohorts, and cut-off values for all 100 integrated clinical risk calculators.

---

## 10. Scientific Transparency, Honest Disclosures & Pre-Analytical Quality

To maintain absolute medical integrity and transparency:

1. **Conversational AI Assistant Status (v1.3.1):**  
   The natural-language Conversational AI Copilot is currently under development and intentionally disabled in Release v1.3.1. This ensures that the application remains extremely lightweight (~130 MB executable), starts instantly, and runs reliably on standard clinical laptops without requiring gigabytes of GPU weights or runtime dependencies.  
   **Crucially:** All 101 Bayesian diagnostic models, 100 disease risk equations, and 33,875 evidence rules are **100% active, deterministic, and fully operational offline**.
2. **Pre-Analytical Interference Warning:**  
   Diagnostic inferences assume sample integrity. Specimen hemolysis, marked lipemia, icterus, or high-dose biotin therapy may distort laboratory measurements. HEMOGLYPH features pre-analytical plausibility checks, but final interpretations must always be reconciled with patient history and physical examination.
3. **Strict Data Privacy:**  
   Zero patient data leaves your workstation. No external cloud endpoints, no third-party telemetry, and no remote data storage. Your clinical data remains completely sovereign.

---
*Copyright © 2026 Sobhan Bahrami. All rights reserved.*

