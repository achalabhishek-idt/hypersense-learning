# HyperSense for Analysts

> **Role:** Business Analyst / Data Analyst
> **Goal:** Explore data, build dashboards, generate reports, and derive business insights.

---

## Your Learning Path

```
Getting Started → Data Catalog → BI Studio → Superset → Data Management (Basics)
```

---

## Module 1 — Data Catalog

**What it is:** A centralized repository for discovering, understanding, and searching your organization's data assets.

### Key Capabilities
- Search and browse all available datasets
- Understand data lineage — where data comes from and how it flows
- View metadata, tags, and data quality indicators
- Access data from a unified, searchable catalog

### Where to Start
1. From the left nav, click **Data Catalog**.
2. Use the **Search** bar to find datasets by name, tag, or type.
3. Click any dataset to view its **metadata, lineage, and schema**.

> **PDF Reference:** Pages 20–83

---

## Module 2 — BI Studio (Business Intelligence)

**What it is:** HyperSense's data visualization tool for building reports, charts, and dashboards.

### Key Capabilities
- Create and publish **dashboards and reports**
- Slice and dice data with filters and context drill-downs
- In-memory caching via **OLAP cubes and Data Marts** for fast reporting
- **Business Story Designer** for narrative-driven insights

### Where to Start
1. From the left nav, click **BI Studio**.
2. Go to **Workspace** to see existing reports and dashboards.
3. Click **Create Dashboard** to start a new visualization.

> **PDF Reference:** Pages 414–485

---

## Module 3 — Superset (Advanced BI)

**What it is:** An advanced charting and dashboard platform embedded within BI Studio.

### Key Capabilities
- 30+ chart types (bar, line, pie, heatmap, scatter, sankey, etc.)
- Interactive dashboard exploration and drilling
- Data filtering, slicing, and cross-chart interactions
- Dashboard sharing and exporting

### Creating Your First Dashboard
1. Navigate to **BI Studio → Superset**.
2. Go to **Charts** → click **+ Chart**.
3. Select a **Dataset** and choose a **Chart Type**.
4. Configure dimensions, metrics, and filters.
5. Click **Save** and add to a **Dashboard**.

> **PDF Reference:** Pages 588–687

---

## Module 4 — Data Management (Analyst View)

**What it is:** As an analyst, you primarily consume data prepared by the Data Engineering team. Understanding pipeline outputs helps you work with data effectively.

### What Analysts Need to Know
- How data flows from source → transformation → sink
- Understanding data formats: CSV, JSON, XML, XLSX
- Locating your datasets in the **Pipeline Repository**

> **PDF Reference:** Pages 688–711 (Overview and Workspace)

---

## Quick Reference — Analyst Workflows

| Task | Module | Steps |
|---|---|---|
| Find a dataset | Data Catalog | Search → browse metadata |
| Build a chart | BI Studio / Superset | Create Chart → configure → save |
| Create a dashboard | BI Studio / Superset | Add charts → layout → publish |
| Drill into data | Superset | Click chart data point → drill |
| Export a report | BI Studio | Dashboard → Export |

---

## Tips for Analysts
- Use **Data Catalog** before building reports — it saves time locating the right dataset.
- Use **OLAP caching** in BI Studio for large datasets to speed up dashboard loading.
- In Superset, use **Dashboard Drilling** to create interactive, multi-level reports.
