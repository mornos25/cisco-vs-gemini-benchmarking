# Evaluating Cisco Foundation-Sec-8B vs. Gemini 2.0 in Cybersecurity Analysis

An empirical benchmarking study evaluating the efficacy of Cisco's domain-specific security model (`Foundation-Sec-8B-Reasoning`) against a general-purpose frontier model (`Gemini 2.0`) in automated CVE-to-CWE mapping and mitigation generation.

## 📌 Project Overview
This project evaluates how effectively specialized security LLMs perform under hardware and context constraints compared to larger commercial models. Testing was conducted across 10 distinct vulnerabilities sourced from the **CISA Known Exploited Vulnerabilities (KEV) catalog**.

### Key Highlights:
* **Hardware Optimization:** Successfully ran and tested the 8-billion parameter model on a consumer-grade cloud GPU (Google Colab T4) by implementing **4-bit quantization** (`BitsAndBytesConfig`) to circumvent systemic RAM constraints.
* **Methodology:** Designed a quantitative evaluation matrix tracking Tactic Accuracy, Technique ID Accuracy, Sub-Technique Precision, and Hallucination Rates against established Ground Truths from MITRE ATT&CK.

## 📊 Evaluation Summary
* **CWE Performance:** Gemini achieved 90% accuracy (9/10), while Cisco Foundation-Sec-8B reached 50% (5/10).
* **Knowledge Recency:** The standalone Cisco model relied heavily on pre-2021 training data, while Gemini successfully mapped 2026 threats.
* **Hallucination Metrics:** The Cisco model showed a higher frequency of domain-specific hallucinations (e.g., mismapping isolated service architecture flaws to unrelated vendor VPN vulnerabilities) when evaluated without RAG.

## 📁 Repository Structure
* `/notebooks`: Contains the Google Colab execution pipeline for local model sharding and inference.
* `/dataset`: Explored CVE/CWE data profiles extracted for performance tracking.
* `/reports`: The comprehensive academic paper detailing testing methodologies, architectural constraints, and ethical trade-offs.

## 🛠️ Tech Stack & Concepts Tested
* **Frameworks/Libraries:** Hugging Face Transformers, PyTorch, BitsAndBytes
* **Concepts:** Model Quantization (4-bit), Specialized Corpus Bias, Automated Incident Response, MITRE ATT&CK Mapping, Guardrailed LLM Benchmarking.

## 🎓 Academic Credit
This research was developed as part of the **Penetration Testing and Ethical Hacking** curriculum at **Halmstad University (Spring 2026)** under the supervision of Jonny Svensson and Olga Torstensson.
