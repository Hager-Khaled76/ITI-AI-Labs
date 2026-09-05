
# 🛡️ SecCommander-Agent: Real-Time Security Incident Commander & Threat Triaging Agent
> **An Agentic AI System for Automated Threat Triaging, Vulnerability Risk Assessment, and Dual-Layer Guardrail Protection.**

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![Framework](https://img.shields.io/badge/Orchestration-LangGraph-orange.svg)](https://www.langchain.com/langgraph)
[![Knowledge Base](https://img.shields.io/badge/RAG-LlamaIndex-green.svg)](https://www.llamaindex.ai/)
[![Domain](https://img.shields.io/badge/Domain-Cybersecurity%20%26%20SOC-red.svg)]()

---

## 📌 Executive Summary & Problem Statement
In modern Cybersecurity Operations Centers (SOC), security analysts face extreme **alert fatigue** from processing hundreds of daily system logs and vulnerability reports. Standard LLMs are insufficient for SOC operations due to halluncinations, lack of execution safety, and deterministic tool requirements.

**SecCommander-Agent** resolves this by automating the end-to-end triaging workflow. It dynamically routes security incidents, retrieves domain-specific standards via RAG, executes diagnostic tools, and enforces programmatic dual-layer guardrails to block prompt injections and dangerous payload generation.

---

##    System Architecture

```mermaid
graph TD
    A[User Input / Security Query] --> B[Input Guardrail Node]
    
    B -->|Injection / Unsafe Request| C[System Refusal Output]
    B -->|Safety Passed| D[Triage Router Node]
    
    D --> E[LlamaIndex RAG Framework Context]
    D --> F[Supervisor / Tool Execution Node]
    
    E --> G[CVSS Calculator & Log Parser Tools]
    F --> G
    
    G --> H[Multi-Agent Reflection & Audit Node]
    H --> I[Output Safety Verification]
    I --> J[Executive Security Incident Report]



---

## Core Components
- **Input Guardrails:** Intercepts and blocks malicious payloads (SQLi, Prompt Injections) upfront before reaching backend components.
- **Triage Router (LangGraph):** Dynamically orchestrates tasks between retrieval and execution paths.
- **LlamaIndex RAG:** Fetches security frameworks and threat intelligence context (OWASP / MITRE ATT&CK).
- **Tools Executor:** Runs automated log parsing and computes CVSS scores.
- **Reflection Node:** Performs an internal audit loop to verify and refine final security incident reports.

---

## Tech Stack
- **Orchestration:** LangGraph
- **Retrieval:** LlamaIndex
- **Language:** Python 3.10+
