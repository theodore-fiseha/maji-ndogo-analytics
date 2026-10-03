# Maji Ndogo: Python Foundations

## The Business Problem

Maji Ndogo's Ministry of Agriculture oversees roughly 5,654 smallholder farms, and yields vary widely with no clear explanation. Harvest data arrived as handwritten field notes: inconsistent crop names, totals worked out by hand, and no shared record anyone could audit.

The Ministry needed two things. First, a season record that Finance could trust, with every figure traceable in code. Second, the logic for a Digital Twin, a programmable model of the farms that can track fuel, planting progress, machinery and harvests without someone recalculating by hand.

## The Tech Stack

**Core Python only — no libraries.**

- **Data types and operators** for the harvest, cost, revenue and profit calculations
- **String methods and f-string formatting** to clean messy crop names and produce Finance-ready summaries
- **Lists, tuples, sets and dictionaries**, each chosen for a specific job: lists for ordered records, tuples for field records that must not change, sets for removing duplicates and comparing crop plans, and nested dictionaries for the regional registry
- **Conditionals, loops and comprehensions** for decisions, scanning grids and filtering data

Working without libraries was deliberate. Every result comes from logic I wrote and can explain line by line, which is the foundation any later work with pandas or machine learning depends on.

## The Deliverable

### 1. A season record Finance can trust

Two test fields, wheat and potato, became a formatted summary: 5,650 kg harvested, $9,140.00 revenue, $5,420.00 profit and a 59.3% margin. Currency and percentage formatting are handled in code, so the figures read the same every time.

![Figure 1](images/01-season-summary.jpg)

### 2. Harvests organised for analysis

As more fields report, their harvests go into a list that the code can slice, rank and total in one pass. The largest field and the regional total come out of the data rather than a manual scan.

![Figure 2](images/02-season2-summary.jpg)

### 3. A fuel gauge that makes decisions

The Digital Twin classifies any tank as Empty, Low, OK or Full from just its fuel level and capacity. Empty is checked first, so a dry tank is never misreported as merely low.

![Figure 3](images/03-season3-summary.jpg)

### 4. A tractor that stops at obstacles

The tractor plants each cell along a row and stops the moment it reaches an obstacle, such as the irrigation pipe. It never plants past it, and on a clear row it runs to the end.

![Figure 4](images/04-season4-summary.jpg)

### 5. Crop plans compared instantly

Two farms' messy, repetitive crop lists become three clean answers: what both farms grow, what only one grows, and every crop across both. Sets remove the duplicates automatically.

![Figure 5](images/05-season5-summary.jpg)

### 6. A registry that remembers the season

Each farm has its own record of crop weights. A new reading either starts a fresh entry or adds to the existing total, so a farm reporting wheat twice never overwrites its own history.

![Figure 6](images/06-season6-summary.jpg)

## The "So What?"

The Ministry went from a notepad of figures to a season record whose every number can be traced back to code, ready for Finance and for the next programmer. The Digital Twin can now check its own fuel, track planting progress, avoid obstacles and keep a running harvest record for every farm. That is the groundwork for scaling from two test fields to all 5,654 farms without adding manual work.

