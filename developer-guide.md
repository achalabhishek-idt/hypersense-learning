# HyperSense for Developers

> **Role:** Data Engineer / Developer / Integration Engineer
> **Goal:** Build and configure ETL pipelines, integrate data sources, design AI/ML workflows, and extend the platform.

---

## Your Learning Path

```
Getting Started → Data Management Studio → AI Studio → BMS → Process Automation → Data Catalog (Advanced)
```

---

## Module 1 — Data Management Studio (DMS)

**What it is:** The core ETL/ELT engine of HyperSense. Build pipelines to extract data from sources, transform it, and load it into targets.

### Key Capabilities
- Batch and real-time data ingestion
- Multi-format support: CSV, JSON, XML, ASN, Binary, XLSX, XLS
- Multiple data sources: FTP, SFTP, HDFS, RDBMS, Kafka, S3, GCS, Azure, Hive
- Transformation operators: Parser, Mapper, Flattener, Filter, Aggregator
- Multiple data sinks: RDBMS, HDFS, Kafka, GCS, S3

### ETL Pipeline Build Flow

```
Create Pipeline → Configure Data Source → Add Transformation Operators → Configure Data Sink → Run Pipeline
```

### Step 1 — Create a Pipeline
1. Go to **Data Management → Pipeline Repository**.
2. Click **Create Pipeline**.
3. Enter pipeline name, description, and type (Batch / Streaming).
4. Click **Save**.

### Step 2 — Configure Data Source
1. In the pipeline canvas, drag a **Data Source** operator.
2. Select source type (FTP, SFTP, Kafka, RDBMS, S3, etc.).
3. Enter connection details: Host, Port, Credentials, Directory/Topic.
4. Configure **Post Collection Details** (what to do after data is collected).

### Step 3 — Add Transformation Operators
Common operators:

| Operator | Purpose |
|---|---|
| **ASCII Parser** | Parse ASCII/flat file formats |
| **CSV Parser** | Parse comma-separated files |
| **XLSX Parser** | Parse Excel workbooks |
| **JSON Mapper** | Map and transform JSON data |
| **Flattener** | Flatten XML and JSON nested structures |
| **Mapping** | Map incoming columns to new column names |
| **Filter** | Filter records based on conditions |
| **Aggregator** | Aggregate data (sum, count, avg, etc.) |

### Step 4 — Configure Data Sink
1. Drag a **Data Sink** operator to the canvas.
2. Select sink type (RDBMS, Kafka, HDFS, S3, GCS).
3. Configure connection and target table/path.
4. Set **write mode**: Insert, Upsert, or Overwrite.

### Step 5 — Run and Monitor
1. Click **Run** to execute the pipeline.
2. Monitor status from the **Pipeline Repository** (Running / Success / Failed).
3. Check **Error Logs** for any failures.

### Common Error Scenarios

| Error | Cause | Fix |
|---|---|---|
| UPSERT Failure | Null value in NOT NULL column | Check target schema constraints |
| File Compression Failure | File extension mismatch | Verify source file matches configured compression type |
| Post Collection Failure | Target directory doesn't exist | Create target directory before pipeline run |
| Data Type Mismatch | Schema mismatch in parser | Validate incoming file schema vs. parser config |

> **PDF Reference:** Pages 688–909

---

## Module 2 — AI Studio

**What it is:** End-to-end data science pipeline builder for model training, evaluation, and deployment.

### Key Capabilities
- Data feeding, evaluation, and preparation
- Algorithm training with ML models
- Auto feature engineering and feature store
- Auto Hyper Parameter Tuning
- Model evaluation and explainable AI
- Natural Language Processing (NLP) and Natural Language Querying (NLQ)

### AI Pipeline Components

| Component | Role |
|---|---|
| **Data Reader** | Read data from a source |
| **Data Operation** | Clean and transform data |
| **Statistical Analysis** | Run statistical profiling |
| **Algorithm** | Train ML models |
| **Data Writer** | Store output to a target database |

### Data Preparation Flow
1. **Gather Data** — connect to the right source in the right format
2. **Discover & Access** — profile the data, understand structure
3. **Cleanse & Validate** — remove outliers, handle missing values, mask sensitive data
4. **Transform & Enrich** — reformat and add derived features
5. **Store** — write prepared data to target for analysis

### Types of Analytics Supported
- **Predictive Analytics** — forecast future outcomes
- **Prescriptive Analytics** — recommend actions
- **Descriptive Analytics** — summarize historical data
- **Diagnostic Analytics** — explain why something happened

> **PDF Reference:** Pages 1066–1224

---

## Module 3 — Business Modelling Studio (BMS)

**What it is:** A rule engine for creating complex business logic, chaining rules into workflows, and connecting with pipeline outputs.

### Key Capabilities
- Statistical rules, audit rules, and measure rules
- Rule chaining into workflows
- Integration with DMS pipelines to trigger case generation
- Real-time and batch processing modes

> **PDF Reference:** Pages 910–1065

---

## Module 4 — Process Automation Studio (PAS)

**What it is:** Workflow and case management system for automating business processes.

### Key Capabilities
- Create workflow templates
- Manage cases generated from pipeline outputs
- Configure Participating Records workflows
- Link workflows with BMS for rule-driven automation

> **PDF Reference:** Pages 486–587

---

## Quick Reference — Developer Workflows

| Task | Module | Steps |
|---|---|---|
| Create ETL pipeline | DMS | Pipeline Repository → Create Pipeline |
| Add data source | DMS | Drag Data Source → configure connection |
| Build ML pipeline | AI Studio | Create pipeline → add components |
| Train a model | AI Studio | Add Algorithm operator → configure → run |
| Create a business rule | BMS | BMS Workspace → New Rule |
| Create a workflow | PAS | PAS Workspace → New Workflow |

---

## Developer Tips
- Use **Record Sequence** in parser operators (ASCII, CSV, XLSX) to validate file ordering integrity.
- Use **Create Date Format** in ASCII Parser for custom date-time parsing.
- In the **Mapping operator**, use the Search bar to filter incoming and outgoing columns when dealing with large schemas.
- Use **Pagination** in the Mapping operator for easier navigation in large field-mapping configurations.
