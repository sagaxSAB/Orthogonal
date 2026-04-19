# Helium — AI Career Co-Pilot

Helium is your AI co-pilot for the full career journey: explore careers, sharpen your resume, and practice live interviews with instant feedback.
---

## ✨ Features

- **Career Exploration** — Search any role or take a short quiz to get salary ranges, AI-impact score, required skills, a learning roadmap, and a concrete next step.
- **Resume Analyzer** — Upload your PDF resume, get an overall score, ATS keyword gaps, and AI-rewritten bullet points.
- **AI Voice Interview** — Practice real interview questions out loud. Get scored on clarity, confidence, relevance, and structure, with a "better answer" example.

---

## 🛠 Tech Stack

| Layer | Tech |
|---|---|
| Frontend | React 18, Vite 5, TypeScript 5, Tailwind CSS, shadcn/ui |
| Routing / State | React Router, TanStack Query |
| Backend | Lovable Cloud (Supabase Edge Functions) |f
| AI | Lovable AI Gateway → Google Gemini (2.5 Flash / 3 Flash Preview) |
| PDF parsing | pdfjs-dist |
| Voice | MediaRecorder API + Gemini multimodal transcription |

---

## 🚀 Run Locally (macOS)

### Prerequisites
- **Node.js 18+** ([download](https://nodejs.org/))
- npm (bundled with Node) or Bun

### Setup

```bash
# 1. Install dependencies
npm install

# 2. Start the dev server
npm run dev
```

Open **http://localhost:8080** in your browser.

## 📁 Project Structure

```
src/
  pages/              # Index, Explore, Resume, Interview, NotFound
  components/         # PageShell, SiteHeader, Questionnaire, CareerProfileView, ui/
  lib/                # pdf.ts, utils.ts
  integrations/
    supabase/         # auto-generated client + types (DO NOT EDIT)
  types/career.ts     # shared TS types
supabase/
  functions/
    career-profile/   # Returns full career profile JSON
    career-recommend/ # Returns 3-5 career matches from quiz answers
    resume-analyze/   # Scores + improves a resume
    interview/        # Generates questions, scores answers, summarizes session
    transcribe/       # Audio → text via Gemini multimodal
```

---
