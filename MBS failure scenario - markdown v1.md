# MBS Trading Readiness Dashboard (Markdown)
*(Scenario: FICC Gateway Failure @ 06:08 AM CDT)*
*(Data as of: Friday, April 4, 2025 at 6:50 AM CDT)*

---

## [L0] Overall Business Health & Outcomes

* **Overall Status:** 🔴 **CRITICAL**
* **Key Outcomes (L0):**
    * Trading Volume (Prev. Day): `$1.2B` (`+5% DoD`) 🟢
    * Settlement Rate (T+1): `95.0%` (Falling) 🔴 *(Target: >99.5%)*
    * Reconciliation Breaks (Open): `12` (`+2 DoD`) 🟡 *(Target: <10)*
    * Collateral Sufficiency: `105%` (`+1% DoD`) 🟢 *(Target: >102%)*
* **Est. Financial Impact of Issues:** `$50k+` (Rising) 🔴

---

## [L1] Core Business Process: TRADE LIFECYCLE

* **Overall Health:** `85%` (Target: 99.5%) `[-13% DoD]` 🔴

---

### [L2] Stage 1: Trade Initiation & Matching

* **[L3] Steps:**
    1. `Step 1.1: Trade Order Entry`
    2. `Step 1.2: Counterparty Communication`
    3. `Step 1.3: Trade Matching Confirmation`
* **[L4] Key Outcomes (Stage 1):**
    * **Short-Term (Readiness):**
        * 🟢 OMS/Matching System Availability: OK
        * 🟢 Real-time Trade Volume: Normal Flow
        * 🟢 Pending Match Alerts: 0
    * **Mid-Term (Performance):**
        * Avg. Time-to-Match: `1.5 min` (Stable)
        * Match Failure Rate (Prev Day): `0.1%` (Target <0.2%)
* **[L4] Supporting Systems:**
    * 🟢 OMS (`100%`)
    * 🟢 Matching Engine (`100%`)

---

### [L2] Stage 2: Clearing & Settlement 🔴 CRITICAL

* **[L3] Steps:**
    1. `Step 2.1: Clearing Submission to FICC` <span style="color:red; font-style:italic; font-weight:bold;"><-- FAILING</span>
    2. `Step 2.2: Netting Process (by FICC)` <span style="color:red; font-style:italic; font-weight:bold;"><-- Blocked</span>
    3. `Step 2.3: Settlement Confirmation (from FICC)` <span style="color:red; font-style:italic; font-weight:bold;"><-- Blocked</span>
* **[L4] Key Outcomes (Stage 2):**
    * **Short-Term (Readiness):**
        * 🔴 FICC Connectivity: DOWN ⚠️ *(See Incident)*
        * 🟢 Settlement System Latency: Low
        * 🔴 Pending Clearing Alerts: `50+` (Rising)
    * **Mid-Term (Performance):**
        * 🔴 Settlement Failure Rate (T+1): (Rising - Est. >1%) ⚠️ *(Target <0.5%)*
        * Avg. Time-to-Clear (Post-Match): `N/A` (Blocked)
* **[L4] Supporting Systems:**
    * 🔴 FICC Gateway (`DOWN`) ⚠️
    * 🟡 Settlement System (`99.8%`)

---

### [L2] Stage 3: Post-Trade Processing 🟡

* **[L3] Steps:**
    1. `Step 3.1: Reconciliation`
    2. `Step 3.2: Collateral Management (Tracking)`
    3. `Step 3.3: Accounting Entry`
    4. `Step 3.4: Regulatory Reporting`
* **[L4] Key Outcomes (Stage 3):**
    * **Short-Term (Readiness):**
        * 🟡 Recon Engine Status: Slow Processing ⚠️ *(See Incident)*
        * 🟢 Accounting System Availability: OK
        * 🟢 Reporting Queue Depth: Low
    * **Mid-Term (Performance):**
        * 🟡 Reconciliation Exceptions (Open): `12` (Target <10)
        * 🔴 Aged Recon Exceptions (>3d): `3` (Target 0)
        * Avg. Time-to-Reconcile: `45 min` (Increasing 🟡)
* **[L4] Supporting Systems:**
    * 🟡 Recon Engine (`95%`) ⚠️
    * 🟢 Acct Ledger (`100%`)
    * 🟢 Reporting Tool (`100%`)

---

## [L1] Supporting Processes

* 🟢 Collateral Management: `100%` (Target: 100%) `[NC]`
* 🟢 Regulatory Reporting: `100%` (Target: 100%) `[NC]`

---

## [L_INCIDENT] Active Incidents Affecting Flow

| Status        | Description                                     | Impact                      | Owner           | ETR        |
| :------------ | :---------------------------------------------- | :-------------------------- | :-------------- | :--------- |
| 🔴 Investigating | **FICC Gateway Unavailable** (Relates to S2.1) | **CRITICAL** - Clearing Blocked | Network/Infra   | TBD        |
| 🟡 In Progress  | Recon Engine Slow Processing (Relates to S3.1)  | Medium (Delay)              | App Support     | 09:00 AM   |

*(Legend: 🟢=OK/Healthy, 🟡=Warning, 🔴=Critical/Failure, NC=No Change, TBD=To Be Determined, S2.1=Stage 2 Step 1 etc.)*
