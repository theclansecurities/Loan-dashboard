# Property & Loan Dashboard

A fully client-side, interactive Home Loan Calculator built with vanilla HTML, CSS, and JavaScript. No build tools, no dependencies, no server required — just open the file in any browser.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)

---

## Features

### Property Management
- **Property Details** — Name, location, price, type (2/3/4 BHK, Villa, Plot, Commercial), carpet area, appreciation rate, possession date
- **Payment Schedule** — Dynamic add/remove payment rows with date, amount, and funding type (Equity / Loan / Subsidy)
- **Auto-calculated summaries** — Total paid, total equity, total loan drawn, remaining balance

### Loan Calculators

| Calculator | What it shows |
|---|---|
| **Amortization** | Monthly EMI, total payment, total interest, interest-to-principal ratio, full month-by-month table |
| **Pre-payment** | Compare Scenario A (same EMI, shorter tenure) vs Scenario B (reduced EMI, same tenure) with interest saved |
| **Rate Cut** | Compare Option 1 (lower EMI, same tenure) vs Option 2 (same EMI, shorter tenure) with interest saved |

### Visualizations
- **Principal vs Interest** stacked bar chart over tenure
- **Outstanding balance** line chart over time
- **Pre-payment comparison** — balance & cumulative interest line charts
- **Rate cut comparison** — 3-line balance chart + bar chart for total interest
- All charts are **responsive** and redraw on window resize

### UI/UX
- **Dark / Light theme toggle** — persisted via `data-theme` attribute, charts auto-recolor
- **Responsive design** — works on desktop, tablet, and mobile
- **Indian number formatting** — `Rs 50,00,000` style formatting
- **No external libraries** — pure Canvas API for all charts

---

## Quick Start

### Option 1: Download the HTML file
1. Download `property_loan_dashboard.html`
2. Double-click to open in any modern browser (Chrome, Firefox, Safari, Edge)
3. That's it — no server, no install

### Option 2: Clone and open
```bash
git clone https://github.com/yourusername/property-loan-dashboard.git
cd property-loan-dashboard
# Open property_loan_dashboard.html in your browser
```

---

## Usage Guide

### Step 1: Enter Property Details
Fill in property name, location, price, type, carpet area, appreciation rate, and possession date.

### Step 2: Add Payment Schedule
Click **"+ Add Payment"** to record each payment made toward the property. Specify:
- **Date** — when the payment was made
- **Amount** — payment value in Rs
- **Funding Type** — Equity (own money), Loan (bank disbursement), or Subsidy

The dashboard auto-calculates totals and remaining balance.

### Step 3: Configure Loan
Set your loan parameters:
- Loan amount (auto-suggests 80% of property price)
- Annual interest rate (%)
- Tenure in years
- Pre-payment amount and frequency (optional)

### Step 4: Calculate
Click **"Calculate & Show Graphs"** to generate:
- EMI and interest metrics
- Interactive charts
- Full amortization tables

### Step 5: Explore Scenarios
Switch between tabs to compare:
- **Amortization** — standard repayment schedule
- **Pre-payment** — impact of extra payments
- **Rate Cut** — impact of interest rate reduction

---

## Formulas Used

### EMI (Equated Monthly Installment)
```
EMI = P × r × (1 + r)^n / ((1 + r)^n − 1)
```
Where:
- `P` = Principal loan amount
- `r` = Monthly interest rate (annual rate ÷ 12)
- `n` = Total number of months (tenure × 12)

### Monthly Breakdown
```
Interest = Outstanding Balance × Monthly Rate
Principal = EMI − Interest
New Balance = Old Balance − Principal
```

### Rate Cut — Same EMI, Shorter Tenure
```
New Tenure = ln(EMI / (EMI − P × r_new)) / ln(1 + r_new)
```

---

## File Structure

```
property-loan-dashboard/
├── property_loan_dashboard.html    # Main application (single file)
├── home_loan_calculator.html       # Standalone loan calculator (3-in-1)
├── README.md                       # This file
└── .gitignore                      # Git ignore rules
```

> **Note:** The entire application is contained in a single HTML file. All CSS, JavaScript, and Canvas chart rendering is embedded — no external dependencies.

---

## Browser Compatibility

| Browser | Version | Status |
|---|---|---|
| Chrome | 90+ | ✅ Supported |
| Firefox | 88+ | ✅ Supported |
| Safari | 14+ | ✅ Supported |
| Edge | 90+ | ✅ Supported |

---

## Tech Stack

- **HTML5** — Semantic structure, form inputs, data attributes
- **CSS3** — CSS Variables for theming, Flexbox/Grid layouts, media queries
- **Vanilla JavaScript** — DOM manipulation, event delegation, Canvas API
- **Canvas 2D API** — Custom chart engine (no Chart.js, D3, or other libraries)

---

## Screenshots

### Dark Mode — Property Details
*(Add screenshot here)*

### Amortization Charts
*(Add screenshot here)*

### Pre-payment Comparison
*(Add screenshot here)*

### Light Mode
*(Add screenshot here)*

---

## Roadmap

- [ ] Export amortization table to CSV/Excel
- [ ] Save/load property profiles via localStorage
- [ ] PDF report generation
- [ ] Multiple loan comparison side-by-side
- [ ] GST / stamp duty calculator
- [ ] Rental yield calculator

---

## Contributing

Contributions are welcome! Since this is a single-file application, please keep changes focused:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

Please ensure your changes work in both **dark** and **light** themes.

---

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## Acknowledgements

- Inspired by Excel-based home loan calculators
- Built for Indian real estate market (Rs formatting, standard home loan terms)
- Designed for offline use — no data leaves your browser

---

**Made with ❤️ for home buyers and real estate investors.**
