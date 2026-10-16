# 🧠 AURA — AI Unified Retrieval Assistant
### *Air-Gapped Local Multimodal RAG Engine & Offline AI Knowledge Assistant for Desktop & Web*

<div align="center">

[![Platform](https://img.shields.io/badge/Platform-Desktop_%26_Web-4f46e5?style=for-the-badge&logo=electron&logoColor=white)](#)
[![Backend](https://img.shields.io/badge/Backend-Java_17_%2B_Spring_Boot_3-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](#)
[![Frontend](https://img.shields.io/badge/Frontend-React_%2B_Vite-61DAFB?style=for-the-badge&logo=react&logoColor=black)](#)
[![Inference](https://img.shields.io/badge/Local_LLM-Ollama_(LLaMA_3)-000000?style=for-the-badge&logo=ollama&logoColor=white)](#)
[![License: Strict Proprietary](https://img.shields.io/badge/License-Strict%20Proprietary-dc2626?style=for-the-badge&logo=lock&logoColor=white)](#)

<p align="center">
  <a href="https://github.com/Tharun4743/AURA">📦 <b>Official GitHub Repository</b></a>
</p>

</div>

---

## 1. 📌 Problem Statement & Context
Enterprises, defense agencies, legal practices, and healthcare facilities handle confidential internal documents under strict regulatory mandates:
* 🔒 **Data Privacy & Leakage Hazards:** Feeding internal trade secrets, proprietary source code, or patient records to cloud LLM APIs breaches compliance (GDPR, HIPAA, air-gapped policies).
* 💸 **Unpredictable Cloud Costs:** High-volume document indexing incurs steep per-token pricing and recurring API subscription overhead.
* 📴 **Connectivity Dead Zones:** Maritime, defense, remote field, and secure cleanroom facilities operate with zero internet connectivity.

---

## 2. 🔍 Existing Solutions & Critical Gaps
| Knowledge Assistant Metric | Commercial Cloud LLM APIs | Generic Local Python Scripts | 🧠 AURA Local RAG System |
| :--- | :---: | :---: | :---: |
| **100% Air-Gapped Privacy** | ❌ Data Leaves Organization | ⚠️ Complex Setup / Fragile | ✅ Complete Air-Gapped Isolation |
| **Real-Time Token Streaming** | ✅ Paid Cloud WebSockets | ❌ Slow Batch Generation | ✅ High-Throughput Java WebSockets |
| **Verified Page Citations** | ⚠️ Frequent Hallucinations | ❌ Unreliable Scraping | ✅ Deterministic Page-Level Citations |
| **Unified Web & Desktop App** | ⚠️ Web Only | ❌ CLI Only | ✅ Dual React + Electron Distribution |

---

## 3. 💡 Proposed Solution & Architectural Innovation
**AURA (AI Unified Retrieval Assistant)** is an air-gapped, privacy-first local multimodal Retrieval-Augmented Generation (RAG) platform architected by **Tharunkumar K**:
* 🛡️ **100% On-Device Inference:** Executes quantized local LLMs (`llama3`) and dense embeddings (`nomic-embed-text`) entirely on local consumer silicon via Ollama.
* 📄 **Deterministic Document Extraction:** Ingests multi-page PDFs using Apache PDFBox with strict chunk-to-page citation tracking.
* ⚡ **High-Concurrency Spring Boot Backend:** Enterprise Java 17 service tier delivering streaming token responses over bi-directional WebSocket connections (`/ws/chat`).

---

## 4. ⚙️ Technical Approach & System Architecture

### 📐 High-Level Architectural Flowchart:
```mermaid
graph TD
    User["User Interface (React 19 / Electron 31)"] -->|"WebSocket /ws/chat & REST /api/*"| Gateway["Spring Boot 3 Core Backend (Java 17)"]
    Gateway --> Parser["Local Document Pipeline (Apache PDFBox)"]
    Parser --> Embedding["Local Embedding Engine (Ollama nomic-embed-text)"]
    Embedding --> DB[("Embedded SQLite Vector & Relational Storage")]
    Gateway --> Retriever["Semantic Vector Retrieval & Context Builder"]
    Retriever --> LLM["Local LLM Inference Engine (Ollama LLaMA 3)"]
    LLM -->|"Streaming Token Response"| User
```

| Subsystem | Technology Stack | Operational Responsibility |
| :--- | :--- | :--- |
| **Desktop Shell** | Electron 31, Node.js | Cross-platform desktop runtime, system tray, window management, and bundled JRE |
| **Web Frontend** | React 19, Vite, Tailwind CSS | High-performance reactive UI with instant hot reloading and markdown rendering |
| **Backend Core** | Java 17, Spring Boot 3.x | Enterprise REST endpoints, WebSocket streaming controllers, and HikariCP connection pooling |
| **Document Processing**| Apache PDFBox, Commons IO | High-fidelity text extraction, multi-page segmentation, and token boundary chunking |
| **Local AI Inference** | Ollama (`llama3`, `nomic-embed-text`)| On-device dense vector embeddings and streaming local LLM generation |
| **Data Storage** | SQLite JDBC, Hibernate ORM | Zero-configuration local database for chat history and vector indexing |

---

## 5. 📈 Quantifiable Impact & Measurable Benefits
* 🛡️ **100% Zero-Cloud Data Sovereignty:** Zero bytes transmitted externally; completely air-gapped and immune to third-party data interception.
* 💰 **Zero Recurring Token Costs:** Eliminates monthly SaaS fees and per-token cloud API bills.
* ⚡ **Sub-100ms Vector Similarity Matching:** Embedded SQLite vector lookups retrieve relevant context segments instantaneously.
* 🎯 **Elimination of Hallucinations:** Every generated statement links back to exact page numbers in the uploaded source documents.

---

## 6. 🚀 Feasibility, Operational Viability & Scalability
* 🔬 **Technical Feasibility:** Runs smoothly on consumer hardware with 16GB RAM using quantized 4-bit and 8-bit local models.
* 💰 **Economic Viability:** Single-click launcher (`run-web.bat`) eliminates complex orchestration software requirements.
* 📈 **Enterprise Scalability:** Modular Spring Boot microservice architecture readily accommodates additional local embedding and vision models.

---

## 7. 👨‍💻 Engineering Author

<table border="0" itemscope itemtype="https://schema.org/Person">
  <tr>
    <td width="130" align="center" valign="middle">
      <img src="https://github.com/Tharun4743.png" width="105" style="border-radius: 6px;" alt="Tharunkumar K — Full Stack Developer & AI Systems Engineer at V.S.B. Engineering College" title="Tharunkumar K — V.S.B. Engineering College (VSBEC)" itemprop="image" />
    </td>
    <td>
      <h3 itemprop="name">Tharunkumar K</h3>
      <p>
        <b itemprop="jobTitle">Full Stack Developer & AI Systems Engineer</b> | <b>V.S.B. Engineering College (VSBEC)</b><br/>
        🎓 <b>B.Tech in Information Technology</b> — <b>V.S.B. Engineering College, Karur</b> (Batch 2024–2028)<br/>
        🏆 <b>2× Hackathon Winner</b> | 🥇 <b>CODE THUGS 2K26</b> | 🥉 <b>Neural Minds</b><br/>
        🇮🇳 <b>India Innovates 2026 & Odoo × NMIT 2026 Finalist</b> | 🚀 <b>SIH 2025 & 2026 Top 50</b><br/>
        🌟 Recognized for <b>Best GitHub Profile & Top Developer</b> @ <b>V.S.B. ENGINEERING COLLEGE</b>
      </p>
      <p>
        🚀 <b>Top Flagship Engineering Projects:</b><br/>
        • 🏛️ <b>TaskManager (VSBEC IT Vault)</b> — Institutional Task Governance & LeetCode/GitHub Sync &nbsp;<a href="https://github.com/Tharun4743/Taskmanager"><img src="https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white" alt="Code" /></a>&nbsp;<a href="https://it-taskmanager.vercel.app/"><img src="https://img.shields.io/badge/Live_Demo-10B981?style=flat-square&logo=vercel&logoColor=white" alt="Live Demo" /></a><br/>
        • 🧠 <b>AURA</b> — Air-Gapped Local Multimodal RAG Engine & Offline AI Assistant &nbsp;<a href="https://github.com/Tharun4743/AURA"><img src="https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white" alt="Code" /></a><br/>
        • 🪖 <b>Smart Helmet IoT</b> — SIH Top 50 Dual-Unit Motorcycle Accident Prevention System &nbsp;<a href="https://github.com/Tharun4743/AGILE-INNOVATORS-smart-helmet-"><img src="https://img.shields.io/badge/Code-181717?style=flat-square&logo=github&logoColor=white" alt="Code" /></a>
      </p>
      <p>
        <a href="https://tharunkumark4743.netlify.app/"><img src="https://img.shields.io/badge/Portfolio-0284c7?style=flat-square&logo=googlechrome&logoColor=white" alt="Portfolio" /></a>&nbsp;
        <a href="https://github.com/Tharun4743"><img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white" alt="GitHub" /></a>&nbsp;
        <a href="https://www.linkedin.com/in/tharunkumark4743"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>&nbsp;
        <a href="https://leetcode.com/u/Tharunkumar__K/"><img src="https://img.shields.io/badge/LeetCode-FFA116?style=flat-square&logo=leetcode&logoColor=white" alt="LeetCode" /></a>&nbsp;
        <a href="mailto:tharunkumark42007@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email" /></a>
      </p>
    </td>
  </tr>
</table>
