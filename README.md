# Sales Performance – Power BI Project (.pbip)
![Dashboard](Screenshot%202026-11-23%20161104.png)

Rebuild of the "Sales Performance Dashboard" web artifact using the same data
(Jan 2023 – Dec 2025, delivered orders, INR).

## Open it
1. Power BI Desktop (current release) → File → Options → Preview features →
   enable **Power BI Project (.pbip) save option** and **Store reports using enhanced metadata format (PBIR)**, then restart.
2. Unzip, open `Sales Performance.pbip`, and click **Refresh** once.
   The data is embedded in the model (Power Query), so no file paths or credentials are needed.

## Model (star schema)
- `Fact Sales` – month × region × category × segment (sales, profit, delivered orders, units, all orders)
- `Fact Product Sales` – year × region × product × segment (feeds Top 8 products)
- `Dim Calendar`, `Dim Year`, `Dim Region`, `Dim Category`, `Dim Segment`, `Dim Product`
- `_Measures` – KPIs, prior-year comparison, return/cancel rate, insight text

## Report page
Slicers (Year, Region, Category, Customer segment) · 5 KPI cards with vs-prior-year deltas ·
Monthly sales & profit · Sales by segment · Sales by category · Sales by region · Top 8 products · Insight cards.

## Using your own data
`data/*.csv` hold the same rows. In Power Query, replace the `Source` step of
`Fact Sales` / `Fact Product Sales` with `Csv.Document(File.Contents("<path>"))`.
