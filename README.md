# 🏥 Aarogya Intelligence

### Agentic Healthcare Maps for 1.4 Billion Lives

---

## 🚀 Overview

**Aarogya Intelligence** is an **agentic AI-powered healthcare intelligence system** designed to audit, verify, and optimize healthcare infrastructure across India.

Built on a dataset of **10,000 healthcare facilities**, the system detects false specialty claims, mines unstructured data using an **IDP (Intelligent Document Processing) engine**, and identifies **medical deserts** where millions lack access to verified care.

It goes beyond detection — it **prescribes actionable interventions** and quantifies NGO impact in real time.

---

## 🔴 Problem Statement

India’s healthcare directory data suffers from **critical structural and trust failures**:

* **66% (6,602 facilities)** claim specialties with **zero procedure evidence**
* **771 facilities** list high-risk specialties (ICU, surgery, oncology) with **no equipment**
* **484 facilities** claim advanced care with **no documented doctors**
* Only:

  * **16%** have equipment data
  * **34%** have procedure records
  * **6%** have doctor counts

### 🚨 Real-World Impact

In rural regions such as **Assam, Barpeta, and Azamgarh**, entire districts have:

* ❌ No verified ICU
* ❌ No emergency care
* ❌ Millions of people with no reliable referral system

This is not a data issue —
👉 **It is a life-or-death routing failure affecting 1.4 billion people.**

---

## 🎯 Target Users

### 🥇 Primary

* NGO healthcare planners
* Field coordinators deploying medical resources

### 🥈 Secondary

* Government health programs (NHM, Ayushman Bharat)
* Policy makers allocating budgets

### 🥉 Tertiary

* Emergency dispatch systems
* Telemedicine platforms

---

## 💡 Solution Architecture

Aarogya Intelligence operates as a **5-layer agentic pipeline**:

---

### 🧠 1. IDP Text Mining Engine

* Processes unstructured fields: `description`, `capability_text`
* Extracts:

  * Equipment keywords
  * Procedure signals
  * Doctor counts
* Recovers hidden data from **84% incomplete records**

👉 Converts unusable data into actionable insights

---

### 🔬 2. Validator Agent

* Cross-checks **claimed specialties vs required infrastructure**
* Uses a **specialty-requirements matrix**:

| Specialty  | Required Evidence          |
| ---------- | -------------------------- |
| ICU        | Ventilator + Defibrillator |
| Oncology   | Chemotherapy Pump + LINAC  |
| Cardiology | ECG + Cath Lab             |

* Flags contradictions per specialty
* Applies trust penalties

---

### 📊 3. Trust Scoring System

Transparent 100-point scoring:

| Component                     | Score |
| ----------------------------- | ----- |
| Specialties                   | +20   |
| Procedures                    | +20   |
| Equipment                     | +20   |
| Description Quality           | +15   |
| Doctor Count                  | +15   |
| Capability Text               | +10   |
| Missing Equipment (High-risk) | −15   |
| Missing Doctors               | −10   |

**Trust Tiers:**

* 🟢 HIGH ≥ 75
* 🟡 MEDIUM ≥ 45
* 🔴 LOW ≥ 20
* ⚪ UNVERIFIED < 20

---

### 🗺️ 4. Medical Desert Detection

* Uses geospatial clustering + trust data
* Identifies underserved regions
* Computes **Desert Risk Score (0–100)**

👉 Highlights zones where intervention is critical

---

### 🤖 5. Agentic Query Engine

Example query:

```
Find ICU facility in rural Assam
```

Pipeline:

1. Parse intent (specialty + location + urgency)
2. Query Databricks dataset
3. Apply IDP enrichment
4. Run Validator Agent
5. Rank by adjusted trust score

👉 Fully traceable with MLflow spans

---

### 🌍 6. What-If Simulator

Interactive NGO planning tool:

Inputs:

* Facilities upgraded
* ICU beds added
* Budget

Outputs:

* Lives saved per year
* Population reached
* Cost per life saved
* ROI by region

👉 Converts abstract decisions into measurable outcomes

---

### ⚖️ 7. Facility Comparison Tool

* Side-by-side comparison
* Multi-dimensional evaluation
* Exportable reports for funding proposals

---

## 💎 Unique Selling Proposition (USP)

### 🔥 1. Prescriptive Intelligence

Not just “this is wrong” —
👉 “Here’s exactly how to fix it”

---

### 🔥 2. IDP Innovation

* Works even when structured data is missing
* Extracts signals from free text
* Doubles usable data without new collection

---

### 🔥 3. Quantified Impact

* Budget → lives saved → population coverage
* Enables data-driven NGO decisions

---

## ⚙️ Technology Stack

### 🧱 Backend

* Databricks (data warehouse + compute)
* SQL for querying

### 🧠 Processing

* Python
* Regex-based NLP
* Pandas

### 📊 Visualization

* Plotly
* Folium

### 🖥️ Frontend

* Streamlit

### 🔍 Tracking

* MLflow experiment tracking

---

## 🔄 Data Pipeline

* 10,000 facility records
* 41 attributes per facility
* 100% GPS coverage
* Precomputed trust scores
* Real-time query enrichment

---

## 📈 Results & Impact

### 🚨 Key Findings

* 🔴 6,602 false specialty claims
* 🔴 771 facilities with no equipment
* 🔴 484 facilities with no doctors
* 🏜️ 8 medical desert zones detected

---

### 🌍 Case Study

**Assam (Rural)**

* Population: ~3.5 million
* Verified ICU facilities: **0**
* Desert Risk Score: **95+**

---

### 📊 NGO Simulation Results

* ₹20 crore investment →

  * ~160 lives saved/year
  * 3.2 million people covered

* 50 ICU beds →

  * +600 lives saved/year

---

## 🔒 Security

* Secrets managed via Streamlit secrets
* No API tokens stored in repository
* Fully auditable pipeline

---

## 🧠 Key Innovation

> “The system catches what humans miss.”

Example:
A clinic claims **neurology + cardiology**
→ No equipment
→ No doctors
→ No procedures

✔ Validator flags it
✔ IDP confirms absence
✔ System prescribes corrective actions

---


---

## 🏁 Conclusion

Aarogya Intelligence is not just a healthcare directory.

It is a **decision engine** that:

* Detects misinformation
* Restores trust
* Guides interventions
* Saves lives at scale

---

⭐ If you found this impactful, consider starring the repository!
