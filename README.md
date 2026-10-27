# ColdChain Sentinel — Vaccine & Diagnostic Sample Monitoring System (PS02)

ColdChain Sentinel is an intelligent cold-chain integrity monitoring system built for vaccines and clinical samples. It detects temperature excursions, missing sensor telemetry, incomplete chain-of-custody transfers, and routes compromised batches to authorized QA investigation.

---

## Key Features

1. **Healthcare Operations Dashboard**
   - KPI metrics: Total monitored batches, batches in safe range, at-risk alerts, and pending reviews.
   - Sensor health warnings (stale telemetry, gap anomalies).
   - Real-time excursion alert stream.

2. **Batch Monitoring & Filtering**
   - Track batches by ID, product, cold-chain classification, destination, and current telemetry.
   - Filter by risk status, search by batch ID or carrier, and sort by deviation severity.
   - Color-coded risk indicators (Safe, Excursion, Sensor Issue, Custody Issue).

3. **High-Fidelity Temperature Monitoring**
   - Product-specific threshold bands (e.g., Ultra-Cold -80°C to -60°C for mRNA, 2°C to 8°C for Standard Vaccines).
   - Explicit gap rendering for missing telemetry (missing readings are never zeroed).
   - Duration-weighted thermal excursion calculations.

4. **Multi-Severity Excursion Alerts**
   - Critical, High, Medium, and Low severity classifications based on temperature deviation and exposure time.
   - Interactive acknowledgment and investigation workflows.
   - Immutable audit trail of alerts and actions.

5. **Chain of Custody Timeline**
   - Full timeline from manufacture dispatch through cold-hub transit to delivery.
   - Distinct visualization for verified physical handovers vs. dashed indicators for missing transfer confirmations.

6. **Quality Assurance & Review Queue**
   - Dedicated workflow for authorized personnel to investigate flagged batches.
   - Enforces reviewer identity and mandatory rationale notes before changing status (Pending Review, On Hold, Cleared, Rejected).
   - Clear simulated data disclaimer (not an automated final release tool).

---

## Getting Started Locally

### Prerequisites
- Node.js 18+ or 20+
- npm, pnpm, or bun

### Installation & Run
```bash
# 1. Install dependencies
npm install

# 2. Start local development server
npm run dev
```
Open your browser at `http://localhost:8080` (or the port shown in your terminal).

### Available Scripts
- `npm run dev` — Starts the local dev server with hot reload
- `npm run build` — Builds production-ready assets
- `npm run test` — Runs automated Vitest test suites

---

## Hackathon Presentation Script & Demo Flow

### 1. The Problem (30s)
> "Cold-chain failures cause billions of dollars in wasted vaccines and compromised patient diagnostics every year. Manual temperature logs fail to spot sensor gaps or unauthorized handovers before the product reaches the clinic."

### 2. The Solution (30s)
> "ColdChain Sentinel combines continuous thermal telemetry with immutable chain-of-custody tracking, offering automated risk triage and an auditable QA investigation workflow."

### 3. Demo Walkthrough (90s)
1. **Dashboard Overview**: Point out the live telemetry metrics, safe vs at-risk batches, and current sensor health warnings.
2. **Temperature Excursions**: Open the Temperature view. Highlight how product thresholds differ (-70°C mRNA vs 4°C vaccines) and show how sensor gaps are preserved instead of treated as 0°C.
3. **Chain of Custody**: Navigate to `/custody`. Toggle *'Only incomplete transfers'* to demonstrate missing handover detection.
4. **Investigation Decision**: Open the Review Queue. Select batch `CCS-1007`, enter QA reviewer notes, and trigger an *'On Hold'* or *'Cleared'* decision with full timestamp logging.

---

## Simulated Data Notice
All batch IDs, sensor readings, and custody logs in this application are simulated mock data created for hackathon prototyping and evaluation purposes.
