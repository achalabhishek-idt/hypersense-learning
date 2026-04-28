# HyperSense Learning Portal — Content Map

> This page shows exactly which sections of the HyperSense User Guide (v2.5.13.7, 1297 pages) map to which role in the learning portal.

---

## Role Overview

| Role | Primary Modules | PDF Pages | Portal Guide |
|---|---|---|---|
| **All Users** | Introduction, Getting Started, UI Basics | 1–19 | `shared/introduction.md`, `shared/getting-started.md` |
| **Analyst** | Data Catalog, BI Studio, Superset, Data Management (Overview) | 20–83, 414–485, 588–687, 688–711 | `analyst/analyst-guide.md` |
| **Admin** | Admin (All), User Management, Audit Trail, Common Settings, App Monitoring, Error Logging, Housekeeping | 84–413 | `admin/admin-guide.md` |
| **Developer** | Data Management Studio, AI Studio, BMS, Process Automation | 486–587, 688–909, 910–1065, 1066–1224 | `developer/developer-guide.md` |
| **Support** | Error Logging, Application Monitoring, Task Search, Audit Trail | 84–113, 141–401 | `support/support-guide.md` |
| **DevOps** | Application Monitoring, Housekeeping, Error Logging, Common Settings, KeyCloak | 84–141, 394–413 | `devops/devops-guide.md` |

---

## Detailed Section-to-Role Mapping

### Shared (All Roles) — Pages 1–19

| Section | Pages | Content |
|---|---|---|
| What's New | 4–5 | Latest feature updates |
| Introduction / About HyperSense | 6–8 | Platform overview, modules, architecture |
| Getting Started / Login | 9–15 | Login, 2FA, AD Integration, KeyCloak |
| User Interface Basics | 16–17 | Navigation, left menu, multi-tasking |
| Abbreviations | 18–19 | Glossary of terms |

---

### Analyst — Pages 20–83, 414–485, 588–687, 688–711

| Section | Pages | Content |
|---|---|---|
| Data Catalog — Overview | 20–21 | What is Data Catalog |
| Data Catalog — Workspace | 22–24 | Navigating the catalog |
| Data Catalog — Features | 25–83 | Search, lineage, metadata |
| BI Studio — Overview | 414 | What is BI Studio |
| BI Studio — Workspace | 414–429 | Navigating BI Studio |
| BI Studio — Features | 430–485 | Reports, charts, dashboards, story designer |
| Superset — BIS Overview | 588–598 | Embedded Superset in BI Studio |
| Superset — Chart Walkthrough | 599–601 | Step-by-step first chart |
| Superset — Exploring Data | 602–610 | Filters, slicing, exploration |
| Superset — Settings | 611–625 | Configuration options |
| Superset — Types of Charts | 626–676 | All 30+ chart types explained |
| Superset — Create Dashboard | 677–684 | Build and publish dashboards |
| Superset — Dashboard Drilling | 685–687 | Interactive drill-through |
| Data Management — Overview | 688–687 | ETL overview for analysts |
| Data Management — Workspace | 688–711 | Pipeline Repository basics |

---

### Admin — Pages 84–413

| Section | Pages | Content |
|---|---|---|
| Application Monitoring (BMS) | 84–97 | Pipeline health dashboard |
| Application Monitoring Superset | 98–109 | Extended monitoring views |
| Audit Trail | 110–113 | User action logs |
| Common Settings | 114–140 | Platform-wide config |
| Error Logging | 141–393 | Error log management |
| Task Search | 394–401 | Search and track tasks |
| User Management | 402–410 | Create/manage users and roles |
| Housekeeping | 411–413 | Storage and log cleanup |

---

### Developer — Pages 486–587, 688–909, 910–1065, 1066–1224

| Section | Pages | Content |
|---|---|---|
| Process Automation — Overview | 486–488 | PAS introduction |
| Workflow Configuration | 487–488 | Creating workflow templates |
| Participating Records Workflow | 489 | PR workflow setup |
| Process Automation — Workspace | 489–587 | Full PAS workspace |
| Data Management — Overview | 688–711 | ETL architecture |
| Data Management — Features | 712–909 | All operators, sources, sinks |
| BMS — Overview | 910 | BMS introduction |
| BMS — Workspace | 911–920 | BMS navigation |
| BMS — Features | 921–1065 | Rules, workflows, integrations |
| AI Studio — Overview | 1066–1067 | AI Studio introduction |
| AI Studio — Workspace | 1068–1071 | Pipeline builder UI |
| AI Studio — Features | 1072–1165 | All AI/ML components |
| AI Studio — Scenarios | 1166–1224 | End-to-end use case walkthroughs |

---

### Support — Pages 84–113, 141–401

| Section | Pages | Content |
|---|---|---|
| Application Monitoring | 84–109 | Health and status dashboard |
| Audit Trail | 110–113 | Track user changes |
| Error Logging | 141–393 | Diagnose failures |
| Task Search | 394–401 | Find and track tasks |

---

### DevOps — Pages 9–15, 84–141, 394–413

| Section | Pages | Content |
|---|---|---|
| KeyCloak Configuration | 12–15 | SSO, 2FA, AD setup |
| Application Monitoring | 84–109 | Infrastructure health |
| Common Settings | 114–140 | Session, timeout, lockout |
| Error Logging (ops view) | 141–393 | Log management |
| Task Search | 394–401 | Ops task tracking |
| Housekeeping | 411–413 | Storage management |

---

## Content Gaps (Needs New Content)

The following topics are needed for a complete learning portal but are **not covered** in the master PDF:

| Topic | Target Audience | Suggested Action |
|---|---|---|
| HyperSense Architecture Diagram | All | Create new diagram + md file |
| Onboarding Checklist | All | Create new md file |
| Role-Based Quick Start (per role) | Each role | Create 5 quick-start md files |
| FAQ / Common Issues | Support | Create FAQ md file |
| Pipeline Troubleshooting Guide | Support, DevOps | Create troubleshooting md file |
| Release Notes Summary | All | Extract from Previous Releases (pages 1228–1255) |
| API Reference | Developer | Create from platform API docs |
| Certification Quizzes | All | Create per-module quizzes |

---

## Suggested Portal Structure (Zensical)

```
docs/
├── shared/
│   ├── introduction.md        ✅ Done
│   └── getting-started.md     ✅ Done
├── analyst/
│   └── analyst-guide.md       ✅ Done
├── admin/
│   └── admin-guide.md         ✅ Done
├── developer/
│   └── developer-guide.md     ✅ Done
├── support/
│   └── support-guide.md       ✅ Done
├── devops/
│   └── devops-guide.md        ✅ Done
└── (coming soon)
    ├── shared/onboarding-checklist.md
    ├── shared/faq.md
    ├── support/troubleshooting.md
    └── developer/api-reference.md
```
