# APG ROI Calculator

A comprehensive multi-step ROI calculator that helps businesses understand the cost of their current SaaS tools, operational inefficiencies, and AI enablement opportunities—comparing them against APG solution investment.

## Tech Stack

- **HTML/CSS/JS**: Single `index.html` file with embedded styles and scripts
- **Font**: Inter (Google Fonts)
- **Charts**: Custom canvas-based line chart (no external libraries)
- **No build tools**: Vanilla implementation, no dependencies

## Architecture

All code is contained in `index.html`:
- Lines 8-794: CSS styles
- Lines 796-968: HTML structure (5-step wizard)
- Lines 970-1802: JavaScript (data, state, initialization, calculations, chart rendering)

## 5-Step Wizard Flow

### Step 1: SaaS Tool Selection
16 categories with 70+ tools, each with 3 pricing tiers:
- CRM & Sales, Project Management, Form Tools, Social Media
- Dashboards & BI, Support & Help Desk, Invoicing & Accounting
- Time Tracking, Communication, Automation, Document Management
- E-signature, Scheduling, Marketing, Collaboration & Wikis, HR & Payroll

Users can:
- Expand/collapse categories (accordion style)
- Select individual tools
- Choose pricing tier (T1/T2/T3)
- Set number of users per tool

### Step 2: Inefficiency Waste
5 waste categories with adjustable inputs:
- Duct-tape Labor
- Email Archaeology
- Spreadsheet Hell
- File Hunting
- Status Meetings

Each has sliders for:
- Hours per week (team-wide): 0-80h
- Hourly labor rate (AUD): $20-$150

### Step 3: AI Enablement
10 AI agents with toggle on/off:
- Company Context Agent, Customer Service AI, Sales Assistant
- Financial Insights, Proposal Generator, Project Kickoff Agent
- Timesheet Approval Agent, Client Onboarding Agent
- Intelligent Semantic Search, Meeting Prep Agent

Shows monthly opportunity cost for each enabled agent.

### Step 4: APG Investment
3 tier options:
- Tier 1: $65,000 one-time + $999/mo maintenance (starts month 7)
- Tier 2: $95,000 one-time + $999/mo maintenance
- Tier 3: $125,000 one-time + $999/mo maintenance

### Step 5: Summary Dashboard
- Summary cards: Monthly waste, Annual waste, Investment, Break-even point
- 36-month ROI projection chart (canvas-based)
- Detailed cost breakdown
- 3-year net savings calculation

## Key Features

### Running Total Bar
Sticky footer showing real-time totals as user progresses:
- SaaS Cost/mo
- Inefficiency/mo
- AI Opportunity/mo
- Total Waste/mo

### Responsive Design
- Desktop: Full layout with all controls visible
- Mobile: Stacked layout, step labels hidden in progress bar

### Iframe Integration
- Communicates height changes to parent via `postMessage`
- Uses MutationObserver for dynamic content height updates
- Throttled updates (150ms) to prevent rapid fire messages

## Design

- Dark theme: `#0a0a0a` background
- Accent color: `#7DFF00` (lime green)
- Semi-transparent panels with subtle borders
- Smooth transitions and hover states

## File Structure

```
roi-calculator/
├── index.html                                    # Complete application
├── claude.md                                     # This documentation
└── finalcalc.xlsx - APG_ROI_Calculator_working.csv  # Source data
```

## Data Sources

Tool pricing and categories based on `finalcalc.xlsx - APG_ROI_Calculator_working.csv`:
- Section 1: SaaS Tool Selection (70+ tools with tier pricing)
- Section 2: Inefficiency Waste (5 categories)
- Section 3: AI Enablement (10 AI agents)
- Section 4: APG Investment (3 tiers)
- Section 5: Summary calculations and 36-month projections

## Development Notes

- No build process required - edit `index.html` directly
- Test locally by opening `index.html` in a browser
- Background is solid dark for standalone use, works in iframes
- All calculations update in real-time as users interact
