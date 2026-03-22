# prismatest-
Multilingual self-discovery platform — 20 languages, 50+ assessments, 1.4M lines of code

<h1 align="center">PrismaTest — Multilingual Self-Discovery Platform</h1>

<p align="center">
  <strong>1,400,000+ lines of code · 20 languages · 50+ assessments · Open infrastructure</strong>
</p>

<p align="center">
  <a href="https://prismatest.com">🌐 Live Platform</a> ·
  <a href="https://prismatest.com/en">English</a> ·
  <a href="https://prismatest.com/ru">Русский</a> ·
  <a href="https://prismatest.com/es">Español</a> ·
  <a href="https://prismatest.com/de">Deutsch</a> ·
  <a href="https://prismatest.com/ja">日本語</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Next.js-14+-black?logo=next.js" alt="Next.js" />
  <img src="https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript" alt="TypeScript" />
  <img src="https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Redis-7-DC382D?logo=redis" alt="Redis" />
  <img src="https://img.shields.io/badge/Docker-Ready-2496ED?logo=docker" alt="Docker" />
  <img src="https://img.shields.io/badge/Languages-20-green" alt="20 Languages" />
</p>

---

## About

[**PrismaTest**](https://prismatest.com) is a full-scale multilingual platform designed for personality exploration and self-assessment. Born from a personal passion for psychology and behavioral science, the project evolved into a comprehensive product serving thousands of daily users across 20 languages.

The idea came from a simple frustration: most existing platforms are English-only, cluttered with ads, lack scientific rigor, or lock results behind paywalls. I wanted to build something better — a clean, research-backed, and truly global tool that anyone could use for free, in their native language.

## The Journey

### Research Phase

The development started long before writing the first line of code. Months were spent studying peer-reviewed publications, clinical assessment manuals, and psychometric literature:

- **Personality models**: Five-Factor Model (Costa & McCrae), Cattell's 16PF, Jung's typology, socionics frameworks
- **Emotional intelligence**: Goleman's EI model, Bar-On EQ-i, Hall's methodology
- **Clinical instruments**: Beck Depression Inventory (BDI-II), State-Trait Anxiety scales, anger assessment inventories (STAXI-2, MAI, BPAQ)
- **Relationship psychology**: Attachment theory (Bowlby, Ainsworth), Sternberg's triangular theory, Chapman's Love Languages framework
- **Vocational psychology**: Holland's RIASEC model, Belbin team roles
- **Cognitive assessment**: Raven's Progressive Matrices, spatial reasoning paradigms, change detection methodology

Each assessment on [PrismaTest](https://prismatest.com) is built on validated scientific instruments, with careful attention to scoring algorithms, normative data, and interpretation guidelines drawn from the original research.

### Architecture & Design

After the research phase, I spent weeks designing the system architecture — drawing entity diagrams, planning data flows, prototyping scoring algorithms on paper, and mapping out how 20 different languages with different scripts (Latin, Cyrillic, CJK, Arabic RTL, Devanagari, Thai, Bengali) would coexist in a single coherent system.

Key architectural decisions:
- **Content-as-code**: All assessment data lives in structured JSON files — translations, questions, scoring rules, results, and SEO metadata packed together. Adding a new assessment means creating a single file
- **Universal scoring engine**: 7 scoring algorithms (Likert scales, Likert levels, dichotomy, forced-choice, color-sequence, formula, custom) handle every possible assessment type
- **Universal display system**: 6 visualization types (bar charts, type cards, level indicators, radar diagrams, percentage bars, color analysis) render any result format

## Tech Stack

| Layer | Technologies |
|-------|-------------|
| **Frontend** | Next.js 14+ (App Router), TypeScript, Tailwind CSS, Framer Motion, Recharts |
| **Backend** | Next.js API Routes, NextAuth.js, Prisma ORM |
| **Database** | PostgreSQL 16, Redis 7 (caching, rate limiting, sessions) |
| **i18n** | next-intl — 20 locales with ICU MessageFormat pluralization |
| **Infrastructure** | Docker, Docker Compose, Traefik (reverse proxy + auto SSL) |
| **Monitoring** | Google Analytics, Yandex Metrica, structured logging |

### Supported Languages

<table>
<tr>
<td>🇷🇺 Russian</td><td>🇺🇸 English</td><td>🇪🇸 Spanish</td><td>🇩🇪 German</td><td>🇫🇷 French</td>
</tr>
<tr>
<td>🇧🇷 Portuguese</td><td>🇮🇹 Italian</td><td>🇵🇱 Polish</td><td>🇺🇦 Ukrainian</td><td>🇹🇷 Turkish</td>
</tr>
<tr>
<td>🇳🇱 Dutch</td><td>🇷🇴 Romanian</td><td>🇮🇩 Indonesian</td><td>🇻🇳 Vietnamese</td><td>🇹🇭 Thai</td>
</tr>
<tr>
<td>🇯🇵 Japanese</td><td>🇰🇷 Korean</td><td>🇮🇳 Hindi</td><td>🇧🇩 Bengali</td><td>🇸🇦 Arabic (RTL)</td>
</tr>
</table>

Each language includes full localization: UI elements, assessment content, scoring interpretations, result descriptions, SEO metadata, and culturally adapted recommendations.

## Project Scale

| Metric | Value |
|--------|-------|
| **Total codebase** | 1,428,177 lines |
| **Files** | 432 |
| **React components (TSX)** | 162 files · 36,000+ lines |
| **Business logic (TypeScript)** | 111 files · 14,000+ lines |
| **Structured content (JSON)** | 129 files · 1,360,000+ lines |
| **Database schemas** | PostgreSQL + Prisma ORM |
| **Languages supported** | 20 |
| **Scoring algorithms** | 7 universal types |
| **Display renderers** | 6 visualization types |

## Key Features

- 🧠 **Science-backed assessments** — built on peer-reviewed instruments and validated psychometric methods
- 🌍 **True multilingual** — not machine-translated; each locale reviewed for accuracy and cultural context
- 📊 **Rich visualizations** — radar charts, animated counters, color-coded scales, SVG-based custom displays
- 🔒 **Privacy-first** — GDPR-compliant, cookie consent, minimal data collection
- ⚡ **Performance** — server-side rendering, Redis caching, optimized Core Web Vitals
- 📱 **Mobile-first** — responsive design across all breakpoints
- ♿ **Accessible** — semantic HTML, ARIA attributes, keyboard navigation, screen reader support
- 🔍 **SEO-optimized** — dynamic metadata, Schema.org markup (Quiz, FAQPage, WebSite), automated sitemaps, hreflang tags for all 20 locales

## Architecture Overview

```
┌─────────────────────────────────────────────────────┐
│                     Client Layer                     │
│   Next.js App Router · React Server Components       │
│   Tailwind CSS · Framer Motion · Recharts            │
└───────────────────────┬─────────────────────────────┘
                        │
┌───────────────────────┴─────────────────────────────┐
│                    Server Layer                       │
│   API Routes · NextAuth.js · Prisma ORM              │
│   Universal Scoring Engine · Content Loader           │
└──────────┬────────────────────────────┬──────────────┘
           │                            │
┌──────────┴──────────┐   ┌────────────┴──────────────┐
│   PostgreSQL 16     │   │        Redis 7             │
│   Users · Results   │   │   Cache · Sessions · Rate  │
│   Settings · Stats  │   │        Limiting            │
└─────────────────────┘   └───────────────────────────┘
           │
┌──────────┴──────────────────────────────────────────┐
│                   Infrastructure                     │
│   Docker · Traefik · Let's Encrypt SSL · VPS         │
└─────────────────────────────────────────────────────┘
```

## Development Philosophy

This project follows several core principles:

1. **Content as data** — assessments are data files, not code. Non-developers can review and update content
2. **Universal over specific** — one scoring engine, one display system, one test flow — for any assessment type
3. **Localization is not an afterthought** — i18n is baked into every layer, from URL structure to meta tags to pluralization rules
4. **Performance at scale** — designed for 50K+ daily active users with caching, lazy loading, and optimized bundles
5. **Zero paywalls** — all assessments are free, forever

## Try It

Visit [**prismatest.com**](https://prismatest.com) to explore the platform. Available in 20 languages — the interface automatically adapts to your browser locale, or you can switch manually.

Popular starting points:
- [Personality assessments](https://prismatest.com/en/tests?category=personality) — understand your traits and tendencies
- [Emotional intelligence](https://prismatest.com/en/tests?category=emotional) — explore your EQ profile
- [Cognitive assessments](https://prismatest.com/en/tests?category=erudition) — challenge your reasoning abilities

## License

This repository contains the source code for [PrismaTest](https://prismatest.com). All rights reserved.

---

<p align="center">
  Built with ❤️ and a lot of ☕ by <a href="https://github.com/alexgor26">@alexgor26</a>
</p>
