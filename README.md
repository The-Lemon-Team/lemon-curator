# 🍋 Lemon Curator — AI Multi-Agent Editorial & Knowledge Synthesis Platform

**Lemon Curator** is the intelligence and curation engine of the Lemon ecosystem. It unites multi-agent AI workflows, specialized editorial curators, breaking news ingestion, resonance scoring, and cross-analysis synthesis to turn rapid information streams into high-density structured knowledge.

Repository: [git@github.com:The-Lemon-Team/lemon-curator.git](https://github.com/The-Lemon-Team/lemon-curator)

---

## 🎯 Core Mission & Vision

1. **Curator Personas & Domain Specialization**:
   - Individual AI curators act as dedicated domain experts (e.g. domestic analysis, international geopolitics, economic trends, culture/science).
   - Notes are tagged with `curator` and `persona` metadata to establish perspective and voice.
2. **Multi-Agent Collaboration & Cross-Analysis**:
   - Curators debate and contrast viewpoints across events and breaking news.
   - Cross-analysis calculates a mathematical **Resonance Score (0–100%)** representing conceptual overlap and conflict between distinct contours.
3. **Breaking News Ingestion & Synthesis (`DONE` Notes)**:
   - High-resonance note clusters are synthesized into unified `DONE` notes (Case-Based Memory) with full citations and action items.
4. **Public & Collaborative Hub**:
   - Serves as the public-facing knowledge base where curated streams, live feeds, and AI synthesis are published and shared.

---

## 🏛️ Architecture Overview

```
                      ┌────────────────────────┐
                      │  Breaking News Feeds   │
                      │  (RSS / Webhooks / API)│
                      └───────────┬────────────┘
                                  ▼
                      ┌────────────────────────┐
                      │    Ingestion Engine    │
                      └───────────┬────────────┘
                                  ▼
           ┌──────────────────────┴──────────────────────┐
           ▼                                             ▼
  🇷🇺 Ivan Bely (Internal)                      🌐 Kirk Kitten (Global)
  - Domestic policy & energy                    - Sanctions & foreign trade
  - Local market trends                         - Geopolitical ripple effects
           │                                             │
           └──────────────────────┬──────────────────────┘
                                  ▼
                      ┌────────────────────────┐
                      │ Cross-Analysis & Math  │
                      │ Resonance Scoring (0-100)
                      └───────────┬────────────┘
                                  ▼
                      ┌────────────────────────┐
                      │ Synthesis: DONE Note   │
                      │ (Obsidian + DB Store)  │
                      └────────────────────────┘
```

---

## 📦 Monorepo Packages & Applications

- **`apps/backend`**: Nest.js 10 backend with PostgreSQL (`ltree`), Prisma ORM, Political & Holiday Ingestion engines, AI parser, and resonance calculation services.
- **`apps/calendar-app`**: React 18 + Vite chronological timeline and calendar app featuring Curator Lens filtering, resonance indicators, and synthesis workflows.
- **`apps/admin-cms`**: React + Ant Design CMS for managing feeds, taxonomy paths, curation personas, and system telemetry.
- **`packages/shared`**: Universal TypeScript schemas, curator constants, frontmatter utilities, and DTOs.
- **`packages/obsidian-plugin`**: Svelte 4 Obsidian sync plugin that reads/writes curator frontmatter (`curator`, `persona`, `resonance_score`, `assistants`) and maintains container vault synchronicity.

---

## 🚀 Quick Start

### 1. Prerequisites
- Node.js >= 20
- pnpm >= 9
- Docker & Docker Compose

### 2. Start PostgreSQL Database
```bash
pnpm run db:up
```

### 3. Install Dependencies & Build
```bash
pnpm install
pnpm run build
```

### 4. Database Migration & Seed
```bash
pnpm run backend:prisma:migrate
pnpm run backend:prisma:seed
```

### 5. Start Development Servers
```bash
pnpm run dev
# or start core apps concurrently:
pnpm run dev:local
```

- **Calendar & Curator App**: [http://localhost:5173](http://localhost:5173)
- **Admin CMS**: [http://localhost:5174](http://localhost:5174)
- **Backend API & Swagger**: [http://localhost:3001/api/docs](http://localhost:3001/api/docs)

---

## 📖 Deep Dives & Specifications

- [Concept: AI Assistants & Cross Analysis Specification](docs/CONCEPT_ASSISTANTS_AND_CROSS_ANALYSIS.md)
- [Intermediate Architecture & State Document](INTERMEDIATE_DOCUMENT_GEMINI.md)
