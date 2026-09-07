# 📄 AI Resume Analyzer

![React](https://img.shields.io/badge/React_18-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS_v4-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript_ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![OpenAI](https://img.shields.io/badge/OpenAI_GPT--4o-412991?style=for-the-badge&logo=openai&logoColor=white)
![Puter.js](https://img.shields.io/badge/Puter.js_AI_SDK-0A84FF?style=for-the-badge&logo=cloud&logoColor=white)
![PDF.js](https://img.shields.io/badge/PDF.js-FF0000?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)

> A client-side, AI-driven web application that parses PDF resumes in the browser and leverages GPT-4o via Puter.js to generate ATS readiness evaluations, performance metrics, and actionable career insights.

---

## 📝 Project Description

**AI Resume Analyzer** is a modern React application built to streamline how candidates evaluate and polish their resumes for Applicant Tracking Systems (ATS). Instead of relying on heavy backend infrastructures or risky server-side file uploads, this application executes client-side PDF document parsing directly in the browser using `pdfjs-dist`.

Once parsed, the extracted document text is evaluated against ATS criteria using OpenAI's **GPT-4o** model orchestrated via the **Puter.js AI API**. The application provides an instant assessment consisting of an overall ATS score, categorized strengths and weaknesses, visual metric progress bars, an ATS formatting checklist, and industry-tailored keywords.

---

## ✨ Key Features

- **⚡ Client-Side PDF Text Extraction:** Parses multi-page PDF documents entirely in-browser using `pdfjs-dist` and web workers—zero server file storage required.
- **🧠 Zero-Backend GPT-4o Integration:** Connects directly to OpenAI's GPT-4o model via `window.puter.ai.chat`, enabling serverless AI evaluation without exposing private API keys.
- **🏆 ATS Score & Verdict:** Calculates a 1–10 overall ATS readiness rating with visual indicators (Excellent, Good, Needs Improvement) and dynamic progress bars.
- **✅ ATS Compatibility Checklist:** Inspects the resume for essential candidate sections (contact information, work experience, education, skills, metrics).
- **📊 Granular Performance Metrics:** Breaks down resume effectiveness across core evaluation dimensions (Content Quality, Keyword Match, Impact & Metrics, Readability).
- **⚡ Action Items & Pro Tips:** Delivers actionable recommendations and targeted advice on phrasing, bullet points, and action verbs.
- **🔑 Recommended Keywords:** Generates tailored industry and technical keywords to incorporate naturally to beat automated resume filters.
- **🎨 Modern Glassmorphic UI:** Styled with Tailwind CSS, custom gradients, Outfit typography, responsive layouts, and interactive micro-animations.

---

## 🛠️ Technologies & Stack

### Frontend & Core
- **Framework / Bundler:** [React 18](https://react.dev/) + [Vite](https://vitejs.dev/)
- **Language:** Modern JavaScript (ES6+ / JSX)
- **Styling:** [Tailwind CSS](https://tailwindcss.com/) with custom gradient design tokens and Google Font [Outfit](https://fonts.google.com/specimen/Outfit)

### Document Parsing & AI
- **Document Extraction:** [`pdfjs-dist`](https://mozilla.github.io/pdf.js/) for in-browser client-side PDF rendering and text layer extraction.
- **AI Model & Provider:** OpenAI `gpt-4o` powered via the [Puter.js](https://puter.com/) v2 SDK (`window.puter.ai.chat`).
- **Data Serialization & Prompts:** Custom prompt engineering configured to extract structured JSON responses with robust fallback error handling.

---

## 🏗️ How It Works (Application Flow)
``` 
[ 1. User Uploads Resume (.pdf) ]
              │
              ▼
[ 2. In-Browser Text Extraction (pdfjs-dist) ]
  • Reads array buffer from File object
  • Iterates through pages with web worker
  • Assembles clean, unified plain text
              │
              ▼
[ 3. Local ATS Presence Check & Prompt Construction ]
  • Checks essential structural sections
  • Injects extracted text into ANALYZE_RESUME_PROMPT
              │
              ▼
[ 4. Serverless AI Inference (Puter.js + GPT-4o) ]
  • Sends system & user prompt to window.puter.ai.chat
  • Extracts and validates structured JSON schema
              │
              ▼
[ 5. Dynamic Interactive Dashboard ]
  • Overall ATS Score & Status Badge
  • Strengths & Priority Improvements
  • Executive Summary
  • Multi-attribute Performance Metric Bars
  • Action Items, Pro Tips & Recommended Keyword Badges
```