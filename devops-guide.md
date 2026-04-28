# HyperSense for DevOps Engineers

> **Role:** DevOps / Infrastructure / Platform Operations Engineer
> **Goal:** Keep HyperSense running reliably — monitor health, manage infrastructure, handle deployments, and maintain system hygiene.

---

## Your Learning Path

```
Getting Started → Application Monitoring → Housekeeping → Error Logging → Common Settings → KeyCloak Configuration
```

---

## Module 1 — Application Monitoring

**What it is:** The primary operations dashboard for HyperSense. Your first stop every morning.

### What to Monitor Daily
- All pipeline statuses — Batch and Streaming
- Studio health indicators (should be green)
- Case generation volume from BMS and PAS
- Data source connectivity

### Setup (One-time)

#### 1. Import the Monitoring Dashboard
1. Get the **JSON dashboard file** from the admin.
2. Go to **BI Studio → Dashboard Repository**.
3. Click **Import** → Select JSON file → Click **Open** → Click **Import**.

#### 2. Configure Data Source Connections
1. Go to **BI Studio → Create Dashboard → Data Source tab**.
2. Search for **Application Monitoring** folder.
3. Edit each data source:
   - Click **Edit Connection** → Search for the pre-selected connection → click edit.
   - Update **PostgreSQL** details: username, password, host/IP, port.
   - Click **Test Connection** — must show success.
   - Click **Done**.
4. In the **Preview tab**, click the play icon next to the SQL Query.
5. Click **No** on the override confirmation.
6. Verify preview loads correctly → click **Done**.

#### 3. Import Dataset
- Complete dataset import as per the admin's guidance.

#### 4. Verify Dashboard
- In **Visualizer tab**, search for all Application Monitoring data sources.
- All indicators should be **green**.

> **PDF Reference:** Pages 84–109

---

## Module 2 — Housekeeping

**What it is:** Tools for maintaining platform hygiene — archiving old runs, clearing stale data, and managing storage.

### Regular Housekeeping Tasks

| Task | Frequency | Why |
|---|---|---|
| Archive old pipeline run logs | Weekly | Prevents database bloat |
| Purge stale error logs | Monthly | Keeps error log search fast |
| Review storage utilization | Weekly | Prevents disk space issues |
| Schedule housekeeping jobs | One-time setup | Automate recurring cleanup |

### How to Access
1. From the left nav, go to **Admin → Housekeeping**.
2. Configure retention periods for pipeline runs and logs.
3. Schedule automated housekeeping jobs.

> **PDF Reference:** Pages 411–413

---

## Module 3 — Error Logging (Ops View)

**What it is:** Centralized error logs for all platform components. Essential for incident response.

### DevOps Usage Pattern
- **Proactive monitoring** — check for recurring error patterns
- **Incident response** — correlate error timestamps with deployment events
- **Capacity planning** — identify resource-heavy operations

### How to Use
1. Go to **Admin → Error Logging**.
2. Filter by time range and studio.
3. Look for **recurring errors** that might indicate infrastructure issues (memory, disk, network).
4. Download logs for centralized logging platforms (ELK, Splunk, etc.).

> **PDF Reference:** Pages 141–393

---

## Module 4 — Common Settings (Platform Configuration)

**What it is:** Platform-wide settings that affect all users and studios. Handle with care — changes here are global.

### Key Settings for DevOps

| Setting | What It Controls |
|---|---|
| **Session Properties** | Idle timeout and max session duration |
| **Login Timeout** | Max time to complete login |
| **Lockout Properties** | Failed login thresholds |
| **Password Policy** | Password expiry, complexity, history |

> **PDF Reference:** Pages 114–140

---

## Module 5 — KeyCloak Configuration

**What it is:** The identity and access management backbone of HyperSense. Manages SSO, 2FA, and AD integration.

### Key DevOps Tasks

#### Configure 2FA (OTP)
1. In KeyCloak admin → **Realm Settings → Security Defenses → Headers**.
2. Add `Data:` next to `img-src self` in Content Security Policy (for migrated setups).
3. Go to **Authentication → Required Actions** → enable **Configure OTP**.
4. OTP Policy defaults: Time Based, SHA1, 6 digits, 30-second period.

#### Add Azure AD as Identity Provider (SAML)
1. Go to KeyCloak → **Identity Providers** → select **SAML**.
2. Set alias and display name.
3. In Azure portal, register the app and add the KeyCloak redirect URI.
4. Copy the **Federation Metadata Document** URL from Azure endpoints.
5. Paste into **Import from URL** in KeyCloak and save.

#### Required AD Attribute Mappers
For AD users to show as active and federated in HyperSense:

| Attribute | Mapper Type | Value |
|---|---|---|
| `status` | Hardcoded attribute | `1` (active user) |
| `isAdUser` | Hardcoded attribute | `true` |

#### Configure Auto-redirect to AD Login
1. Go to **Authentication → Flows → Browser**.
2. In Identity Provider row, set mode to **ALTERNATIVE**.
3. Click **Actions → Config** → enter the alias of the identity provider.
4. Save — HyperSense login will now redirect to AD.

> **PDF Reference:** Pages 12–15

---

## Quick Reference — DevOps Runbook

| Scenario | Action | Location |
|---|---|---|
| Morning health check | Review monitoring dashboard | Application Monitoring |
| Disk space alert | Run housekeeping job | Admin → Housekeeping |
| Platform degraded | Check error logs for spikes | Admin → Error Logging |
| Users locked out after AD change | Verify KeyCloak attribute mappers | KeyCloak Admin Console |
| Session expiry complaints | Adjust session properties | Admin → Common Settings |
| New SSO integration | Configure SAML identity provider | KeyCloak Admin Console |
| 2FA issues | Check OTP policy configuration | KeyCloak → Authentication |
