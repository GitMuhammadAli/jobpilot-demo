<div align="center">

<h1>JobPilot</h1>

### Apply to jobs the way you would — only faster.

An AI co-pilot that scrapes 8 job boards, scores every role against your real profile, and runs a 4-agent pipeline to tailor your resume and write the application — **without ever inventing a skill you don't have.**

<br/>

[![Live](https://img.shields.io/badge/▶_Live_App-job--auto--applier--three.vercel.app-10b981?style=for-the-badge&labelColor=06231a)](https://job-auto-applier-three.vercel.app)
[![Demo](https://img.shields.io/badge/Watch_the_demo-▶-10b981?style=for-the-badge&labelColor=06231a)](#-demo)

![Next.js](https://img.shields.io/badge/Next.js_14-000?style=flat-square&logo=next.js)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=fff)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=flat-square&logo=prisma)
![Postgres](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=fff)
![Groq](https://img.shields.io/badge/Groq_LLM-10b981?style=flat-square)

</div>

---

## 🎬 Demo

https://github.com/user-attachments/assets/2b459d69-979c-48f7-b99b-f8ea159e2d8b

> A cinematic product promo. ▶ Also runs as an interactive film → **[gitmuhammadali.github.io/jobpilot-demo](https://gitmuhammadali.github.io/jobpilot-demo/)**

**▶ Live app:** **https://job-auto-applier-three.vercel.app**

---

## The problem

Job hunting is a full-time job. You copy-paste the same application into a hundred forms, tweak the same resume, and write the same email — at midnight, for weeks. Generic "AI apply" tools make it worse: they spray, they hallucinate skills you don't have, and recruiters spot the slop in five seconds.

## The solution

JobPilot does the busywork **honestly**. It finds roles that actually fit, tailors your real experience to each one, and drafts the application — with an audit that rejects any fabricated claim before you ever see it.

---

## ✨ What makes it different

| | |
|---|---|
| 🎯 **It scores, it doesn't spray** | Every job is matched **0–100** against your skills, location and preferences. You apply where you fit — not to everything. |
| 🤖 **A 4-agent pipeline** | **Research → Tailor → Write → QA.** Four AI agents study the company, map your real skills to the role, draft a personalized email, and score it for spam + quality. |
| 🛡️ **It can't lie on your resume** | A strict **anti-fabrication audit** rejects any word in the generated resume not traceable to your real profile. No invented skills, no fake metrics. |
| ✍️ **Writes like a human, not an AI** | The generator is trained against the exact tells recruiters screen out — banned buzzwords, context-free metrics, soft-skill filler. |
| ⚡ **Cost-controlled & resilient** | Multi-provider LLM routing (Groq → Gemini → Ollama) with fallback, per-user token budgets, and DB-persisted circuit breakers on the scrapers. |
| 📬 **Your email, your reputation** | Send from your own Gmail with rate limiting + bounce handling, or copy-paste. You stay in control. |

---

## 🧩 How the pipeline works

```
 Job posting ──▶ ① Researcher ──▶ ② Resume Tailor ──▶ ③ Email Writer ──▶ ④ QA Checker ──▶ ✅ Ready to send
                  studies the       maps your real      drafts the          scores spam +
                  company           skills (no fakes)   personalized email  quality, refunds
                                    + honesty audit                          on failure
```

Each agent uses **native function-calling** for schema-constrained output (no parse-and-pray), with a JSON-prompt fallback so the pipeline never hard-fails.

---

## 🏗️ Tech

- **Frontend:** Next.js 14 (App Router), React, TypeScript, Tailwind, shadcn/ui
- **Backend:** Next.js API routes + server actions, Prisma, Neon Postgres
- **AI:** Groq (primary) → Gemini → Ollama fallback chain · native tool-calling · per-user token quotas
- **Scraping:** 8 sources, quota-budgeted, DB-persisted circuit breakers
- **Email:** multi-provider SMTP, rate limiting, encrypted credentials, bounce handling
- **Infra:** Vercel, Sentry, 463 unit tests

---

## 📊 By the numbers

- **8** job sources scraped & deduped
- **4** cooperating AI agents per application
- **0** fabricated skills (enforced by audit)
- **463** passing unit tests

---

<div align="center">

**Built by Ali Shahid** · [Portfolio](https://alishahid-dev.vercel.app) · [LinkedIn](https://linkedin.com/in/alishahid-fswebdev)

</div>
