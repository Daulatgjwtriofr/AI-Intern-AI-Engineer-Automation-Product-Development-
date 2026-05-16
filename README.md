<div align="center">

<img src="https://img.shields.io/badge/⚡-Energybae-2d6a4f?style=for-the-badge&logoColor=white" alt="Energybae"/>

# ⚡ Energybae — Solar Load Calculator
### AI-Powered Electricity Bill to Excel Automation

[1[Made with HTML](https://img.shields.io/badge/Made%20with-HTML%2FJS-orange?style=flat-square&logo=html5)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[2[AI Powered](https://img.shields.io/badge/AI-Google%20Gemini-4285F4?style=flat-square&logo=google)](https://ai.google.dev/)
[3[Free to Use](https://img.shields.io/badge/API-FREE%201500%2Fday-52b788?style=flat-square)](https://aistudio.google.com/app/apikey)
[4[No Backend](https://img.shields.io/badge/Backend-None%20Required-lightgrey?style=flat-square)](/)
[5[License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)

**Upload an electricity bill → AI reads it → Get a filled Excel file in under 30 seconds.**

*Built as part of the Energybae AI Intern practical task — Pimpri, Pune*

---

[🚀 Live Demo](#-live-demo) · [✨ Features](#-features) · [🛠️ How It Works](#️-how-it-works) · [⚙️ Setup](#️-setup-guide) · [📸 Screenshots](#-screenshots) · [🧠 Tech Stack](#-tech-stack)

</div>

---

## 🎯 Problem Statement

Energybae helps homes and businesses switch to solar power. A key part of the sales process is analyzing a customer's electricity bill to calculate the correct solar system size.

**Before this tool — the process was:**
- Customer shares electricity bill (PDF or photo)
- Team manually reads bill → extracts units, load, tariff slab, etc.
- Data entered into Excel to calculate solar system size, savings, and ROI
- ⏱️ **Time taken: 15–30 minutes per customer**
- 📉 Done dozens of times per week = massive bottleneck

**After this tool:**
- Upload bill → AI auto-extracts all data → Excel downloaded
- ⚡ **Time taken: Under 30 seconds**

---

## ✨ Features

| Feature | Description |
|---|---|
| 📄 **Bill Upload** | Drag & drop or click — supports JPG, PNG, PDF, WEBP |
| 🤖 **AI Extraction** | Google Gemini reads the bill and extracts 15+ fields automatically |
| ✏️ **Manual Edit** | All auto-filled fields are editable — AI mistakes can be corrected |
| ☀️ **Solar Sizing** | Calculates recommended system size (kWp), panels needed, rooftop area |
| 💰 **Financial Analysis** | Monthly saving, annual saving, payback period, PM Surya Ghar subsidy |
| 📊 **25-Year Projection** | Year-by-year savings table with tariff inflation factored in |
| 🌱 **CO₂ Impact** | Annual carbon offset and tree-planting equivalent |
| 📥 **3-Sheet Excel** | Filled Excel with Bill Data, Solar Calculation, and Customer Summary sheets |
| 🌐 **No Installation** | Pure HTML/JS — runs in any browser, no server needed |
| 🆓 **Free API** | Uses Google Gemini 1.5 Flash — 1500 requests/day free, no credit card |

---

## 🛠️ How It Works

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   STEP 1         STEP 2          STEP 3         STEP 4     │
│                                                             │
│  📄 Upload  →  🤖 Gemini AI  →  ✏️ Review  →  📥 Excel   │
│   Bill         Reads Bill       & Edit         Download    │
│                                                             │
│  JPG/PNG/       Extracts        Fix any        3-Sheet     │
│  PDF/WEBP       15+ fields      AI errors      .xlsx file  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### What Gemini AI Extracts from the Bill

```json
{
  "consumer_name":      "Rajesh Kumar",
  "consumer_number":    "123456789012",
  "meter_number":       "MH04E1234567",
  "bill_month":         "March 2024",
  "tariff_category":    "LT Residential",
  "address":            "Flat 3, Shiv Sagar CHS, Pimpri, Pune 411018",
  "previous_reading":   4200,
  "current_reading":    4523,
  "units_consumed":     323,
  "sanctioned_load":    5.0,
  "bill_amount":        2840,
  "fixed_charges":      130,
  "arrears":            0,
  "rate_per_unit":      8.79,
  "due_date":           "15/04/2024"
}
```

### Solar Calculation Formula

```
Daily Units  =  Monthly Units ÷ 30
System Size  =  Daily Units ÷ (Peak Sun Hours × System Efficiency)
               = (323 ÷ 30) ÷ (4.5 × 0.80)
               = 2.99 kWp  →  rounded up to  3.0 kWp

Panels Needed  =  (System kWp × 1000) ÷ Panel Wattage
               =  (3.0 × 1000) ÷ 400  =  8 panels

Monthly Saving  =  min(Solar Generation, Units Consumed) × Rate/unit
Net Cost        =  Gross Cost − PM Surya Ghar Subsidy
Payback Period  =  Net Cost ÷ Annual Saving
```

---

## ⚙️ Setup Guide

### Step 1 — Get Free Gemini API Key

1. Go to **[aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)**
2. Sign in with your Google account
3. Click **"Create API Key"**
4. Copy the key — it looks like: `AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXX`

> 🆓 **Completely free** — 1500 requests per day, no credit card required

### Step 2 — Download and Open the App

```bash
# Clone this repository
git clone https://github.com/YOUR_USERNAME/energybae-solar-calculator.git

# Navigate to folder
cd energybae-solar-calculator

# Open in browser — just double click!
open energybae_solar_calculator.html
# OR on Windows:
start energybae_solar_calculator.html
```

**No npm install. No pip install. No server. Just open and use.**

### Step 3 — Use the App

1. **Paste your Gemini API key** in the box at the top → click Save
2. **Upload** electricity bill (photo or PDF)
3. **Click "Extract Data"** — Gemini reads the bill in ~10 seconds
4. **Review** the auto-filled fields, edit if needed
5. **Click "Download Excel"** — done ✅

---

## 📁 Project Structure

```
energybae-solar-calculator/
│
├── energybae_solar_calculator.html   ← Main app (entire project in 1 file)
├── README.md                         ← This file
├── sample_bill/
│   └── sample_msedcl_bill.jpg        ← Sample MSEDCL bill for testing
└── sample_output/
    └── Energybae_Solar_Sample.xlsx   ← Example Excel output
```

> **Why a single HTML file?**  
> Zero dependencies, zero setup, works offline, easy to share via WhatsApp or email. The Energybae field team can just double-click and use it.

---

## 📊 Excel Output — 3 Sheets

### Sheet 1: Bill Data
Customer details, consumer number, meter number, address, bill month, tariff category, all consumption figures, charges breakup.

### Sheet 2: Solar Calculation
Full solar sizing logic, all assumptions (editable), financial analysis, and a **25-year year-by-year savings projection table** with tariff inflation.

### Sheet 3: Summary (Customer Proposal)
Clean one-page summary ready to share with the customer — system size, net cost after subsidy, monthly saving, payback period, lifetime saving.

---

## 🧠 Tech Stack

| Technology | Purpose | Why chosen |
|---|---|---|
| **HTML / CSS / JS** | Frontend & logic | Zero dependencies, runs anywhere |
| **Google Gemini 1.5 Flash** | Bill reading (Vision AI) | Free 1500/day, excellent OCR & understanding |
| **SheetJS (xlsx.js)** | Excel file generation | Client-side Excel creation, no server needed |
| **Google Fonts (DM Sans)** | Typography | Clean, professional look |

**No backend. No database. No framework. No build step.**

---

## 🔧 Customization

All calculation assumptions are editable in the app UI — no code changes needed:

| Parameter | Default | Description |
|---|---|---|
| Peak Sun Hours | `4.5 hrs/day` | Maharashtra average — change for other states |
| System Cost/kWp | `₹65,000` | Adjust as per current market rates |
| Panel Wattage | `400W` | Change for different panel specs |
| System Efficiency | `80%` | Accounts for cable loss, inverter loss, etc. |
| PM Surya Ghar Subsidy | `₹78,000` | Government subsidy — update as policy changes |
| Tariff Inflation | `5%/year` | For 25-year projection calculation |

---

## 🗺️ Roadmap / Future Improvements

- [ ] **WhatsApp Bot** — Customer sends bill photo on WhatsApp, gets Excel back
- [ ] **Multi-month averaging** — Upload 3 months of bills for better load estimate
- [ ] **Google Sheets integration** — Auto-fill into team's shared Google Sheet
- [ ] **State-wise tariff database** — Auto-detect state from bill, apply correct sun hours
- [ ] **Proposal PDF export** — Branded PDF with Energybae letterhead
- [ ] **Mobile app** — React Native wrapper for field sales team

---

## ⚠️ Important Notes

- The **Gemini API key is stored only in your browser session** — it is never sent to any third-party server except Google's API
- Bill images are sent to Google's Gemini API for processing — do not use bills with sensitive personal data in a production environment without proper consent
- Solar calculations are estimates based on average Maharashtra irradiance — a site survey is recommended before installation
- The Excel template preserves formula cells — only input cells are populated

---

## 👨‍💻 Built By

**AI Intern Practical Task — Energybae**  
Issued by: Energybae Founders, Pimpri, Pune  
Submission: [pranay@energybae.in](mailto:pranay@energybae.in)

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

<div align="center">

**⚡ Energybae — Empowering People with Renewable Energy Solutions**

[www.energybae.in](https://energybae.in) · [energybae.co@gmail.com](mailto:energybae.co@gmail.com) · +91 9112233120

*Office No. 42, 1st Floor, Sukhwani Chambers, Kamala Cross Rd, MIDC, Pimpri Colony, Pune, Maharashtra 411018*

</div>
