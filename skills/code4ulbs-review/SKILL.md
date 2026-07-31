---
name: code4ulbs-review
description: Use when reviewing a Code4ULBS repository for compliance with the project standards defined in code4ulbs-starter/README.md. Runs through all mandatory requirements, code quality, testing, security, deployment, and organizational rules.
version: 1.0.0
author: Code4ULBS
license: MIT
metadata:
  hermes:
    tags: [code4ulbs, ulbs, review, compliance, quality, university, sibiu]
    related_skills: [ulbs-brand]
---

# Code4ULBS Repository Review

## Overview

Review a Code4ULBS repository against the mandatory requirements defined in [`code4ulbs-starter/README.md`](https://github.com/code4ulbs/code4ulbs-starter). This skill produces a structured compliance report with pass/fail per section and an overall readiness verdict.

**Reference documents:**
- [code4ulbs-starter README](https://github.com/code4ulbs/code4ulbs-starter)
- [`ulbs-brand/SKILL.md`](../ulbs-brand/SKILL.md) — ULBS brand guidelines

## When to Use

- Reviewing a new project before declaring it production-ready
- Auditing an existing project for compliance gaps
- Onboarding a project into the Code4ULBS organization
- Pre-merge review of a PR that adds significant infrastructure (CI/CD, Docker, auth)
- Periodic quality audits of active projects

**Do NOT use for:** reviewing individual code changes (use normal PR review), projects outside the Code4ULBS organization.

## Review Procedure

For each section below, inspect the repository (local clone or GitHub) and mark each item as **✅ Pass**, **❌ Fail**, or **⚠️ Partial**. Collect evidence for every fail/partial status.

---

## 1. 🎯 Core Requirements

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 1.1 | **Linting configured** | Check for linter config file (`.eslintrc*`, `.pylintrc`, `checkstyle.xml`, `.golangci.yml`, etc.) | `⬜` |
| 1.2 | **Protected main branch** | Check GitHub Settings > Branches — rule exists, requires PR, requires approvals | `⬜` |
| 1.3 | **AI Agent Instructions** | Check `copilot-instructions.md` or `.github/copilot-instructions.md` exists and is populated | `⬜` |
| 1.4 | **Containerization support** | Check `Dockerfile` and `compose.yaml` or `docker-compose.yml` exist | `⬜` |
| 1.5 | **CI/CD pipelines** | Check `.github/workflows/` has at least one workflow (lint → test → build → deploy) | `⬜` |
| 1.6 | **E2E tests** | Check E2E test files exist (Playwright, Cypress, Selenium) | `⬜` |
| 1.7 | **Unit tests** | Check test dir/file exists (`__tests__/`, `*.test.*`, `*.spec.*`, `src/test/`) | `⬜` |
| 1.8 | **Environment separation** | Check for staging + production references (`.env.development`, `.env.production`, or infra scripts) | `⬜` |
| 1.9 | **IDE setup docs** | Check `.vscode/` or IDE-specific docs exist | `⬜` |
| 1.10 | **Design system compliance** | Check repo references ULBS design system (Figma link, brand colors, typography) | `⬜` |
| 1.11 | **Google Authentication** | Check auth uses Google OAuth/OIDC, no local password storage | `⬜` |
| 1.12 | **Database auditing** | Check audit trail framework configured (Hibernate Envers, django-simple-history, etc.) | `⬜` |

---

## 2. 🔍 Code Quality & Analysis

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 2.1 | **Linter config committed** | Linter config file is in version control | `⬜` |
| 2.2 | **Pre-commit hooks** | Check `.husky/`, `.pre-commit-config.yaml`, or `lint-staged` config | `⬜` |
| 2.3 | **CI/CD fails on lint errors** | Check workflow has a `lint` job that fails on errors | `⬜` |
| 2.4 | **Security scanning** | Check for CodeQL, Snyk, or similar integrated | `⬜` |
| 2.5 | **Dependency vulnerability checks** | Check Dependabot or similar enabled | `⬜` |
| 2.6 | **Type checking** | For typed languages: check `tsconfig.json`, `pyright`, `mypy`, etc. | `⬜` |

---

## 3. 🔐 Version Control & Collaboration

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 3.1 | **PRs required before merging** | GitHub branch protection rule checked | `⬜` |
| 3.2 | **≥1 approval required** | Branch protection rule checked | `⬜` |
| 3.3 | **Stale approvals dismissed** | Branch protection rule checked | `⬜` |
| 3.4 | **Status checks required** | Branch protection — lint, test, build jobs selected | `⬜` |
| 3.5 | **Branches must be up-to-date** | Branch protection rule checked | `⬜` |
| 3.6 | **No direct commits to main** | Branch protection rule checked | `⬜` |

---

## 4. 🧪 Testing Requirements

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 4.1 | **Unit test coverage ≥80%** | Run coverage report (`npm run test:coverage`, `pytest --cov`, etc.) | `⬜` |
| 4.2 | **Tests run before commit** | Pre-commit hook runs tests | `⬜` |
| 4.3 | **Fast execution (<5 min)** | Check CI test job duration | `⬜` |
| 4.4 | **Isolated tests** | No external dependencies in unit tests (mocks used) | `⬜` |
| 4.5 | **Clear test naming** | Test names describe what they test | `⬜` |
| 4.6 | **E2E tests implemented** | E2E test files exist and cover critical user journeys | `⬜` |
| 4.7 | **E2E runs daily via scheduled workflow** | Check `.github/workflows/` for scheduled E2E workflow | `⬜` |
| 4.8 | **E2E runs against staging** | E2E test URL points to staging environment | `⬜` |

---

## 5. 🚀 Deployment & Environments

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 5.1 | **Staging environment exists** | Check `ENVIRONMENT.md` or infra config for staging URL | `⬜` |
| 5.2 | **Production environment exists** | Check for production URL/configuration | `⬜` |
| 5.3 | **CI/CD deploy jobs configured** | Workflow has `deploy-staging` and `deploy-production` jobs | `⬜` |
| 5.4 | **Uses ULBS organization runners** | Workflow `runs-on` uses `[self-hosted, build-01]` or similar, not `ubuntu-latest` | `⬜` |

---

## 6. 🐳 Infrastructure

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 6.1 | **Dockerfile exists** | Check `Dockerfile` at repo root | `⬜` |
| 6.2 | **Compose file exists** | Check `compose.yaml` or `docker-compose.yml` | `⬜` |
| 6.3 | **Podman compatible** | Compose file works with Podman (no Docker-exclusive features) | `⬜` |

---

## 7. 🗄️ Database Management

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 7.1 | **Automated backups** | Check for backup scripts, cron jobs, or backup service config | `⬜` |
| 7.2 | **Audit system implemented** | Check for audit framework config (see table below) | `⬜` |
| 7.3 | **Recovery strategy defined** | Check docs for point-in-time recovery or backup restore process | `⬜` |

### Recommended Audit Frameworks

| Stack | Tool |
|---|---|
| Java / Spring Boot | Hibernate Envers |
| Node.js (TypeORM) | typeorm-extension or Custom Subscribers |
| Python (Django) | django-simple-history |
| Python (SQLAlchemy) | SQLAlchemy-Continuum |
| Go | Custom middleware or DB-level triggers (GORM hooks) |

---

## 8. 🔒 Security & Authentication

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 8.1 | **Google Auth only** | Auth provider is Google (OAuth/OIDC), no local login | `⬜` |
| 8.2 | **No local passwords stored** | No password hashing, no `password` column in user models | `⬜` |
| 8.3 | **OAuth2 / OIDC compliance** | Standard protocol used, not custom auth | `⬜` |
| 8.4 | **Dependabot enabled** | Check GitHub Settings > Code security > Dependabot, or `.github/dependabot.yml` | `⬜` |
| 8.5 | **Secrets not committed** | Check `.gitignore` includes `.env`, no hardcoded keys in source | `⬜` |
| 8.6 | **`.env.example` exists** | Documents required environment variables without real values | `⬜` |

---

## 9. 💻 Developer Experience

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 9.1 | **VS Code settings** | Check `.vscode/settings.json` exists | `⬜` |
| 9.2 | **VS Code extensions** | Check `.vscode/extensions.json` with recommendations | `⬜` |
| 9.3 | **IDE setup documented** | README or separate docs cover IDE setup steps | `⬜` |
| 9.4 | **Local run instructions** | README documents how to start the project locally | `⬜` |
| 9.5 | **Debugging instructions** | README or docs cover debugging (frontend + backend) | `⬜` |

---

## 10. 🎨 Design & Brand

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 10.1 | **ULBS color palette used** | Check CSS/design tokens use ULBS brand colors (`#0B2F63` primary) | `⬜` |
| 10.2 | **Typography follows ULBS system** | Fonts match ULBS guidelines (Open Sans, proper sizes) | `⬜` |
| 10.3 | **Responsive design (mobile-first)** | Check CSS media queries, viewport meta, responsive components | `⬜` |
| 10.4 | **Accessibility WCAG 2.1 AA** | Check for alt texts, ARIA labels, contrast ratios, keyboard navigation | `⬜` |
| 10.5 | **ULBS logo used correctly** | Logo variant matches background (positive/negative), proportional scaling | `⬜` |

---

## 11. 🏢 Organization

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 11.1 | **Dedicated GitHub Team exists** | Check GitHub organization for project team | `⬜` |
| 11.2 | **Repo linked to team** | Check repo access — team has access, not individuals | `⬜` |
| 11.3 | **GitHub Project board active** | Check Projects tab for active board with To Do / In Progress / QA / Done | `⬜` |
| 11.4 | **Issue templates exist** | Check `.github/ISSUE_TEMPLATE/` or organization defaults | `⬜` |

---

## 12. 📝 Issue-Driven Development

| # | Requirement | How to Verify | Status |
|---|-------------|---------------|--------|
| 12.1 | **Issues linked to project board** | Check issues are assigned to a GitHub Project | `⬜` |
| 12.2 | **Issues assigned to developer** | Check issues have assignees | `⬜` |
| 12.3 | **PRs link to issues** | Check recent PRs: description includes `fixes #` or `closes #` | `⬜` |
| 12.4 | **PR descriptions follow format** | Check PR has title, description, related issue, testing notes | `⬜` |
| 12.5 | **Conventional commit format** | PR titles follow conventional commits (`feat:`, `fix:`, `chore:`, etc.) | `⬜` |

---

## 13. ✅ Final Verdict

| Category | Pass | Fail | Partial | Score |
|---|---|---|---|---|
| Core Requirements | ⬜ | ⬜ | ⬜ | __/12 |
| Code Quality | ⬜ | ⬜ | ⬜ | __/6 |
| Version Control | ⬜ | ⬜ | ⬜ | __/6 |
| Testing | ⬜ | ⬜ | ⬜ | __/8 |
| Deployment | ⬜ | ⬜ | ⬜ | __/4 |
| Infrastructure | ⬜ | ⬜ | ⬜ | __/3 |
| Database | ⬜ | ⬜ | ⬜ | __/3 |
| Security | ⬜ | ⬜ | ⬜ | __/6 |
| Developer Experience | ⬜ | ⬜ | ⬜ | __/5 |
| Design & Brand | ⬜ | ⬜ | ⬜ | __/5 |
| Organization | ⬜ | ⬜ | ⬜ | __/4 |
| Issue-Driven Dev | ⬜ | ⬜ | ⬜ | __/5 |
| **TOTAL** | ⬜ | ⬜ | ⬜ | **__/67** |

### Readiness Thresholds

| Score | Verdict | Action |
|---|---|---|
| **≥90% (≥60/67)** | ✅ **Production-ready** | All good |
| **70–89% (47–59/67)** | ⚠️ **Needs work** | Fix fails before deploying to production |
| **<70% (<47/67)** | ❌ **Not ready** | Project should not be in production; major gaps |

## Common Pitfalls

1. **Skipping infrastructure checks** — CI/CD pipeline exists but doesn't actually enforce status checks in branch protection. Always verify both.
2. **Confusing "has tests" with "≥80% coverage"** — Check coverage numbers, not just test file existence.
3. **Missing ULBS runner configuration** — Default GitHub runners (`ubuntu-latest`) are explicitly forbidden.
4. **Dependabot in repo settings vs `.github/dependabot.yml`** — Both count, but the repo-level setting is what matters for automatic security updates.
5. **Design tokens mismatched** — Many projects define their own colors instead of using ULBS brand palette. Cross-check with `ulbs-brand/SKILL.md`.
6. **E2E workflow exists but never runs** — Scheduled workflow must be on `main` branch and have `schedule` trigger, not just `workflow_dispatch`.
7. **Project board exists but is empty** — Active means issues are being tracked through the lifecycle, not just created.

## Verification Checklist

- [ ] Repository cloned and inspected locally
- [ ] GitHub Settings reviewed (branch protection, Dependabot, teams)
- [ ] CI/CD workflows inspected
- [ ] Test coverage numbers verified (not just file existence)
- [ ] Brand compliance cross-checked with `ulbs-brand/SKILL.md`
- [ ] Auth mechanism confirmed (Google OAuth, no local passwords)
- [ ] Secrets checked — no credentials in source code
- [ ] Docker/Podman build tested locally
- [ ] E2E workflow trigger confirmed (scheduled)
- [ ] Project board has active issues with correct statuses
- [ ] Final verdict calculated with score and readiness assessment
