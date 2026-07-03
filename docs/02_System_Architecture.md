# 🏗️ System Architecture

# CoraAI - Multi-Agent AI Powered Digital Public Safety Intelligence Platform

---

# 1. Architecture Overview

CoraAI follows a **Multi-Agent AI Architecture**, where multiple specialized AI agents collaborate to analyze different types of fraud-related information. Instead of relying on a single AI model, each agent is responsible for a specific task, while a central Coordinator Agent orchestrates the workflow and a Risk Fusion Agent combines results into a final intelligence report.

This modular architecture improves scalability, explainability, maintainability, and allows independent development of each AI component.

---

# 2. High-Level Architecture

```
                           Users
                              │
      ┌───────────────────────┼────────────────────────┐
      │                       │                        │
      ▼                       ▼                        ▼
   Citizens                 Banks                 Law Enforcement
                              │
                              ▼
                    React Web Application
                              │
                              ▼
                    FastAPI Backend Server
                              │
                              ▼
                     Coordinator AI Agent
                              │
      ┌──────────────┬──────────────┬──────────────┬──────────────┐
      ▼              ▼              ▼              ▼
Communication   Counterfeit    Fraud Graph      Geo Intelligence
    Agent          Agent           Agent             Agent
      │              │              │                  │
      └──────────────┴──────────────┴──────────────────┘
                              │
                              ▼
                 Threat Intelligence Agent
                              │
                              ▼
                    Risk Fusion Agent
                              │
          ┌───────────────────┼───────────────────┐
          ▼                   ▼                   ▼
   PostgreSQL Database    Neo4j Database      Alert Engine
                              │
                              ▼
                   Dashboard & Investigation Report
```

---

# 3. System Components

## Frontend Layer

Technology:

- React
- Tailwind CSS
- Chart.js
- Leaflet

Responsibilities:

- User Authentication
- Dashboard
- Fraud Reports
- Risk Visualization
- Crime Heatmap
- Investigation Graph

---

## Backend Layer

Technology:

- FastAPI

Responsibilities:

- API Gateway
- Authentication
- Request Validation
- Agent Communication
- Database Management

---

## AI Layer

The AI layer consists of specialized agents working together under the supervision of the Coordinator Agent.

Each agent performs one dedicated responsibility.

---

## Data Layer

PostgreSQL

- Users
- Reports
- Risk Scores
- Logs

Neo4j

- Fraud Networks
- Device Relationships
- Phone Numbers
- UPI IDs
- Bank Accounts

---

# 4. AI Agent Architecture

## Coordinator Agent

Responsibilities

- Receives every request
- Identifies request type
- Calls required AI agents
- Coordinates workflow
- Sends outputs to Risk Fusion

---

## Communication Agent

Purpose

Detect scam communications.

Input

- SMS
- Email
- WhatsApp
- Call Transcript

Output

- Scam Probability
- Scam Type
- Confidence Score

---

## Counterfeit Detection Agent

Purpose

Detect counterfeit currency.

Input

Currency Image

Output

- Genuine
- Counterfeit
- Confidence Score

---

## Fraud Graph Agent

Purpose

Discover organized fraud networks.

Input

- Phone Number
- Bank Account
- UPI ID
- Device ID
- IP Address

Output

Fraud Relationship Graph

---

## Geo Intelligence Agent

Purpose

Detect regional fraud trends.

Input

- Complaint Location
- Fraud Reports
- Seizure Data

Output

- Heatmap
- Crime Hotspots

---

## Threat Intelligence Agent

Purpose

Generate contextual intelligence.

Combines:

- Historical fraud
- AI predictions
- Criminal relationships

Output

Threat Summary

---

## Risk Fusion Agent

Purpose

Merge outputs from every AI agent.

Calculates

- Overall Risk Score
- Threat Level
- Recommended Actions

---

# 5. Data Flow

Step 1

User submits request.

↓

Step 2

Backend validates request.

↓

Step 3

Coordinator Agent identifies required AI agents.

↓

Step 4

Selected AI agents perform analysis.

↓

Step 5

Threat Intelligence Agent enriches results.

↓

Step 6

Risk Fusion Agent generates final assessment.

↓

Step 7

Backend stores results.

↓

Step 8

Dashboard displays intelligence.

---

# 6. Technology Stack

Frontend

- React
- Tailwind CSS
- Chart.js
- Leaflet

Backend

- FastAPI
- Python

AI

- PyTorch
- HuggingFace
- OpenCV
- Scikit-learn

Database

- PostgreSQL
- Neo4j

Deployment

- Docker
- GitHub Actions

---

# 7. Design Principles

- Modular
- Scalable
- Explainable AI
- Independent AI Agents
- Fault Tolerant
- Easy Integration

---

# 8. Advantages of Multi-Agent Architecture

- Independent AI modules
- Parallel processing
- Easy maintenance
- Better scalability
- Higher explainability
- Future-ready architecture

---

# Conclusion

The Multi-Agent AI architecture enables CoraAI to combine specialized intelligence from multiple AI systems into a unified fraud detection platform. This approach allows the platform to proactively identify digital threats, assist investigations, and provide explainable, actionable intelligence to citizens, financial institutions, and law enforcement agencies.
