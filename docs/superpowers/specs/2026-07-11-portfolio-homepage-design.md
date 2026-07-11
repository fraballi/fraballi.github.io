# Portfolio Homepage Design

Date: 2026-07-11

## Purpose

GitHub Pages user site (`fraballi.github.io`) as a job-hunting portfolio for Félix Aballí, Software Technical Lead. Currently a one-line stub `index.html`.

## Approach

Plain HTML/CSS/JS, no build step, no framework, no dependencies. Chosen over Jekyll/Hugo/React for lowest ongoing maintenance: no toolchain to keep updated, no build pipeline, GitHub Pages serves the repo root as-is.

## Files

```
index.html
css/style.css
js/main.js
assets/resume.pdf
```

`main.js` only handles: mobile nav toggle, smooth scroll to anchors. No other JS behavior.

## Deployment

Push to `main` (already renamed from `master`, confirmed as GitHub default branch). GitHub Pages auto-publishes root of `main`. No Actions workflow needed.

## Page structure

Single page, anchor-nav sections: `#about`, `#skills`, `#experience`, `#projects`, `#contact`.

### 1. Hero / header
- Name: Félix Aballí
- Title: Software Technical Lead
- Short tagline (from resume About Me, condensed to one line)
- Nav links to each section
- "Download Resume" button → `assets/resume.pdf`

### 2. About
Condensed version of resume's "About Me" paragraph: 15+ years backend systems for FinTech/Payments/Banking-as-a-Service across LATAM/EMEA/APAC; currently leading backend architecture at Eron International for PandaBlue; deep expertise Java/Kotlin + Spring Boot on AWS/Kubernetes; background in Neuro-Engineering/Bioinformatics.

### 3. Skills
Grouped tag lists, derived from resume tech stacks across all roles:
- **Backend:** Java, Kotlin, Spring Boot, J2EE, EJB, Netty
- **Cloud/DevOps:** AWS, Azure, Kubernetes, Docker, ArgoCD, Helm
- **Frontend:** React, TypeScript, Angular, AngularJS
- **Data:** MySQL, PostgreSQL, Redis, Kafka, Hadoop, Spark, Elasticsearch
- **Testing:** JUnit, Mockito, AssertJ, WireMock, TestContainers
- **Observability:** Grafana, Prometheus, New Relic, Datadog, Kibana

### 4. Experience
All 9 roles from resume, reverse-chronological. Each entry: company, title, dates, bullet achievements, tech tag list. Top 2-3 roles (Eron International, MercadoLibre, Technisys) expanded by default; older roles collapsed behind `<details>`/`<summary>` to avoid an overwhelming wall of text while keeping full content on-page (no separate PDF-only content).

Roles, in order:
1. Eron International S.A — Software Technical Lead (2024–current)
2. MercadoLibre S.A — Software Technical Lead (2022–2024)
3. Technisys S.A — Software Technical Lead (2022)
4. Samqua S.A — Senior Software Engineer (2021–2022)
5. Verifone S.A — Senior Software Design Engineer / Edge Guild Lead (2020–2021)
6. US General Software Inc — Software Technical Lead / Data Engineer (2018–2019)
7. Apollo Systems .Gmbh (TISSCA) — Senior Full-Stack Software Engineer (2017–2018)
8. Carricay Group — Senior Full-Stack Software Engineer / Business Architect (2016–2017)
9. Cuban Center for Neurosciences — Head of Telematics / Software Technical Lead (2009–2017)

### 5. Projects
7 GitHub repo cards, name + description (pulled from GitHub API) + link to repo:
1. `play-spring-kotlin-kafka` — Spring with Kotlin and Kafka Use Cases
2. `wallet` — Money Conversion with Javalin Framework Demo
3. `thorntail-microservices-multiple-profiles` — Application with Thorntail/Undertow Microservices Multiple Profiles in Docker
4. `challenge` — Java Game Console Application
5. `hadoop-install-guide` — Hadoop Install Guide (fork)
6. `hive-install-guide` — Hive Install Guide (fork)
7. `kafka-install-guide` — (fork, no description on GitHub)

### 6. Contact / footer
Email (felixaballi@gmail.com), LinkedIn (https://www.linkedin.com/in/felix-roberto-aballi-morell-01), GitHub (https://github.com/fraballi) as icon/text links. No contact form (avoids third-party form backend dependency).

## Visual style

Dark theme, red accent color (matches resume branding), system sans-serif font stack (no external font request — keeps page dependency-free and fast). Responsive via CSS flexbox/grid with one mobile breakpoint. No light/dark toggle — dark only.

## Out of scope

- No CMS, no JSON data files — content is hardcoded directly in HTML; edits are direct HTML edits
- No contact form / backend
- No build tooling, no JS framework, no analytics
- No blog or additional pages beyond the single homepage

## Testing / verification

Manual: open in browser, verify responsive layout at mobile/desktop widths, verify all links (repo links, LinkedIn, email, resume PDF) resolve, verify collapsed experience entries expand correctly.
