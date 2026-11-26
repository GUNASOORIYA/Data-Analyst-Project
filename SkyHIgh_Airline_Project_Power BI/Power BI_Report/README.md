# Power BI Report

**File:** `SkyHigh_Airline_Report.pbix` (about 2.2 MB)

The finished Power BI report for the SkyHigh Airlines project. It has three pages.

| Page | Name | What it shows |
|---|---|---|
| 1 | Executive Summary | Total Flights, Total Passengers, Overall Revenue, Avg. Delay, Flights by Status, Monthly Revenue Trend, map of flights by airport |
| 2 | Flight Operations | Avg. Delay by Route, Avg. Delay by Month, Aircraft Type usage, Top 5 Delayed Airports, On-Time Rate and Avg. Delay cards |
| 3 | Customer Insights | Avg. Feedback Score, Frequent Flyer Rate, Total Passengers, Avg. Age, Feedback Score Distribution, Ticket Class by Gender, Frequent Flyer vs Feedback Score |

## How to open

1. Install **Power BI Desktop** (free, Windows only): https://powerbi.microsoft.com/desktop/
2. On GitHub, click `SkyHigh_Airline_Report.pbix`, then **Download raw file**.
3. Double-click the downloaded file to open it in Power BI Desktop.
4. If a data-source message appears, go to **Home > Transform data > Data source settings** and point each source to the matching CSV in the `Data` folder, then click **Refresh**.

A .pbix file cannot be previewed on GitHub. Screenshots of all pages are in the `Images` folder.

## Data model

Tables: `Airline_Airports`, `Airline_Flights`, `Airline_Passengers`, `Airline_Revenue`.

- `Airline_Airports[Airport Code]` to `Airline_Flights[Source]` (one-to-many)
- `Airline_Flights[Flight ID]` to `Airline_Passengers[Flight ID]` (one-to-many)
- `Airline_Flights[Flight ID]` to `Airline_Revenue[Flight ID]` (one-to-many)

DAX measures are listed in [`../Docs/DAX_Measures.md`](../Docs/DAX_Measures.md).

## Requirements

- Power BI Desktop (current version)
- The map visual needs internet access (Bing Maps) and Map visuals enabled under **File > Options > Security**
