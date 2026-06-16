# HyperSense for Administrators

> **Role:** System Administrator / Platform Admin
> **Goal:** Manage users, configure platform settings, monitor health, and maintain audit compliance.

---

## Your Learning Path

```
Getting Started → User Management → Common Settings → Audit Trail → Application Monitoring → Error Logging → Housekeeping
```

---

## Module 1 — User Management

**What it is:** Create and manage user accounts, assign roles, and control access permissions.

### Key Tasks
- Create new users and assign roles
- Configure group memberships
- Enable/disable 2FA per user
- Manage AD-integrated users via KeyCloak

### Creating a New User
1. From the left nav, go to **Admin → User Management**.
2. Click **New User**.
3. Enter: First Name, Last Name, Email, Username.
4. Assign a **Role** (Analyst, Developer, Admin, etc.).
5. Click **Save**.

### Roles & Permissions
- All role and permission configurations are managed via **KeyCloak**.
- AD users get privileges assigned through KeyCloak attribute mappers.
- Configure `status = 1` (active) and `isAdUser = true` for federated AD users.

> **PDF Reference:** Pages 402–410

---

## Module 2 — Common Settings

**What it is:** Platform-wide configuration settings that apply across all studios.

### Key Configuration Areas
- **Password Policy** — expiry, length, complexity rules
- **Session Properties** — idle timeout, max session duration
- **Login Timeout** — max time to complete login actions
- **Lockout Properties** — login failure thresholds
- **KeyCloak Configuration** — SSO, 2FA, AD integration

> **PDF Reference:** Pages 114–140

---

## Module 3 — Audit Trail

**What it is:** A complete log of all user actions and system events for compliance and security monitoring.

### What It Tracks
- User logins and logouts
- Configuration changes
- Data access and modifications
- Pipeline create/edit/delete actions

### Accessing Audit Trail
1. From the left nav, go to **Admin → Audit Trail**.
2. Filter by **user**, **date range**, or **action type**.
3. Export logs for compliance reporting.

> **PDF Reference:** Pages 110–113

---

## Module 4 — Application Monitoring

**What it is:** A dashboard providing real-time health and performance visibility of all HyperSense studios.

### What It Monitors
- Number of **Batch and Streaming pipelines** and their status
- Cases generated from BMS and PAS pipelines
- Studio-level health indicators

### Setup Steps
1. **Import Dashboard** — contact the admin for the JSON dashboard file, then import it via BI Studio → Dashboard Repository.
2. **Update Data Source** — edit PostgreSQL connection details (host, port, username, password) for all Application Monitoring data sources.
3. **Import Dataset** — complete dataset import via BI Studio.
4. Verify data source indicators show **green** in the Visualizer tab.

> **PDF Reference:** Pages 84–109

---

## Module 5 — Error Logging

**What it is:** Centralized log management for diagnosing and troubleshooting platform issues.

### Key Features
- View and filter system error logs
- Identify pipeline failures and data processing errors
- Download logs for deeper analysis

> **PDF Reference:** Pages 141–393

---

## Module 6 — Housekeeping

**What it is:** Tools for maintaining platform health — clearing old data, archiving, and storage management.

### Key Tasks
- Archive or purge old pipeline runs
- Manage storage utilization
- Schedule housekeeping jobs

> **PDF Reference:** Pages 411–413

---

## Quick Reference — Admin Workflows

| Task | Module | Location |
|---|---|---|
| Add a new user | User Management | Admin → User Management → New User |
| Reset user password | User Management | Admin → User Management → Edit User |
| View all audit events | Audit Trail | Admin → Audit Trail |
| Check pipeline health | Application Monitoring | Admin → Application Monitoring |
| View error logs | Error Logging | Admin → Error Logging |
| Configure password policy | Common Settings | Admin → Common Settings |
| Run housekeeping | Housekeeping | Admin → Housekeeping |

---

## Admin Best Practices
- Review **Audit Trail** weekly for unusual access patterns.
- Set **password expiry** to 90 days and enforce complexity rules.
- After any platform upgrade, verify **Application Monitoring** dashboards show green indicators.
- Configure **2FA** for all admin-level accounts.
