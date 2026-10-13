# Companies House Analysis

An analysis of a sample of Companies House data (company profiles, officers and charges) for BDO. The notebook has two aims:

1. **Check the quality of the data**, clean it where possible, and state the problems clearly where it can't be fixed.
2. **Build a repeatable filter, as a proof of concept,** that narrows Companies House data down to companies that could fit BDO's mid-market client profile.

**Built with:** Python, pandas, plotly, Jupyter.

## Headline results

- **Data quality:** The Profiles sheet has 1,027 rows but only 63 companies. Removing 957 exact duplicates and 7 conflicting rows leaves one row per company.
- **Filter:** 63 companies → 52 active → 46 filing full or group accounts → 28 private companies → **19 nearest a regional BDO office**. 5 of the 19 sit in sectors BDO has published research on.
- **Main limitation:** Companies House data has no revenue, so the filter can't yet check companies against BDO's £10m to £500m mid-market definition. The sample is also small and made up of very old companies, so the method matters more than the shortlist.

## Contents

### Setting up the notebook
Imports, loading the three sheets from `Dataset.xlsx`, and the BDO colours used in every chart.

### 1 — Contextual research and notes
Research done before working with the data, so the questions asked of it matter to BDO.

- **1.1 — What is Companies House?** What the register is, how the data can be accessed, and what it does and doesn't cover.
- **1.2 — Company Profiles:** What the profiles sheet holds and why it is used as the starting point.
- **1.3 — Company Officers:** What the officers sheet holds and what it can show.
- **1.4 — Company Charges:** What a charge is and what the charges sheet records.
- **1.5 — Who BDO is, and what that means for this analysis:** How BDO works, where it operates, and how its priorities lead to each step of the filter.

### 2 — Data quality and cleaning
Building a data dictionary against the Companies House API documentation, then checking and cleaning the data before any conclusions are drawn.

- **2.1 — Shape of the data:** Rows and columns in each of the three sheets.
- **2.2 — Initial data exploration:** How many distinct companies each sheet covers and whether the sheets can be joined.
- **2.3 — Repeated rows in Profiles:** Finding exact duplicates, investigating the 7 companies whose rows disagree, and building a clean one-row-per-company table.
- **2.4 — Officers and Charges:** Whether these sheets hold every record compared with the Companies House totals, plus duplicate and missing-ID checks.
- **2.5 — Data types:** Finding columns stored as text that should hold dates, and converting `date_of_creation`.
- **2.6 — Completeness:** How much of each column is missing.
- **2.7 — Age of the data:** Using the latest recorded events to estimate how current the data is.
- **2.8 — Summary of data quality findings:** Every issue found, how it was found, and what was done about it.

### 3 — Profiling: what does the sample look like?
Describing the 63 companies by age, status, size, location and sector.

- **3.1 — Company age:** When the companies were created, and what that says about the sample.
- **3.2 — Company status:** How many are still active, dissolved, in liquidation or in insolvency proceedings.
- **3.3 — Size:** Accounts type and legal form as the closest available indicators of size.
- **3.4 — Location:** Registered office postcode areas, and the split between London and the regions.
- **3.5 — Sector:** Counting SIC codes per company, removing invalid codes, and comparing sectors for companies with one code and companies with several.
- **3.6 — Metrics considered but not explored:** Measures ruled out, and why the data wasn't reliable enough.

### 4 — Building a filter to find potential clients (proof of concept)
Five steps, each linked to one of BDO's priorities. Steps 1 to 4 remove companies; step 5 only flags them.

- **4.1 — Steps 1 and 2:** Keeping active companies that file full or group accounts.
- **4.2 — Preparing step 3:** Labelling each prospect as a private company, public company, investment trust or not-for-profit.
- **4.3 — Preparing step 4:** Matching each prospect to its nearest BDO office.
- **4.4 — Applying steps 3 and 4:** The private companies nearest a regional office, with a funnel chart of each step.
- **4.5 — Step 5:** Flagging companies in sectors covered by BDO's published research (finance and insurance, sport, retail).
- **4.6 — Summary of the filter:** How many companies each step removes, and how the filter could be tested.

### 5 — Techniques I used and what I would do next
The methods applied, ideas set aside to keep the scope manageable, and what I would do with more time.

### 6 — Other data I would use alongside this
External sources that would fill the gaps in this data, such as revenue figures, insolvency notices and BDO's own client records.

## Notes

- The notebook reads `Dataset.xlsx` (sheets: company profiles, company officers, company charges). The data file is not included in this repo.
- All cells have been run, so the tables and charts can be read without running the notebook.
- Charts are saved as images so they show on GitHub and nbviewer. To run the notebook yourself you'll need `pandas`, `plotly`, `openpyxl` (to read the Excel file) and `kaleido` (to save the charts as images).
