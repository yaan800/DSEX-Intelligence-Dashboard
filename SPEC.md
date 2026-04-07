# DSEX Market Intelligence Dashboard — SPEC.md

## Concept & Vision

A sophisticated, Bloomberg-terminal-inspired market intelligence dashboard for tracking the Dhaka Stock Exchange (DSEX) alongside global macro indicators. The interface conveys authority and precision — designed for institutional analysts and serious retail investors who need actionable insights without market noise. The aesthetic is dark, data-dense, and unapologetically technical.

## Design Language

### Aesthetic Direction
Bloomberg Terminal meets modern fintech — dark interfaces with high-contrast data visualization, monospace fonts for numbers, and a clinical precision that signals credibility.

### Color Palette
- **Background Primary**: `#0d1117` (deep charcoal)
- **Background Secondary**: `#161b22` (card surfaces)
- **Background Tertiary**: `#21262d` (elevated elements)
- **Text Primary**: `#f0f6fc` (high contrast white)
- **Text Secondary**: `#8b949e` (muted labels)
- **Accent Green**: `#3fb950` (positive changes, gains)
- **Accent Red**: `#f85149` (negative changes, losses)
- **Accent Blue**: `#58a6ff` (neutral highlights, links)
- **Accent Yellow**: `#d29922` (warnings, attention)
- **Border**: `#30363d`

### Typography
- **Headings**: Inter (600/700 weight), clean sans-serif
- **Data/Numbers**: JetBrains Mono (monospace for precise alignment)
- **Body Text**: Inter (400 weight)
- **Sizes**: 12px base for dense data, 14px for readable content, 24-32px for key metrics

### Spatial System
- 4px base unit
- Card padding: 16px
- Gap between cards: 16px
- Section margins: 24px

### Motion Philosophy
- Subtle pulse animations on live data indicators
- Smooth 200ms transitions on hover states
- No distracting animations — data integrity over flash

### Visual Assets
- Custom SVG charts (line, bar, area)
- Sparkline mini-charts for quick trend indication
- Donut chart for sector allocation
- No external images

## Layout & Structure

### Page Architecture
Single-page dashboard with five main sections arranged in a responsive grid:

1. **Header Bar** — Logo, title, last updated timestamp, market status indicator
2. **DSEX Overview Panel** — Main index card with large price, change %, technical levels
3. **Global Indices Grid** — 2×2 grid showing S&P 500, Nikkei, DAX, FTSE
4. **Energy & Commodities** — Brent/WTI prices with Bangladesh context
5. **Local Macro Panel** — Repo rate, inflation, USD/BDT exchange rate
6. **Sector Performance Table** — Daily sector rotation with turnover data
7. **Technical Analysis Card** — Support/resistance levels, moving averages

### Responsive Strategy
- Desktop: 3-column grid layout
- Tablet: 2-column grid
- Mobile: Single column stack

## Features & Interactions

### Core Features
1. **DSEX Index Display**
   - Current value with decimal precision
   - Daily change (points and percentage)
   - Week-to-date and month-to-date performance
   - Interactive sparkline showing 30-day trend

2. **Global Indices Monitor**
   - Real-time style quotes for major indices
   - Country flag indicators
   - 24-hour mini-chart for each index
   - Correlation indicator (positive/negative movement)

3. **Commodities Tracker**
   - Brent Crude and WTI prices
   - Price change with percentage
   - "Bangladesh Impact" indicator (High/Medium/Low)
   - 7-day trend sparkline

4. **Local Macro Data**
   - Bangladesh Bank Repo Rate (current)
   - National Inflation Rate (CPI)
   - USD/BDT Exchange Rate (interbank)
   - Trend arrows for direction

5. **Sector Performance Table**
   - Sortable columns: Sector, Price Change, Turnover (BDT Crore), Volume
   - Lead sector highlighted
   - Color-coded performance bars

6. **Technical Levels Card**
   - Pivot point
   - Support levels (S1, S2, S3)
   - Resistance levels (R1, R2, R3)
   - 50-day and 200-day moving averages
   - Psychological levels

### Interaction Details
- Hover on cards: subtle elevation increase
- Hover on table rows: highlight row
- Click sector row: could expand (future feature placeholder)
- Refresh button: pulse animation while "loading"

### Edge Cases
- Market closed: Display "Market Closed" badge with next open time
- Data unavailable: Show "—" with muted styling
- Negative values: Display in red with minus sign
- All-time high/low: Special badge indicator

## Component Inventory

### Index Card Component
- Large numeric display (32px)
- Change badge (green/red pill)
- Mini sparkline chart
- States: loading (skeleton), live, closed

### Data Table Component
- Sticky header
- Alternating row backgrounds
- Sortable column headers
- States: default, hover, loading

### Metric Card Component
- Label (muted)
- Value (large, monospace)
- Change indicator
- Optional sparkline

### Status Badge Component
- Market open (green dot + "Open")
- Market closed (gray dot + "Closed")
- Pre-market (yellow dot + "Pre-Market")

### Chart Components
- Line Chart: SVG-based, smooth curves
- Area Chart: Filled line chart
- Bar Chart: Vertical bars for sector performance
- Sparkline: Minimal line for inline trends

## Technical Approach

### Framework
- React 18 with TypeScript
- Vite for bundling
- Tailwind CSS for styling

### Architecture
- Component-based structure
- Custom hooks for data formatting
- Utility functions for financial calculations

### Data Strategy
- Static realistic sample data (simulated market data)
- Structured for easy API integration later
- All monetary values in BDT with proper formatting

### Key Implementation Details
- SVG charts rendered with React components
- Responsive grid using Tailwind
- Dark theme via Tailwind custom configuration
- Number formatting: Locale-aware with proper separators
