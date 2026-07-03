# 🔌 API Design

# CoraAI API Specification

---

# Overview

The CoraAI backend exposes REST APIs that connect the frontend with the Multi-Agent AI system.

All requests are received by the FastAPI backend, processed by the Coordinator Agent, and routed to the appropriate AI agents.

---

# Base URL

/api/v1

---

# Authentication APIs

## Register User

POST /auth/register

Purpose:
Register a new user.

---

## Login

POST /auth/login

Purpose:
Authenticate user and return JWT token.

---

## Get User Profile

GET /auth/profile

Purpose:
Return authenticated user details.

---

# Citizen APIs

## Analyze Scam Message

POST /analyze/message

Input

- SMS
- Email
- Chat

Response

- Scam Probability
- Scam Type
- Confidence Score

---

## Analyze Website

POST /analyze/url

Input

- URL

Response

- Safe
- Suspicious
- High Risk

---

## Analyze Phone Number

POST /analyze/phone

Input

Phone Number

Response

Risk Score

---

## Analyze QR Code

POST /analyze/qr

Input

QR Image

Response

Safe / Fraud

---

## Analyze Currency

POST /analyze/currency

Input

Currency Image

Response

Real / Fake

---

## Report Fraud

POST /reports

Purpose

Submit fraud report.

---

# Police APIs

## Fraud Dashboard

GET /dashboard/police

---

## Fraud Heatmap

GET /dashboard/heatmap

---

## Fraud Network

GET /graph/network

---

## Investigation Report

GET /reports/{id}

---

# Bank APIs

## Fraud Alerts

GET /alerts

---

## Risk Assessment

POST /risk/analyze

---

## Verify Account

POST /verify/account

---

# AI APIs

## Coordinator Agent

POST /agents/coordinator

---

## Communication Agent

POST /agents/communication

---

## Counterfeit Agent

POST /agents/counterfeit

---

## Fraud Graph Agent

POST /agents/graph

---

## Geo Intelligence Agent

POST /agents/geo

---

## Threat Intelligence Agent

POST /agents/threat

---

## Risk Fusion Engine

POST /agents/fusion

---

# Admin APIs

GET /users

GET /reports

GET /logs

GET /analytics

---

# API Response Format

```json
{
  "success": true,
  "message": "Analysis Completed",
  "data": {},
  "timestamp": "2026-07-04T12:00:00Z"
}
```

---

# Error Response

```json
{
  "success": false,
  "error": "Invalid Input",
  "status": 400
}
```

---

# Future APIs

- Voice Scam Detection
- Deepfake Detection
- Banking Integration
- Telecom Integration
- Government API Integration
