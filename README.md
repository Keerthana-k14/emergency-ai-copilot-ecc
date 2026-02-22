# 🚑 AI Emergency Control Centre (ECC) Orchestrator
### *Autonomous Multi-Agent Systems for High-Stakes Dispatch*

---

## 📖 Project Overview
The **Emergency AI Copilot** is a sophisticated orchestration layer that converts unstructured, high-stress emergency calls into a fully synchronized medical response. By leveraging specialized agents, the system autonomously coordinates specialized hospital units, real-time traffic routing, and medical staff readiness before the dispatcher even finishes the call.

---

## 🎯 Rubric Alignment (How we scored)

### 1. Zynd API Usage (30 pts)
* **Search Protocol:** The Hospital Agent queries Zynd's registry to match injury severity with specialized trauma facilities.
* **Publish Protocol:** The Doctor Agent publishes intake requirements and patient vitals directly to the hospital’s internal network.
* **Depth of Integration:** We move beyond surface-level LLM calls by using Zynd as the core "Source of Truth" for resource availability.

### 2. Multi-Agent System (20 pts)
This is a **genuinely agentic system**, not a single prompt. 
* **Autonomous Delegation:** The Main Orchestrator identifies entities (Injury, Location) and delegates to specific experts.
* **Chained Reasoning:** The output of the **Hospital Agent** (address) is dynamically injected into the **Traffic Agent** to calculate the most efficient route.

### 3. Working Model & UI (20 pts)
* **End-to-End Reliability:** Handles the complete flow from raw transcript input to a structured Dispatch Report.
* **Functional UX:** Uses the **Zynd Chat Interface** to provide a "Copilot" experience, allowing for human-in-the-loop verification before final dispatch.

### 4. Closeness to Real World (15 pts)
* **Problem Solved:** Solves the "Information Gap"—the chaotic 60 seconds where a dispatcher is frantically typing while the patient waits. We automate the data coordination so the human can focus on life-saving decisions.

---

## 🛠️ Tech Stack
* **Orchestration:** n8n (Agentic Workflow Engine)
* **Protocols:** X402 Inter-Agent communication
* **Data Layer:** Zynd API (Publish/Search/Pay)
* **Interface:** Zynd Chat UI

---

## 🚀 How It Works (The Demo)
1. **Input:** Dispatcher enters raw text: *"Major crash at T Nagar junction, passenger is unconscious and bleeding."*
2. **Extraction:** AI extracts `Location: T Nagar` and `Injury: Trauma/Bleeding`.
3. **Orchestration:** - **Hospital Agent** finds the nearest Neuro-Trauma unit via Zynd.
    - **Traffic Agent** finds a route avoiding local festival blockages.
    - **Doctor Agent** briefs the on-call surgeon.
4. **Action:** A final report is generated for human approval.

---

## 📄 Final Presentation Note
> "By automating the 'Data Translation' phase of an emergency call, we reduce coordination time from minutes to milliseconds, directly impacting survival rates in critical incidents."

---
**Developed for the AI Dispatcher Hackathon 2026**
