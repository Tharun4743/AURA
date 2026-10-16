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
    <td width="120" align="center" valign="top">
      <img src="https://github.com/Tharun4743.png" width="100" style="border-radius: 6px;" alt="Tharunkumar K — Full Stack Developer & AI Systems Engineer at V.S.B. Engineering College" title="Tharunkumar K — V.S.B. Engineering College (VSBEC)" itemprop="image" />
    </td>
    <td>
      <h3 itemprop="name">Tharunkumar K</h3>
      <p>
        <b itemprop="jobTitle">Full Stack Developer & AI Systems Engineer</b> | <b>V.S.B. Engineering College (VSBEC)</b><br/>
        🎓 <b>B.Tech in Information Technology</b> — <a href="https://vsbec.com" target="_blank" itemprop="alumniOf" style="text-decoration: none;"><b>V.S.B. Engineering College, Karur</b></a> (Batch 2024–2028)<br/>
        🌟 Recognized for holding the <b>Best GitHub Profile & Top Student Developer</b> at <b>V.S.B. Engineering College (VSBEC)</b><br/>
        🥇 <b>Winner — Code Thugs 2K26</b> • 🚀 <b>Smart India Hackathon (SIH)</b> Top 50 National Finalist • 🏆 <b>Odoo × NMIT</b> National Finalist • 🎓 <b>GFG Campus Mantri</b>
      </p>
      <p>
        🚀 <b>Top Flagship Engineering Projects:</b><br/>
        • 🏛️ <a href="https://github.com/Tharun4743/Taskmanager" style="text-decoration: none;"><b>TaskManager (VSBEC IT Vault)</b></a> — Institutional Task Governance & LeetCode/GitHub Daemon Sync (<a href="https://it-taskmanager.vercel.app/" style="text-decoration: none;">Live Portal</a>)<br/>
        • 🧠 <a href="https://github.com/Tharun4743/AURA" style="text-decoration: none;"><b>AURA</b></a> — Air-Gapped Local Multimodal RAG Engine & Offline AI Knowledge Assistant<br/>
        • 🪖 <a href="https://github.com/Tharun4743/AGILE-INNOVATORS-smart-helmet-" style="text-decoration: none;"><b>Smart Helmet IoT</b></a> — SIH Top 50 Dual-Unit Embedded Motorcycle Accident Prevention System
      </p>
      <p>
        <a href="https://tharunkumark4743.netlify.app/" target="_blank" rel="noopener me" style="text-decoration: none;">🌐 Tharunkumar K Portfolio</a> •
        <a href="https://github.com/Tharun4743" target="_blank" rel="noopener me" style="text-decoration: none;">🐙 GitHub (@Tharun4743)</a> •
        <a href="https://www.linkedin.com/in/tharunkumark4743" target="_blank" rel="noopener me" style="text-decoration: none;">💼 LinkedIn</a> •
        <a href="https://leetcode.com/u/Tharunkumar__K/" target="_blank" rel="noopener me" style="text-decoration: none;">🧩 LeetCode</a> •
        <a href="mailto:tharunkumark42007@gmail.com" itemprop="email" style="text-decoration: none;">📧 Email</a>
      </p>
    </td>
  </tr>
</table>
