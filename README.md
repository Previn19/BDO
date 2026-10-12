# Companies House Analysis

An analysis of a sample of Companies House data (company profiles, officers and charges) to find insights that could help BDO identify potential new clients and better understand its existing client population. The notebook covers contextual research, data quality checks and cleaning, profiling of the sample, a prospecting shortlist, and risk and opportunity signals.

**Built with:** Python, pandas, plotly.

## Contents

### 1 — Contextual research and notes
Research done before touching the data, so the questions asked of it matter to BDO.

- **1.1 — What is Companies House?** What the register is, how the data can be accessed, and what it does and doesn't cover.
- **1.2 — Company Profiles:** What the profiles sheet holds and why it is used as the starting point.
- **1.3 — Company Officers:** What the officers sheet holds and what it can show.
- **1.4 — Company Charges:** What a charge is and what the charges sheet records.
- **1.5 — Who BDO is:** How BDO works, its service lines, its mid-market client base, where its offices are, and the lines of enquiry this research leads to.

### 2 — Exploratory analysis
Checking the quality of the data and cleaning it before any conclusions are drawn.

- **2.1 — Shape of the data:** Rows and columns in each of the three sheets.
- **2.2 — Initial data exploration:** How many distinct companies each sheet covers and whether the sheets can be joined.
- **2.3 — Repeated rows in Profiles:** Finding exact duplicates, investigating the companies whose rows disagree, and building a clean one-row-per-company table.
- **2.4 — Officers and Charges:** Whether these sheets hold every record, plus duplicate and missing-ID checks.
- **2.5 — Data types:** Columns stored as text that should hold dates, and converting them.
- **2.6 — Completeness:** How much of each column is missing.
- **2.7 — Age of the data:** Using the latest recorded events to estimate how current the data is.
- **2.8 — Summary of data quality findings:** Every issue found, how it was found, and what was done about it.

### 3 — Profiling: what does the sample look like?
Describing the 63 companies by age, status, size, location and sector.

- **3.1 — Company age:** When the companies were created, and what that says about the sample.
- **3.2 — Company status:** How many are still active, dissolved, in liquidation or in insolvency proceedings.
- **3.3 — Size:** Accounts type and legal form as the closest available indicators of size.
- **3.4 — Location:** Registered office postcode areas, and the split between London and the regions.
- **3.5 — Sector:** Cleaning and validating SIC codes, then grouping them into broad sectors.
- **3.6 — Metrics considered but not explored:** Measures ruled out, and why the data wasn't reliable enough.

### 4 — Prospecting: who could BDO approach?
Narrowing the 63 companies to a shortlist in three stages.

- **4.1 — Size:** Keeping active companies that file full or group accounts.
- **4.2 — Type of organisation:** Labelling each prospect as private, public, investment trust or not-for-profit, and which BDO team might fit.
- **4.3 — Location:** Matching each prospect to its nearest BDO office.
- **4.4 — Shortlist:** The private companies nearest a regional office, with a funnel chart of each step.

### 5 — Risk: signals of distress and opportunity
Whether the data distinguishes active from non-active companies, and where BDO's own research points to opportunities.

- **5.1 — Overdue filings and insolvency history:** Current overdue flags and insolvency links.
- **5.2 — Outstanding charges:** Comparing active and non-active companies, with the calculation cross-checked against the charge records.
- **5.3 — External market signals:** Matching active companies to sectors highlighted in BDO's published research.

### 6 — Shortlisted regional companies with opportunity indicators
Which of the shortlisted companies sit in one of the researched sectors.

### 7 — Techniques used and what I would do next
The methods applied, ideas set aside to keep the scope manageable, and what I would do with more time.

### 8 — Other data I would use alongside this
External sources that would address the gaps in this data, such as revenue figures and insolvency notices.

## Notes

- The notebook reads `Dataset.xlsx` (sheets: company profiles, company officers, company charges). The data file is not included in this repo.
- All cells have been run, so the tables and charts can be read without running the notebook.
