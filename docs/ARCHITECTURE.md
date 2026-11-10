# 🧠 AURA — System Architecture & Air-Gapped Specifications

This document details the system topology, air-gapped data sovereignty boundaries, and on-device RAG ingestion pipeline for **AURA (AI Unified Retrieval Assistant)**.

---

## 1. Architectural Highlights
- **100% Air-Gapped Inference**: Quantized local LLMs (`llama3`) and dense embeddings (`nomic-embed-text`) running entirely on local consumer silicon via Ollama.
- **Enterprise Java Core**: Java 17 + Spring Boot 3 enterprise service tier managing WebSocket token streaming controllers (`/ws/chat`).
- **Deterministic Chunk Provenance**: Apache PDFBox document pipeline tracking page-level citations for every retrieved context chunk.
- **Cross-Platform Shell**: React 19 web frontend with Electron 31 cross-platform desktop wrapper.

---

## 2. Technical Report & Formal Documentation
The full 12-page IEEE-standard technical architecture report is published in:
- **LaTeX Source**: [`docs/report/project-report.tex`](file:///c:/Users/tharu/Documents/GITHUB%20REPO/GITHUB%20MANAGER/AURA/docs/report/project-report.tex)
- **Compiled PDF**: [`docs/report/project-report.pdf`](file:///c:/Users/tharu/Documents/GITHUB%20REPO/GITHUB%20MANAGER/AURA/docs/report/project-report.pdf)
