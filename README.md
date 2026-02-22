# 🚑 Emergency Control Center (ECC)

### Multi-Agent AI Orchestration on ZyndAI Network

---

## 🧠 Overview

Emergency Control Center (ECC) is a multi-agent AI orchestration system built on the ZyndAI Network using X402-powered agents.

It coordinates specialized AI agents to automate emergency response workflows:

* 🏥 Hospital discovery
* 🚦 Transport & traffic estimation
* 👨‍⚕️ Hospital readiness preparation
* 🧠 Intelligent severity assessment

All agents are orchestrated in a strict execution order to ensure deterministic, structured outputs.

---

## 🚨 Problem

Emergency response systems are fragmented:

* No unified hospital discovery
* No coordinated traffic planning
* No hospital resource pre-allocation
* Delays in communication between services

In critical situations, seconds matter.

---

## 💡 Solution

ECC acts as a central AI orchestrator that:

1. Receives emergency input
2. Determines injury severity
3. Finds the best hospital
4. Calculates transport metrics
5. Prepares hospital intake resources
6. Returns a structured emergency response plan

This is achieved using distributed AI agents connected through the ZyndAI decentralized agent network.

---

## 🏗 Architecture

### 🟢 Main Orchestrator

* Receives emergency request
* Calls agents in strict order
* Aggregates responses
* Returns final structured JSON

---

### 🏥 Hospital Agent

Role: Medical Facility Dispatcher
Input:

```json
{
  "injury": "string",
  "location": "string"
}
```

Output:

```json
{
  "hospitalName": "string",
  "address": "string",
  "specialty": "string",
  "confidence": 0-1
}
```

---

### 🚦 Traffic Agent

Role: Emergency Logistics Coordinator
Input:

```json
{
  "incidentLocation": "string",
  "destination": "string"
}
```

Output:

```json
{
  "eta": "string",
  "distance": number,
  "trafficDelay": number
}
```

---

### 👨‍⚕️ Doctor Agent

Role: Senior Intake Coordinator
Input:

```json
{
  "hospitalName": "string",
  "eta": "string",
  "injury": "string"
}
```

Output:

```json
{
  "bedStatus": "string",
  "onCallDoctor": "string",
  "intakeNote": "string",
  "hospitalCode": "string"
}
```

---

## 🔄 Execution Flow

1. Call Hospital_Search
2. Call X402_Hospital
3. Call Traffic_Search
4. Call X402_Traffic
5. Call Doctor_Search
6. Call X402_Doctor
7. Aggregate outputs
8. Return structured response

Strict execution order is enforced.

---

## 📥 Sample Input

```json
{
  "patientId": "P001",
  "injury": "Severe head trauma",
  "location": "T Nagar, Chennai"
}
```

---

## 📤 Sample Output

```json
{
  "patientId": "P001",
  "incident": {
    "injury": "Severe head trauma",
    "location": "T Nagar, Chennai",
    "severity": "Critical"
  },
  "hospital": {
    "hospitalName": "Apollo Hospital Chennai",
    "address": "21 Greams Lane, Chennai",
    "specialty": "Neuro Trauma",
    "confidence": 0.94
  },
  "transport": {
    "eta": "22 mins",
    "distance": 8.5,
    "trafficDelay": 6
  },
  "hospitalReadiness": {
    "bedStatus": "Reserved & Ready",
    "onCallDoctor": "Dr. Mehta",
    "intakeNote": "Prepare neuro trauma unit and ventilator support.",
    "hospitalCode": "TRAUMA-ZONE-A"
  },
  "status": "Emergency Coordinated Successfully"
}
```

---

## ⚙️ Tech Stack

* n8n
* ZyndAI Network
* X402 Webhook Payments
* LangChain Agents
* Google Gemini
* OpenAI
* Structured Output Parsers
* JSON Schema Enforcement

---

## 🔐 Deterministic Design

* Structured output parsers enforce schema
* Strict tool calling order
* No free-form responses
* Production-style JSON outputs

---

## 🌍 Impact

This project demonstrates how decentralized AI agents can coordinate critical emergency infrastructure securely and autonomously.

It showcases:

* Multi-agent orchestration
* Blockchain-integrated AI economy
* Real-world emergency use case
* Deterministic AI execution
