# UI/UX Specification Document

## Project: Nexora — Autonomous AI for Evidence-Based Data Intelligence
**Document Version:** 1.0.0  
**Status:** Approved UI/UX Design System  
**Target Release:** MVP (Phase 1)  
**Author:** Nexora Product Design & Experience Group  
**Last Updated:** October 2026  

---

## 1. Design Philosophy & Guiding Principles

Nexora is designed to deliver the rigorous precision of an elite data science laboratory combined with the effortless elegance of a modern consumer SaaS product.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                          CORE DESIGN PILLARS                                │
├──────────────────────────┬──────────────────────────┬───────────────────────┤
│ 1. Radical Transparency  │ 2. Evidence-First Layout │ 3. Micro-Interaction  │
│ Inspectable agent logic  │ Never state a number     │ Fluid status updates, │
│ and verifiable tools.    │ without its proof card.  │ zero "black box" lag. │
└──────────────────────────┴──────────────────────────┴───────────────────────┘
```

1. **Radical Transparency:** The interface never hides the AI's internal process behind a generic loading spinner. Users watch the agent decompose the problem, select Python tools, and validate results in real time.
2. **Evidence-First Layout:** Every analytical statement is visually tethered to an interactive chart and an expandable "Statistical Evidence" chip showing sample sizes, test statistics, and $p$-values.
3. **Cognitive Calm & Modern Aesthetics:** Built on a sleek, high-contrast dark palette (Deep Obsidian `#0B0F19`, Slate `#1E293B`, Indigo Accent `#6366F1`) with crisp typography and subtle glassmorphic elevation.
4. **Implementation-Ready Architecture:** Designed around atomic **shadcn/ui** and **Tailwind CSS** components with native **Recharts** integration.

---

## 2. Design Tokens & Design System

### 2.1 Color Palette

```
  Surface Backgrounds:
  [#0B0F19 - Obsidian Base]  [#111827 - Surface Card]  [#1F2937 - Card Border]
  
  Brand & Interaction Accents:
  [#6366F1 - Indigo 500]     [#818CF8 - Indigo 400]    [#4F46E5 - Indigo 600]
  
  Statistical Status Signals:
  [#10B981 - Stat Significant] [#F59E0B - Stat Warning] [#EF4444 - Error / Alert]
  
  Chart Visualization Spectrum:
  [#6366F1 - Indigo]  [#06B6D4 - Cyan]  [#10B981 - Emerald]  [#F59E0B - Amber]  [#EC4899 - Pink]
```

* **Background (Base):** `hsl(222, 47%, 7%)` (`#0B0F19`)
* **Card Surface:** `hsl(222, 47%, 11%)` (`#111827`)
* **Card Border / Divider:** `hsl(217, 33%, 17%)` (`#1F2937`)
* **Primary Accent:** `hsl(239, 84%, 67%)` (`#6366F1`)
* **Statistical Significant ($p < 0.05$):** `hsl(158, 64%, 52%)` (`#10B981`)
* **Statistical Inconclusive ($p \ge 0.05$):** `hsl(38, 92%, 50%)` (`#F59E0B`)
* **Error / Critical Warning:** `hsl(0, 84%, 60%)` (`#EF4444`)
* **Text Primary:** `hsl(210, 40%, 98%)` (`#F8FAFC`)
* **Text Secondary:** `hsl(215, 20%, 65%)` (`#94A3B8`)
* **Text Muted:** `hsl(215, 16%, 47%)` (`#64748B`)

### 2.2 Typography Hierarchy

* **Primary Font Family:** `Inter`, `-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif`
* **Monospace Font Family (Data, Code, Statistics):** `JetBrains Mono`, `'Fira Code', monospace`

| Style Token | Size / Line Height | Weight | Usage |
| :--- | :--- | :--- | :--- |
| `display-1` | 32px / 40px | Bold (700) | Major Landing / Workspace Title |
| `h1` | 24px / 32px | SemiBold (600) | Section Headers & Report Titles |
| `h2` | 20px / 28px | SemiBold (600) | Card Headers & Visual Titles |
| `h3` | 16px / 24px | Medium (500) | Sub-section & Insight Headlines |
| `body-base` | 14px / 20px | Regular (400) | General body copy, chat text, tables |
| `body-sm` | 12px / 16px | Regular (400) | Tooltips, metadata labels, status badges |
| `mono-stat` | 13px / 18px | Medium (500) | Numbers, $p$-values, tool parameters |

### 2.3 Elevation, Borders & Glassmorphism
* **Card Border:** `1px solid rgba(255, 255, 255, 0.08)`
* **Card Glow:** `box-shadow: 0 4px 20px -2px rgba(0, 0, 0, 0.5)`
* **Glass Panel:** `backdrop-filter: blur(12px); background: rgba(17, 24, 39, 0.85)`
* **Border Radius:**
  * Chips & Badges: `9999px` (Full Pill)
  * Cards & Modals: `12px` (`rounded-xl`)
  * Buttons & Inputs: `8px` (`rounded-lg`)

---

## 3. User Journey & Navigation Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                            USER JOURNEY PIPELINE                            │
│                                                                             │
│  [ Upload CSV/XLSX ]                                                        │
│           │                                                                 │
│           ▼                                                                 │
│  [ Automated Profile & Quality Screen ]                                     │
│     • Review missing values, health score, column types                     │
│           │                                                                 │
│           ▼                                                                 │
│  [ Interactive Query Formulation ]                                          │
│     • Type question or pick suggested diagnostic prompt                     │
│           │                                                                 │
│           ▼                                                                 │
│  [ Live Agent Execution Stream ]                                            │
│     • Watch LangGraph steps: Planning ➔ Python Tools ➔ Validation           │
│           │                                                                 │
│           ▼                                                                 │
│  [ Evidence & Visualization Workspace ]                                     │
│     • Filter charts, inspect p-values, read synthesized insights            │
│           │                                                                 │
│           ▼                                                                 │
│  [ Export Executive Report (PDF / Markdown) ]                               │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.1 Primary Navigation Structure (Left Rail)
1. **Logo / Brand Header:** Nexora mark + version badge (`v1.0-mvp`).
2. **Datasets Hub (`/datasets`):** Upload new file, view dataset history, file metadata.
3. **Active Analysis Workspace (`/workspace/:id`):** Primary investigative environment.
4. **Reports Library (`/reports`):** Saved executive summaries and past briefings.
5. **System Settings (`/settings`):** LLM provider config, API keys, theme preferences.

---

## 4. Core Screen Specifications

### 4.1 Screen 1: Datasets Ingestion & Quality Inspector

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  Nexora  │ Datasets / q3_ecommerce_sales.csv                                │
├──────────┴──────────────────────────────────────────────────────────────────┤
│ ┌──────────────────────┐ ┌───────────────┐ ┌───────────────┐ ┌────────────┐ │
│ │ Health Score: 94% ⭐  │ │ 124,500 Rows  │ │ 18 Columns    │ │ 2.4% Nulls │ │
│ └──────────────────────┘ └───────────────┘ └───────────────┘ └────────────┘ │
│                                                                             │
│ ┌─────────────────────────────────────────────────────────────────────────┐ │
│ │ Column Schema & Quality Distribution                                    │ │
│ ├──────────────────────┬─────────────┬───────────┬─────────────┬──────────┤ │
│ │ Column Name          │ Type        │ Missing % │ Cardinality │ Outliers │ │
│ ├──────────────────────┼─────────────┼───────────┼─────────────┼──────────┤ │
│ │ order_id             │ ID (UUID)   │ 0.0%      │ 124,500     │ 0        │ │
│ │ customer_region      │ Category    │ 0.0%      │ 4           │ -        │ │
│ │ purchase_amount      │ Float ($)   │ 0.8%      │ 18,240      │ 142 (IQR)│ │
│ │ discount_rate        │ Percentage  │ 3.2%      │ 45          │ 0        │ │
│ └──────────────────────┴─────────────┴───────────┴─────────────┴──────────┘ │
│                                                                             │
│ [ 🚀 Launch AI Analysis Workspace ]                                         │
└─────────────────────────────────────────────────────────────────────────────┘
```

* **Header Summary:** Instant scorecard with 4 key metrics: Data Health Score (0–100%), Total Rows, Total Columns, and Overall Missing Ratio.
* **Schema Inspector Table:** Displays semantic types with colored badge indicators (`Numeric`, `Category`, `Timestamp`).
* **Warning Callouts:** Highlights anomalies (e.g., "Column `discount_rate` has 3.2% missing values; automated median imputation will be suggested").

### 4.2 Screen 2: AI Analysis Workspace (Triple-Pane Layout)

The core analysis cockpit uses a 3-pane responsive layout:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ [← Back]  q3_ecommerce_sales.csv   │ Session: Q3 Revenue Drop Investigation │
├─────────────────┬───────────────────────────────────┬───────────────────────┤
│ PANE 1 (25%):   │ PANE 2 (50%):                     │ PANE 3 (25%):         │
│ Agent Reasoning │ Interactive Visualizations        │ Evidence & Findings   │
│ & Step Stream   │                                   │                       │
├─────────────────┼───────────────────────────────────┼───────────────────────┤
│ ● Supervisor    │ [ Interactive Line / Bar Chart ]  │ ★ Core Finding        │
│   Plan created  │ Monthly Revenue by Region         │ "East Region Revenue  │
│                 │                                   │ dropped 38.4% in Sep" │
│ ✓ Data Profiler │   $400k ──┐                       │                       │
│   Schema valid  │   $300k   └──┐                    │ 📊 Evidence Chip      │
│                 │   $200k      └────────            │ N = 31,420 orders     │
│ ⚙ Statistical   │   $100k                           │ p = 0.0001 (t-test)   │
│   t_test() run  │         Jul   Aug   Sep           │                       │
│   Duration: 42ms│                                   │ 💡 Recommendation     │
│                 │ ┌───────────────────────────────┐ │ "Audit shipping delay │
│ ✓ Insight Agent │ │ Chart Controls: Group by | Zoom│ │ in East fulfillment" │
│   Synthesized   │ └───────────────────────────────┘ │                       │
├─────────────────┴───────────────────────────────────┴───────────────────────┤
│ [ Ask follow-up question...                                      ] [ Send ] │
└─────────────────────────────────────────────────────────────────────────────┘
```

* **Pane 1 (Left): Live Agent Reasoning Stream:** Shows step-by-step agent milestones. Active agents display pulsating indicator rings. Clicking any step expands the raw tool execution payload.
* **Pane 2 (Center): Interactive Visualization Canvas:** Renders Recharts-based visuals. Supports hovering for exact tooltip data, toggling series, zooming, and downloading as SVG/PNG.
* **Pane 3 (Right): Evidence & Insight Cards:** Displays structured insight cards. Each card contains a clear headline, quantitative proof, statistical significance indicator, and direct recommendation.

### 4.3 Screen 3: Executive Report / Briefing View

* Clean, distraction-free reading layout formatted for executive review.
* Displays:
  1. Executive Summary & Problem Scope.
  2. Key Findings & Quantitative Proof points.
  3. Visual Evidence Gallery (embedded high-resolution charts).
  4. Statistical Methodology & Guardrails Audit.
  5. Actionable Recommendations & Prioritized Next Steps.
* Top action bar: `[ Copy Markdown ]`, `[ Download PDF ]`, `[ Share Link ]`.

---

## 5. UI Component Specifications

### 5.1 Component: `QueryInput`
* **Visual:** Floating input container with glassmorphic background, subtle purple glow on focus.
* **Micro-Interactions:**
  * Auto-suggestion pill chips above the input (e.g., *"Find top revenue drivers"*, *"Analyze churn correlation"*).
  * Send button transforms into an animated stop/cancel button while agents are active.
  * Enter key submits; `Shift + Enter` creates newline.

### 5.2 Component: `AgentStepTimeline`
* **Visual:** Vertical timeline with connected glowing lines.
* **States:**
  * `Pending`: Dim gray icon, hollow circle.
  * `Active`: Pulsing indigo ring with live execution timer (`0.4s...`).
  * `Success`: Solid emerald checkmark badge with tool execution duration (`18ms`).
  * `Failed`: Rose warning badge with expandable error stack trace.

### 5.3 Component: `EvidenceCard`
* **Visual:** Dark slate card with a left border accent:
  * Green border: Statistically significant result ($p < 0.05$).
  * Amber border: Inconclusive / weak correlation ($p \ge 0.05$).
* **Elements:**
  * Headline: Bold, concise takeaway.
  * Proof Grid: 3-column micro-stat table (Baseline, New Value, Delta %).
  * Verification Drawer: Expandable disclosure containing Python tool name, parameters, degrees of freedom, and sample sizes.

### 5.4 Component: `ChartContainer`
* **Visual:** Bordered card with header title, subtitle, and action buttons (`PNG`, `SVG`, `Fullscreen`).
* **Interactions:**
  * Hover tooltip with formatted currency/percentage values.
  * Clickable legend items to toggle series visibility.
  * Responsive container recalculating layout on window resize.

---

## 6. Feedback States: Loading, Empty & Error

| State Type | UI Representation & Copy | User Recovery Action |
| :--- | :--- | :--- |
| **Empty State (No Datasets)** | Friendly graphic showing a clean tabular spreadsheet; text: *"No datasets uploaded yet."* | Prominent `[ Drag & Drop CSV / Browse Files ]` button. |
| **Empty State (No Session)** | Grid of 4 suggested investigative prompts tailored to the uploaded dataset's schema. | One-click prompt chips populate the query input automatically. |
| **Streaming / Loading State** | Active agent timeline displays live status: *"StatisticalAgent running Pearson correlation across 14 numeric columns..."* | User can inspect in-flight steps or click `[ Cancel Analysis ]`. |
| **Tool Execution Error** | Yellow alert card: *"DataQualityAgent detected non-numeric characters in column 'revenue'. Coercing 14 rows to NaN."* | Option to review cleaned data or specify custom handling rule. |
| **Critical Server Error** | Red banner: *"LLM connection timed out after 3 retry attempts."* | Action button `[ Retry Query with Fallback Model ]`. |

---

## 7. Responsive Behavior & Breakpoints

* **Desktop Wide ($\ge 1440\text{px}$):** Default triple-pane layout (25% Agent Stream, 50% Visual Canvas, 25% Evidence Cards).
* **Desktop Standard ($1024\text{px} - 1439\text{px}$):** Split layout with collapsable Agent Stream sidebar; Evidence Cards docked beneath charts.
* **Tablet ($768\text{px} - 1023\text{px}$):** Tabbed interface (`[ Reasoning ]`, `[ Visualizations ]`, `[ Report ]`).
* **Mobile ($< 768\text{px}$):** Read-only report view; allows viewing existing reports and charts with swipe navigation. Upload and interactive querying prompted to use desktop.

---

## 8. Accessibility (a11y) & Usability Standards

* **WCAG 2.1 AA Compliance:** All text elements maintain a minimum contrast ratio of **4.5:1** against dark card backgrounds; large headers maintain **3.0:1**.
* **Chart Color-Blind Safety:** Chart color palette is selected to be distinguishable under Deuteranopia and Protanopia conditions. Data points feature distinct marker shapes (circles, squares, triangles) in addition to color encoding.
* **Keyboard Navigation:** Full tab order across inputs, buttons, and expandable evidence drawers; modal dialogs lock focus and dismiss on `Escape`.
* **Screen Reader Tags:** ARIA live regions (`aria-live="polite"`) used for streaming agent thought logs so assistive technologies can read milestone completions without spamming the user.
