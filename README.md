<div align="center">

# Abhijat Mishra

**Machine Learning Engineer**

ML Systems · Applied ML · LLMs · Reinforcement Learning · Computer Vision

[![LinkedIn](https://img.shields.io/badge/LinkedIn-abhijat18-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/abhijat18)
[![Google Scholar](https://img.shields.io/badge/Google_Scholar-Publications-4285F4?style=flat-square&logo=googlescholar&logoColor=white)](https://scholar.google.com/citations?user=SG2_pwUAAAAJ)
[![Email](https://img.shields.io/badge/Email-abhijat1025@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:abhijat1025@gmail.com)
[![IEEE TETCI](https://img.shields.io/badge/First_Author-IEEE_TETCI_2026-00629B?style=flat-square&logo=ieee&logoColor=white)](https://doi.org/10.1109/TETCI.2026.3697428)

</div>

---

I work across the full model lifecycle — training and fine-tuning transformers, vision-language models and RL agents, compressing them until they fit real hardware budgets, and serving them as instrumented production services.

Most of my work sits at the seam between research and systems: a model is only interesting to me once it survives quantization, latency targets, and someone else's traffic. That bias shows up in what I build — 4-bit VLMs that run in ~2 GB of VRAM, federated RL schedulers benchmarked against classical baselines, and retrieval pipelines with citation grounding rather than confident guesses.

**Currently** building a multi-tenant LLM platform for a regulated domain — grounded retrieval, guardrails, and a provider-agnostic inference gateway running on GCP.

**B.Tech, Computer Science & Engineering (AI & Machine Learning)** — Galgotias University, 2022–2026 · CGPA 8.15/10

---

## What I Bring to the Table

| | |
|---|---|
| **End-to-end model ownership** | Data pipeline → training → fine-tuning → evaluation → quantization → deployment. I do not hand off at the checkpoint. |
| **Inference economics** | LoRA adapters, INT8/4-bit NF4 quantization, ONNX export and lightweight embedded pipelines — cutting VRAM and latency without surrendering accuracy. |
| **Trustworthy LLM systems** | Hybrid retrieval with reranking, citation grounding, guardrails, and calibration measurement — built to reduce hallucination as a *measured* number, not a hope. |
| **Production engineering** | FastAPI services, Docker/Kubernetes, Terraform, GitHub Actions and GCP Cloud Run, with Prometheus and Sentry wired in from day one. |
| **Research rigour** | First-author IEEE Transactions publication. I benchmark against real baselines and report the numbers that do not flatter me. |

---

## Technical Toolbox

| Domain | Stack |
|---|---|
| **Deep Learning** | `Transformers` `CNNs` `RNNs` `Vision-Language Models` `LLMs` `NLP` `NER` `OCR` |
| **LLM Systems** | `RAG (Hybrid Retrieval + Reranking)` `Guardrails` `LLM Gateway (routing + failover)` `Claude` `OpenAI` `Gemini / Vertex AI` |
| **Reinforcement & Distributed** | `PPO` `Stable-Baselines3` `Gymnasium` `Federated Learning` `FedAvg` |
| **Optimization & Serving** | `LoRA` `INT8 / 4-bit (bitsandbytes)` `ONNX` `GPU / CUDA` `Inference Optimization` |
| **Frameworks** | `PyTorch` `TensorFlow` `Hugging Face` `sentence-transformers` `scikit-learn` `OpenCV` `NumPy` `Pandas` `FastAPI` `Pydantic` |
| **MLOps & Cloud** | `Docker` `Kubernetes` `Terraform` `GitHub Actions` `Google Cloud` `Cloud Run` `Prometheus` `Sentry` |
| **Data & Storage** | `PostgreSQL` `pgvector` `Redis` `Neo4j` `Kafka` `ChromaDB` `FAISS` `SQLAlchemy` `Alembic` `BigQuery` |
| **Languages** | `Python` `Java` `SQL` |

---

## Selected Engineering Work

<details>
<summary><b>Production LLM Platform for a Regulated Domain</b> — grounded retrieval, guardrails and evaluation at multi-tenant scale <i>(active)</i></summary>

<br>

A SaaS platform where language models operate over authoritative source text and every answer has to be traceable back to it. Correctness is not a nice-to-have here — an unsupported claim is a defect.

- **Grounded retrieval** — hierarchical document indexing with hybrid dense/sparse search and reranking, so responses cite the specific governing clause instead of paraphrasing a corpus.
- **Provider-agnostic inference** — an LLM gateway that routes across multiple model providers with automatic failover and cost-aware selection, keeping the application layer independent of any single vendor's uptime or pricing.
- **Guardrails and evaluation** — structured output validation, grounding and refusal checks, and a curated ground-truth suite that turns "does it work?" into a regression-tested number checked before each release rather than a vibe.
- **Cloud-native infrastructure** — Terraform-provisioned GCP: Cloud Run services, PostgreSQL with pgvector, Redis caching, and Prometheus/Sentry observability, shipped through GitHub Actions.

`RAG` `Hybrid Retrieval` `Reranking` `LLM Gateway` `Guardrails` `pgvector` `Terraform` `GCP Cloud Run`

</details>

<details>
<summary><b>Explainable Vision-Language Systems for Industrial Inspection</b> — detection + natural-language reasoning on a 2 GB budget</summary>

<br>

Built a two-stage inspection system that both **finds** defects and **explains** them.

- Trained Faster R-CNN detectors for PCB defect localization, reaching **86.6% mAP@0.5** on the DeepPCB benchmark at **0.1–0.3 s/board** on GPU.
- Fine-tuned **Qwen2-VL-2B-Instruct** with LoRA (rank 16) and 4-bit NF4 quantization to run inference in **~2 GB VRAM**, adding a natural-language defect Q&A layer over the detector's output.
- Drove hallucinated outputs below **3%**, with a **0.947 confidence-calibration score** — treating faithfulness as a metric to optimize, not a caveat to disclose.
- Shipped as a FastAPI service in Docker with ONNX export for portable inference.

`Qwen2-VL` `Faster R-CNN` `LoRA` `bitsandbytes` `ONNX` `FastAPI` `Docker`

</details>

<details>
<summary><b>Federated Reinforcement Learning for 5G O-RAN Scheduling</b> — privacy-preserving RL that beats classical schedulers</summary>

<br>

Designed a federated RL framework for physical-resource-block (PRB) allocation across a simulated Open RAN deployment.

- **PPO + FedAvg** across **5 heterogeneous cells** with non-IID traffic, 50 PRBs per cell and a 22-dimensional state space — agents share weights, never raw traffic data.
- Engineered a multi-objective reward balancing **throughput, queue occupancy and Jain's fairness index**, so the policy could not win by starving weak users.
- Federated agents consistently outperformed independently-trained local PPO, benchmarked against **four classical schedulers**: round-robin, max-CQI, proportional-fair and random.

`PyTorch` `Stable-Baselines3` `PPO` `Gymnasium` `FedAvg` `NumPy`

</details>

<details>
<summary><b>Retrieval-Augmented Generation & Knowledge Graphs</b> — cited answers over heterogeneous document corpora</summary>

<br>

Built a modular RAG platform designed so every component is swappable.

- Multi-format ingestion — **PDF, DOCX, TXT, Markdown and live web crawl** — normalized into a single chunking and embedding pipeline.
- Pluggable vector store (**ChromaDB or FAISS**) behind one interface, with `all-MiniLM-L6-v2` sentence embeddings.
- Delivers **cited** answers with conversational memory, plus an automatically constructed knowledge graph from entity and relationship extraction — so the corpus becomes navigable, not just searchable.

`ChromaDB` `FAISS` `SentenceTransformers` `Hugging Face` `Streamlit`

</details>

<details>
<summary><b>Applied ML in Production</b> — document automation and edge inference under real constraints</summary>

<br>

Work delivered inside operating organizations, where uptime mattered more than novelty.

- Established core technology infrastructure from the ground up for a professional-services firm, **cutting manual document processing time by 60%** and lifting operational efficiency **40%** through automated processing pipelines.
- Architected backend systems handling **500+ documents and client-data workflows daily**, with the ingestion, storage and audit paths designed for growth.
- Integrated AI-driven predictive analytics into **defense surveillance systems**, improving detection accuracy by **25%**.
- Optimized model inference latency by **35%** via lightweight deployment pipelines targeting **embedded hardware** — quantization and graph-level trimming rather than bigger machines.

`Python` `FastAPI` `PostgreSQL` `Docker` `ONNX` `Edge Inference`

</details>

---

## Publications

<details open>
<summary><b>Peer-reviewed research</b> — 3 publications, 2 as first author</summary>

<br>

**Mishra, A.** *(first author)*, et al. — **"CRISPR-ImmunoPred: A Multi-Stage AI Framework to Predict T-Cell Reactivity and Mitigate Immunogenicity in CRISPR-Cas9 Therapies."**
*IEEE Transactions on Emerging Topics in Computational Intelligence (TETCI)*, 2026.
Designed the multi-stage classification pipeline and feature encoding for T-cell reactivity prediction.
[![DOI](https://img.shields.io/badge/DOI-10.1109%2FTETCI.2026.3697428-00629B?style=flat-square)](https://doi.org/10.1109/TETCI.2026.3697428)

**Mishra, A.** *(first author)*, et al. — **"Accelerating Pharmaceutical R&D: The Role of Generative AI in Modern Drug Discovery."**
*Biomedical Informatics and Smart Healthcare*, Vol. 1(2), 2025.
[![DOI](https://img.shields.io/badge/DOI-10.62762%2FBISH.2025.789201-1f6feb?style=flat-square)](https://doi.org/10.62762/BISH.2025.789201)

Sharma, H., et al. *(incl.* **Mishra, A.**, *4th author)* — **"Heart Failure Prediction: Machine Learning Application in Critical Care."**
*43rd IEEE Symposium on Reliable Distributed Systems (SRDS)*, 2024.
[![DOI](https://img.shields.io/badge/DOI-10.1109%2FSRDS64841.2024.00045-00629B?style=flat-square)](https://doi.org/10.1109/SRDS64841.2024.00045)

</details>

---

## GitHub Activity

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=Abhijat-M&show_icons=true&hide_border=true&include_all_commits=true&count_private=true&theme=github_dark&hide_title=true">
  <img src="https://github-readme-stats.vercel.app/api?username=Abhijat-M&show_icons=true&hide_border=true&include_all_commits=true&count_private=true&theme=graywhite&hide_title=true" height="160" alt="GitHub statistics for Abhijat-M">
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=Abhijat-M&layout=compact&hide_border=true&langs_count=8&theme=github_dark&hide_title=true">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Abhijat-M&layout=compact&hide_border=true&langs_count=8&theme=graywhite&hide_title=true" height="160" alt="Most used languages">
</picture>

</div>

---

<div align="center">

### Open to ML Engineer and Applied Scientist roles

Interested in LLM systems, model efficiency, and reinforcement learning applied to real infrastructure.

[**Email**](mailto:abhijat1025@gmail.com) · [**LinkedIn**](https://linkedin.com/in/abhijat18) · [**Google Scholar**](https://scholar.google.com/citations?user=SG2_pwUAAAAJ)

</div>
