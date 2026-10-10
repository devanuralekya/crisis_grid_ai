# CrisisGrid AI

Urban disaster and civic intelligence platform. A single-page web app that combines citizen issue reporting, flood-risk prediction, safe-route finding, hospital and shelter capacity, and a flood alert system with a voluntary relief fund.

## Features

- **Command overview**: city-wide complaints, flood risk, alerts and resources
- **Flood alert and relief fund** (new)
  - Authorities issue a flood alert for chosen localities, with level, message, suggested amount and fund target
  - Residents of those localities see the alert banner and can contribute ₹1 to ₹500 voluntarily
  - Pooled relief fund with live total, target progress, locality breakdown and proposed allocation
  - Public contribution ledger (receipt, locality, amount, no names)
- **Report an issue**: photo and description, AI-style classification and department routing
- **Complaints and priority**: queue ranked by severity, flood risk and duplicate reports
- **Hazard map and routes**: predicted flood risk per locality, safe routes for ambulances and evacuation
- **Hospitals and shelters**: capacity and access status
- **Infrastructure monitor**: sensors, drainage health, Gumbel return-period analysis

## Flood model

Forecast rainfall → runoff (SCS Curve Number) → peak flow (Rational Method with Kirpich time of concentration) → drain capacity (Manning's equation) → risk = peak flow ÷ capacity.

## Relief fund process

1. Authority issues a flood alert
2. Residents of affected localities are notified
3. Voluntary micro-contributions (₹1 to ₹500)
4. Contributions are pooled into one fund per alert
5. Fund is allocated: 40% relief, 25% pumps and drains, 25% shelters and rescue, 10% audit and payment costs
6. Totals and receipts stay visible in the public ledger

## Run it

No build step. Open `index.html` in a browser, or host it with GitHub Pages (Settings → Pages → deploy from the `main` branch, root folder).

## Important notes

- All data is **simulated demo data** (city, sensors, complaints, curve numbers, catchment areas, drain sizes). Calibrate against past floods before any real use.
- The payment checkout is a **simulation**. No money moves. A real deployment needs a government-approved payment gateway (for example UPI or a payment aggregator) and an official relief-fund account.
- When opened outside claude.ai (for example on GitHub Pages), the app runs in demo mode: reports, alerts and contributions are kept in memory only and reset on reload.
- Informational only. For official warnings see [IMD](https://mausam.imd.gov.in/), [CWC](https://cwc.gov.in/) and your state disaster management authority.

## Tech

Plain HTML, CSS and JavaScript in one file. No dependencies except the Public Sans font from Google Fonts.
