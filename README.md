# HuntO 🚀
### AI-Powered Autonomous Job Application Platform

> **HuntO** (Hunt Opportunities) is an AI-powered job automation platform that discovers relevant jobs, analyzes compatibility, customizes resumes, generates cover letters, auto-fills applications, tracks every submission, and continuously improves using AI feedback—all with a fully autonomous workflow built primarily on free-tier services.

---

## 📖 Table of Contents

- [Overview](#overview)
- [Vision](#vision)
- [Key Features](#key-features)
- [System Architecture](#system-architecture)
- [Complete Workflow](#complete-workflow)
- [Technology Stack](#technology-stack)
- [Microservices](#microservices)
- [Data Flow](#data-flow)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Environment Variables](#environment-variables)
- [Running the Project](#running-the-project)
- [API Flow](#api-flow)
- [Future Roadmap](#future-roadmap)
- [Security](#security)
- [License](#license)

---

# Overview

Searching and applying for jobs is repetitive, time-consuming, and inefficient.

HuntO automates the complete process using AI.

Instead of manually searching, tailoring resumes, filling applications, and tracking submissions, HuntO continuously performs these tasks in the background while learning from recruiter responses.

The platform combines AI agents, browser automation, resume optimization, job matching, and analytics into one autonomous system.

---

# Vision

Build an AI agent capable of acting as a personal career assistant that:

- Finds opportunities
- Understands job descriptions
- Tailors resumes
- Generates cover letters
- Applies automatically
- Tracks recruiter responses
- Learns from outcomes
- Improves future applications

---

# Key Features

## 🤖 AI Job Discovery

- LinkedIn Jobs
- Indeed
- Naukri
- Wellfound
- Greenhouse
- Lever
- Company Career Pages

---

## 🎯 AI Resume Matching

- ATS compatibility scoring
- Skill gap analysis
- Resume optimization
- Keyword extraction
- Experience matching

---

## 📝 AI Resume Customization

Generates a customized resume for every application based on:

- Job Description
- Required Skills
- ATS Keywords
- Experience Weightage

---

## ✉️ AI Cover Letter Generation

Automatically generates personalized cover letters using:

- Company details
- Role requirements
- Resume
- Job Description

---

## 🤖 Autonomous Application Bot

Supports automated application on multiple platforms using:

- Browser Automation
- Smart Form Filling
- AI Field Detection
- Resume Upload
- Cover Letter Upload
- Human-like interaction

---

## 📊 Application Tracking

Tracks:

- Applied Jobs
- Interview Status
- OA Invitations
- Recruiter Replies
- Rejections
- Offers

---

## 📈 Analytics Dashboard

Provides insights including:

- Applications per week
- Response rate
- ATS score trend
- Interview conversion
- Resume effectiveness
- Best performing keywords

---

## 🔄 Continuous Learning

AI continuously improves by learning from:

- Recruiter feedback
- Resume success rate
- Interview invitations
- Rejection patterns

---

# System Architecture

```
                +------------------------+
                |     React Dashboard    |
                +-----------+------------+
                            |
                            |
                    NestJS Backend API
                            |
      -------------------------------------------------
      |        |         |        |        |           |
 Job   Resume  AI      Browser  Tracker  Scheduler
Crawler Engine Service Automation Service
      |        |         |        |        |
      -------------------------------
                    |
              PostgreSQL
                    |
                 Redis Queue
                    |
             Background Workers
```

---

# Complete Workflow

## Phase 1 — User Onboarding

```
User
   │
   ▼
Authentication
   │
   ▼
Profile Creation
   │
   ▼
Resume Upload
   │
   ▼
Career Preferences
```

Collected Information

- Resume
- Skills
- Experience
- Preferred Roles
- Preferred Locations
- Salary Expectation
- Work Authorization
- Portfolio
- LinkedIn
- GitHub

---

## Phase 2 — Resume Parsing

```
Resume
     │
     ▼
AI Parser
     │
     ├────────────► Skills
     ├────────────► Education
     ├────────────► Experience
     ├────────────► Projects
     ├────────────► Certifications
     ├────────────► ATS Keywords
```

Stored inside PostgreSQL.

---

## Phase 3 — Job Discovery

Scheduler triggers crawlers.

```
Scheduler

     │

     ├── LinkedIn
     ├── Greenhouse
     ├── Lever
     ├── Wellfound
     ├── Indeed
     ├── Company APIs
```

Jobs are normalized into a common schema.

---

## Phase 4 — AI Matching

Each discovered job is analyzed.

```
Job Description
        │
        ▼
Embedding Model
        │
        ▼
Similarity Search
        │
        ▼
ATS Score
        │
        ▼
Recommendation Engine
```

Outputs

- Match %
- Missing Skills
- Strengths
- Resume Suggestions

---

## Phase 5 — Resume Optimization

```
Resume
     │
     ▼
LLM
     │
     ▼
Customized Resume
```

Generated per job.

---

## Phase 6 — Cover Letter

```
Resume
+
Job Description
+
Company Info
      │
      ▼
LLM
      │
      ▼
Personalized Cover Letter
```

---

## Phase 7 — Automated Application

```
Job
   │
Browser Automation
   │
AI Form Detection
   │
Field Mapping
   │
Resume Upload
   │
Cover Letter Upload
   │
Application Submit
```

Supports

- Easy Apply
- Multi-page Forms
- Company ATS
- External Websites

---

## Phase 8 — Verification

After submission:

- Screenshot
- Confirmation ID
- Success Detection
- Duplicate Detection

Stored in database.

---

## Phase 9 — Tracking

Background workers monitor:

```
Emails
LinkedIn
Company Portal
```

Status updates:

```
Applied

↓

Under Review

↓

Assessment

↓

Interview

↓

Offer

↓

Rejected
```

---

## Phase 10 — AI Learning Loop

```
Application Results

        │

Recruiter Feedback

        │

Interview Rate

        │

Resume Performance

        │

AI Fine Tuning

        │

Better Future Applications
```

---

# Technology Stack

## Frontend

- React
- TypeScript
- TailwindCSS
- ShadCN UI
- React Query
- React Router
- Framer Motion

---

## Backend

- NestJS
- TypeScript
- Prisma ORM
- PostgreSQL
- Redis

---

## AI

- Gemini API (Free Tier)
- LangChain
- Embeddings
- RAG Pipeline
- Prompt Engineering

---

## Automation

- Puppeteer
- Browserless (Free Tier)
- Playwright (Fallback)

---

## Database

- PostgreSQL
- Redis

---

## Authentication

- Clerk
- JWT

---

## Storage

- Supabase Storage (Free Tier)

---

## Deployment

- Vercel
- Railway
- Supabase
- GitHub Actions

---

# Microservices

```
apps/

├── api
├── auth
├── ai-service
├── crawler
├── automation
├── tracker
├── scheduler
├── notification
└── dashboard
```

---

# Data Flow

```
User

↓

Resume Upload

↓

Resume Parser

↓

Database

↓

Job Crawlers

↓

Matching Engine

↓

Resume Generator

↓

Cover Letter Generator

↓

Browser Automation

↓

Application

↓

Tracker

↓

Analytics
```

---

# Project Structure

```
hunto/

apps/
   frontend/
   backend/
   crawler/
   automation/
   ai/
   tracker/

packages/
   ui/
   shared/
   config/

docs/

docker/

scripts/

.github/

README.md
```

---

# Installation

```bash
git clone https://github.com/your-org/hunto.git

cd hunto

npm install
```

---

# Environment Variables

```env
DATABASE_URL=

REDIS_URL=

SUPABASE_URL=

SUPABASE_KEY=

JWT_SECRET=

GEMINI_API_KEY=

BROWSERLESS_TOKEN=

CLERK_SECRET_KEY=
```

---

# Running the Project

Backend

```bash
npm run start:backend
```

Frontend

```bash
npm run start:frontend
```

Crawler

```bash
npm run crawler
```

Automation Worker

```bash
npm run automation
```

AI Worker

```bash
npm run ai
```

---

# API Flow

```
Login

↓

Upload Resume

↓

Parse Resume

↓

Discover Jobs

↓

Generate Match Score

↓

Optimize Resume

↓

Generate Cover Letter

↓

Auto Apply

↓

Track Status

↓

Analytics Dashboard
```

---

# Future Roadmap

### Version 1

- Resume Parsing
- Job Discovery
- ATS Matching
- Auto Apply
- Dashboard

---

### Version 2

- AI Interview Preparation
- AI Resume Review
- AI Career Coach
- Salary Prediction
- Recruiter Insights

---

### Version 3

- Multi-Agent AI System
- Voice Career Assistant
- Referral Discovery
- Networking Suggestions
- AI Portfolio Builder

---

# Security

- JWT Authentication
- Role-Based Access Control
- Encrypted Secrets
- Secure File Storage
- HTTPS Everywhere
- Rate Limiting
- Input Validation
- Audit Logs

---

# Contributing

We welcome contributions from developers, designers, and AI enthusiasts.

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push your branch
5. Open a Pull Request

---

# License

This project is licensed under the **MIT License**.

---

# Contributors

Built with ❤️ by the HuntO Team.

---

# Why HuntO?

HuntO transforms job searching into an autonomous AI-driven experience.

Instead of spending hours searching and applying, users simply define their career preferences, and HuntO continuously finds opportunities, tailors applications, submits them intelligently, tracks progress, and learns from every outcome.

> **Find Opportunities. Apply Smarter. Get Hired Faster.**
