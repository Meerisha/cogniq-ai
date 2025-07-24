# CogniQ.ai

**AI‑powered progress monitoring & insight platform for neurodiverse education**

> Turning scattered therapy data into actionable, personalized growth plans

---

## ✨ What is CogniQ?

CogniQ.ai is a SaaS platform that aggregates data from therapists, speech & occupational specialists, and parents to create a single, real‑time dashboard for each child in Autism Spectrum Disorder (ASD) therapy. Using LLM‑based analytics, we detect plateaus early, recommend evidence‑backed adjustments, and automate reporting for insurance and school compliance.

## 🔑 Core Features

* **Unified Data Ingestion** – Connect clinic EMRs, Google Sheets, PDFs, and manual logs via secure APIs & CSV uploads.
* **Insight Engine** – OpenAI‑powered agent spots trends, predicts goal attainment, and suggests next‑best interventions.
* **Parent & Provider Dashboards** – Role‑based views with progress graphs, milestone timelines, and collaborative notes.
* **Automated Reports** – One‑click generation of IEP updates, Medicaid billing notes, and quarterly clinic summaries.
* **HIPAA‑grade Security** – Data encrypted at rest/in‑transit, RBAC, audit logs, and optional BAA.

## 🏗️ Tech Stack

| Layer                  | Tech                                                                 |
| ---------------------- | -------------------------------------------------------------------- |
| Front‑end              | Next.js 14 (App Router), TypeScript, Tailwind CSS                    |
| API / Serverless       | Vercel Edge Functions + Node 20                                      |
| AI / Agents            | OpenAI SDK, @mendable/firecrawl-js (web context), Tavily Search      |
| Data                   | Upstash Redis (cache + vector), PostgreSQL (Postgres.js), Prisma ORM |
| Dev Productivity       | pnpm, Turborepo, ESLint, Prettier, Vitest                            |
| Dev‑First Integrations | Model Context Protocol (MCP) & `.cursor/mcp.json`                    |

---

## 🚀 Quick Start

```bash
# 1. Clone
npx degit Meerisha/cogniq cogniq && cd cogniq

# 2. Install deps
pnpm i  # or npm/yarn

# 3. Copy env template & fill secrets
cp .env.example .env.local
#   OPENAI_API_KEY=sk-...
#   UPSTASH_REDIS_REST_URL=https://...
#   UPSTASH_REDIS_REST_TOKEN=...
#   FIRECRAWL_API_KEY=fc_...
#   TAVILY_API_KEY=tv_...

# 4. Run dev server (Next.js + MCP)
pnpm dev

# 5. Open http://localhost:3000  ➜  login with magic link
```

### MCP Tooling in Cursor

If you’re using [Cursor](https://cursor.sh):

1. Open the workspace.
2. Press **⌘K → Reload MCP** to auto‑discover the tools listed in `.cursor/mcp.json`.
3. In any chat, type `run generate_launch_strategy` and watch the agent pull live market data.

---

## 🛠️ Scripts

| Command      | Purpose                                      |
| ------------ | -------------------------------------------- |
| `pnpm dev`   | Start Next.js dev + hot‑reloading MCP server |
| `pnpm build` | Production build                             |
| `pnpm lint`  | ESLint + Typecheck                           |
| `pnpm test`  | Vitest unit tests                            |
| `pnpm mcp`   | Run only the MCP adapter without the web UI  |

---

## 📂 Project Structure

```
.
├── apps/web           # Next.js frontend
├── packages/tools     # MCP tools (TypeScript)
├── .cursor/mcp.json   # Project‑scoped MCP config
├── prisma/schema.prisma  # Postgres models
└── ...
```

---

## 📈 Roadmap

* [x] MVP with manual CSV upload
* [ ] OAuth & direct EMR integrations (TheraNest, SimplePractice)
* [ ] Real‑time event ingestion via QStash
* [ ] Parent mobile app (Flutter)
* [ ] SOC 2 Type II & HIPAA BAA
* [ ] YC S25 application 🤞

---

## 🤝 Contributing

Pull requests are welcome! Please file an issue first if you’re making significant changes. We follow the [Conventional Commits](https://www.conventionalcommits.org/) spec and use semantic‑release for automated versioning.

### Local Setup for Contributors

```bash
pnpm i -g vercel prisma typescript
vercel login
prisma db push --force-reset
```

---

## 📝 License

MIT © 2025 CogniQ.ai

---
