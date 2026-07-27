# 🌐 MetaFetch API — Atelier Busco Utility Suite

[![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white)](https://github.com/Atelier-Busco)
[![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://github.com/Atelier-Busco)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

MetaFetch is a lightweight, high-speed REST API built with **NestJS** to extract metadata (OpenGraph, Twitter Cards, favicons, canonicals) from any public URL. Includes an advanced `/metascore` evaluation engine for instant SEO & social card audits.

---

## 🚀 Endpoints & Usage

### 1. `GET /metafetch?url=https://example.com`
Returns parsed Open Graph and Twitter Card tags.

```json
{
  "title": "Example Domain",
  "meta": {
    "description": "This domain is for use in illustrative examples.",
    "og:title": "Example Domain",
    "og:description": "An example site",
    "twitter:card": "summary",
    "twitter:title": "Example Domain"
  },
  "favicon": "https://example.com/favicon.ico",
  "canonical": "https://example.com"
}
```

### 2. `GET /metascore?url=https://example.com`
Evaluates metadata completeness and yields actionable improvement recommendations.

```json
{
  "url": "https://example.com",
  "score": 72,
  "present": [
    "title",
    "meta.description",
    "og:title",
    "og:description"
  ],
  "missing": [
    "meta.keywords",
    "og:image",
    "twitter:card"
  ],
  "recommendations": [
    "Add a Twitter Card to improve link sharing.",
    "Include an OpenGraph image for better previews."
  ]
}
```

---

## 🛠️ Tech Stack & Dependencies

- **Framework:** NestJS
- **Parser:** Cheerio
- **HTTP Client:** Axios
- **Validation:** Zod / class-validator

---

## 📦 Installation & Local Setup

```bash
git clone https://github.com/Atelier-Busco/metafetch-api.git
cd metafetch-api
npm install
npm run start:dev
```

---

> Part of the **Atelier Busco Micro-Services & Utility Suite**.  
> Engineered by **[Atelier Busco](https://github.com/Atelier-Busco)** — *Strategic technical partner for founders and innovation leaders.*