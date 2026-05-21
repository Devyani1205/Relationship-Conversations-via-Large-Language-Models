
# Social Media Post Generation for Advertisement

A comprehensive AI-powered system for generating research-backed social media content using agentic AI workflows. The system leverages multiple specialized agents to conduct research, analyze competitors, and generate engaging posts optimized for LinkedIn and Twitter/X platforms.

---

# Project Overview

This project implements a multi-agent system that automates content creation for social media marketing. It combines web search capabilities, deep research analysis, competitor intelligence gathering, and AI-driven content generation to produce high-quality, engagement-optimized social media posts.

## Key Features

- Multi-agent architecture with specialized roles
- Integration with Groq LLM for fast inference
- Real-time web search and website scraping capabilities
- Competitor content analysis and strategy insights
- Character-aware tweet generation
- Thread and individual tweet generation modes
- REST API backend with Flask
- Streamlit web interface
- Pydantic models for structured data validation

---

# Architecture

## System Components

### 1. Backend API (Flask)

Features:
- RESTful endpoints for content generation
- CORS support for cross-origin requests
- Request validation and error handling

File:
```bash
twitter_content_app.py
```

---
<img width="494" height="705" alt="image" src="https://github.com/user-attachments/assets/8f0f66b9-8436-46d1-a53b-81cdc94dff02" />

### 2. Frontend Interface (HTML/JavaScript)

Features:
- Single Page Application (SPA) interface
- Real-time form validation
- Response streaming and loading states
- Copy-to-clipboard functionality

File:
```bash
index.html
```

---

### 3. Streamlit Application

Features:
- Advanced web UI for configuration
- API key management
- Feature toggles
- Download functionality

---

# Agent System

The platform uses four specialized agents:

1. Web Search Agent
2. Deep Research Agent
3. Competitor Analysis Agent
4. Content Writer Agent

---

# Technical Stack

| Technology | Purpose |
|---|---|
| agno | Agentic AI framework |
| groq | LLM API integration |
| flask | REST API framework |
| flask-cors | CORS support |
| streamlit | Web UI framework |
| requests | HTTP client |
| pydantic | Data validation |

---

# Installation

## Prerequisites

- Python 3.8+
- Groq API key
- Firecrawl API key (optional)

---

## Setup

### Clone Repository

```bash
git clone https://github.com/Devyani1205/Social-Media-Post-Generation-for-Advertisement.git

cd Social-Media-Post-Generation-for-Advertisement
```

---

### Create Virtual Environment

```bash
python -m venv venv
```

Linux/macOS:
```bash
source venv/bin/activate
```

Windows:
```bash
venv\Scripts\activate
```

---

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

### Configure Environment Variables

Linux/macOS:
```bash
export GROQ_API_KEY="your_groq_api_key"
export FIRECRAWL_API_KEY="your_firecrawl_api_key"
```

Windows:
```bash
set GROQ_API_KEY=your_groq_api_key
set FIRECRAWL_API_KEY=your_firecrawl_api_key
```

---

# Usage

## Option 1: Flask REST API

### Start Backend

```bash
python twitter_content_app.py
```

### API Endpoint

```http
POST http://localhost:5000/api/generate
```

### Request Example

```json
{
  "brand_name": "MindNXT",
  "website_summary": "AI-powered learning platform",
  "tone": "Professional",
  "goal": "Increase Engagement"
}
```

---

## Option 2: Streamlit Application

```bash
streamlit run twitter_content_app.py
```

Access:
```text
http://localhost:8501
```

---

## Option 3: Web Interface

Open:
```bash
index.html
```

in a browser and connect it to the Flask backend.

---

# Workflow Process

1. Input Phase
2. Research Phase
3. Processing Phase
4. Generation Phase
5. Output Phase

---

# API Response Format

## Success Response

```json
{
  "success": true,
  "content": "Generated tweet content"
}
```

## Error Response

```json
{
  "success": false,
  "error": "Error description"
}
```

---

# File Structure

```bash
.
├── twitter_content_app.py
├── index.html
├── requirements.txt
├── README.md
└── twitter_content_report.pdf
```

---




References:- 

https://medium.com/@michael.j.hamilton/conversational-memory-with-langchain-82c25e23ec60
https://github.com/GoogleCloudPlatform/generative-ai/blob/main/gemini/orchestration/intro_langchain_gemini.ipynb
https://youtu.be/BlAqIS1fEBU?si=x29hoMb-HyCl6ZMd
https://youtu.be/BlAqIS1fEBU?si=N-I8Tmn0BTGeZgG6
https://youtu.be/fizZ9mqY1Fs?si=csv2ZoCR5NALockR
https://youtu.be/s5MMPp_WQok?si=5iQc6cJf3Uc-8P5h
https://youtu.be/A3WKdt_MNZQ?si=HMETw0gRksqvD5-S
https://youtu.be/GgeoyzWBrSI?si=vD4pDQdlbiloQMfT
https://youtu.be/nAKhxQ3hcMA?si=XY8rNQS5hICV4XvM
https://youtu.be/nAKhxQ3hcMA?si=TQDOECMoqgJCEIlJ
https://github.com/pinecone-io/examples/blob/master/docs/pinecone-reranker.ipynb

