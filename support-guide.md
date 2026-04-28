# HyperSense for Support Engineers

> **Role:** L1 / L2 / L3 Support Engineer
> **Goal:** Diagnose issues, monitor pipeline health, handle user queries, and resolve errors quickly.

---

## Your Learning Path

```
Getting Started → Error Logging → Application Monitoring → Task Search → Audit Trail → Common Settings (Read-only)
```

---

## Module 1 — Error Logging

**What it is:** Your first stop for diagnosing any platform issue. Centralized error log viewer for all studios and pipelines.

### What You'll Find Here
- Pipeline execution errors with timestamps
- Data parsing and transformation failures
- System-level exceptions
- Studio-specific error events

### How to Use
1. From the left nav, go to **Admin → Error Logging**.
2. Filter logs by:
   - **Studio** (DMS, BIS, BMS, PAS, AI Studio)
   - **Date/Time range**
   - **Error type or severity**
3. Click any error entry to see the **full stack trace**.
4. Download logs for escalation to L3 or development team.

### Common Errors and What They Mean

| Error | Module | Likely Cause |
|---|---|---|
| UPSERT Failure | DMS | Null value inserted into NOT NULL column in target DB |
| File Compression Failure | DMS | Source file extension doesn't match configured compression type |
| Post Collection Failure | DMS | Target directory for file movement doesn't exist |
| Data Type Mismatch | DMS | Incoming file schema doesn't match parser configuration |
| Authentication Failed | Platform | Incorrect credentials or expired AD account |
| Invalid Username or Email | Login | User entered wrong credentials |

> **PDF Reference:** Pages 141–393

---

## Module 2 — Application Monitoring

**What it is:** A live dashboard showing the health and status of all HyperSense pipelines and studios.

### What to Check
- **Pipeline Status** — Running / Paused / Failed / Success
- **Batch vs. Streaming** pipeline counts
- **Case generation status** from BMS and PAS
- **Data source indicators** — should always be green

### How to Use
1. From the left nav, go to **Admin → Application Monitoring**.
2. Review the dashboard for any **red indicators**.
3. For failed pipelines, note the pipeline name and check **Error Logging** for details.

> **PDF Reference:** Pages 84–109

---

## Module 3 — Task Search

**What it is:** Search and locate specific tasks or pipeline runs across the platform for status tracking and troubleshooting.

### When to Use
- A user reports their pipeline is "stuck" or "not running"
- You need to find a specific task by name or ID
- Checking the history of a pipeline's executions

### How to Use
1. From the left nav, go to **Admin → Task Search**.
2. Enter the pipeline name, task ID, or date range.
3. View task status — Running, Completed, Failed, Queued.
4. For Failed tasks, click to see the error details.

> **PDF Reference:** Pages 394–401

---

## Module 4 — Audit Trail

**What it is:** Complete history of user actions — who did what and when. Use this to trace back issues caused by configuration changes.

### When to Use
- A user reports something "stopped working" after a config change
- Security team requests access history for a specific user
- Investigating unauthorized data access

### How to Use
1. Go to **Admin → Audit Trail**.
2. Filter by **User**, **Action Type**, or **Date Range**.
3. Look for configuration changes that correlate with the reported issue time.

> **PDF Reference:** Pages 110–113

---

## Module 5 — User Issues & Password Resets

### Common User Issues You'll Handle

| Issue | Resolution |
|---|---|
| User can't login | Check if account is locked (3 failed attempts). Go to User Management → unlock account. |
| Password expired | Ask user to use Forgot Password flow. Or reset via Admin → User Management. |
| User lost their 2FA device | User clicks Forgot Password → re-registers 2FA device via QR code flow. |
| AD user can't login | Check KeyCloak for `status=1` and `isAdUser=true` attribute mappers. |
| User doesn't see a module | Check their role/permissions in User Management. Module access is role-based. |

---

## Quick Reference — Support Workflows

| Scenario | Where to Go | What to Do |
|---|---|---|
| Pipeline failing | Error Logging → Application Monitoring | Filter by pipeline name → check error details |
| User account locked | Admin → User Management | Find user → unlock account |
| Find who changed a config | Admin → Audit Trail | Filter by date → look for config change events |
| Pipeline "stuck" | Admin → Task Search | Search by pipeline name → check task status |
| Performance issue | Admin → Application Monitoring | Check pipeline queue and data source indicators |

---

## Escalation Guide

| Level | Handles | Tools Used |
|---|---|---|
| **L1** | Login issues, password resets, access requests | User Management, Audit Trail |
| **L2** | Pipeline failures, data errors, monitoring alerts | Error Logging, Task Search, App Monitoring |
| **L3** | Deep config issues, schema bugs, system errors | Error Logs + stack traces → escalate to Dev |
