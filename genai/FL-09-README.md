
# AI-Powered Portfolio Chat Agent

A chat widget integrated into my portfolio that allows visitors to ask questions about my background, technical skills, projects, and experience — powered by Gemini 2.5 Flash.

**Live Demo:** [https://millyanne93-portfolio.netlify.app/](https://millyanne93-portfolio.netlify.app/)

---

## What It Does

- Visitors can ask questions about my professional background
- The agent responds with accurate information about my skills, projects, and experience
- Responses are generated using Gemini 2.5 Flash via a Netlify serverless function
- The agent is intentionally constrained to avoid hallucinations

---

## Who It's For

- Recruiters and hiring managers researching my background
- Potential collaborators wanting to understand my technical experience
- Anyone visiting my portfolio who wants a quick overview of my work

---

## Architecture
┌─────────────────────────────┐
│ Portfolio Website │
│ │
│ HTML / CSS / JS │
│ Chat Widget │
└──────────────┬──────────────┘
│
│ HTTPS request
▼
┌─────────────────────────────┐
│ Netlify Function │
│ │
│ - Receives user question │
│ - Builds system prompt │
│ - Calls Gemini API │
│ - Returns AI response │
└──────────────┬──────────────┘
│
│ HTTPS
▼
┌──────────────────────────────────────────────┐
│ Google Gemini API │
│ │
│ Gemini 2.5 Flash │
│ │
└──────────────────────────────────────────────┘

text

---

## System Prompt Design

The agent is intentionally constrained to avoid hallucinations and keep responses focused:
You are an AI assistant for Millyanne Wanjala's portfolio.

Your purpose is to answer questions about:

Her professional background and experience

Her technical skills and technologies used

Her projects (PlanIt, EduAdapt, Trackr, Widget Platform, Image Matching Engine)

Her education and certifications

Important rules:

Only answer questions about Millyanne

If you don't know something, say you don't know

Do not invent projects, skills, or qualifications

Politely decline unrelated questions

text

---

## Quick Start

### Prerequisites
- Node.js (v18+)
- Netlify account (free)
- Gemini API key (free from Google AI Studio)

### Setup Instructions

1. Clone the repository
2. Install dependencies
3. Set up environment variables
4. Deploy to Netlify
5. The agent is now live on your portfolio

---

## Evaluation Results

| Metric | Result |
|--------|--------|
| Response time | 2-5 seconds |
| Accuracy | High (constrained scope) |
| Hallucination rate | Low (system prompt designed to prevent) |
| Free tier limits | 15 req/min, 1,500 req/day |

---

## Limitations

| Limitation | Description | Why It Exists |
|------------|-------------|---------------|
| No conversation persistence | Chat history resets on page refresh | Simpler implementation, no database required |
| No rate limiting | High traffic could exhaust API credits | Low-traffic portfolio site |
| Limited knowledge scope | Only answers questions about Millyanne | Intentional design to prevent hallucinations |
| Free tier only | Could exceed limits with high traffic | Portfolio is low-traffic, free tier is sufficient |

---

## Links

- **Live Portfolio:** [https://millyanne93-portfolio.netlify.app/](link)
- **GitHub Repository:** [https://github.com/millyanne93/Gen-AI-Fluency-Capstone1/tree/master](link)
