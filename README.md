![overview page](Capture4.png)
![Insights and details page](overview.png)

# Tech Layoffs Dashboard (2020 to 2026)

An interactive Power BI dashboard that shows which industries, countries, companies and company stages were hit hardest by tech layoffs.

**Data:** Kaggle layoffs dataset ([add link]), 4,616 layoff events between March 2020 and September 2026.
**Tools:** Power Query (cleaning), DAX (measures), Power BI Desktop (dashboard).

## Dashboard



## Business questions

1. When did layoffs peak, and how did they trend over time?
2. Which industries were hit hardest?
3. Which countries and companies account for the most layoffs?
4. Which company stages were most affected?
5. How many companies laid off 100% of their staff?

## Key findings

- Layoffs peaked in January 2023 (about 89,700 people), and 2023 was the worst year (about 265,700).
- Post-IPO companies account for about 63% of reported layoffs, led by Amazon, Intel, Meta and Microsoft.
- The United States accounts for about 71% of reported layoffs.
- Shutdowns (companies that laid off 100% of staff) are led by Finance (47 companies) and Food (40), which rank only 6th and 7th for headcount lost.

## Data cleaning (Power Query)

- Trimmed and cleaned all text columns.
- Fixed company name inconsistencies (for example, LOOP/Loop and TikTok/Tiktok).
- Standardized country names (UAE merged into United Arab Emirates).
- Replaced blank industry, country and stage values with "Unknown".
- Converted dates using the US locale, because the source stores them as month/day/year text.
- Removed the source and date_added columns, then removed 2 exact duplicate events (4,618 rows down to 4,616).
- Left blank headcounts as nulls instead of replacing them with 0.
- Added a Company Status column: Shut down (100% laid off), Still operating, or Unknown.

## Data model and measures

A Dim Date calendar table is linked to the layoffs table by date (one-to-many). Measures include Total Laid Off, Layoff Events, Events With Headcount, Companies Affected, Companies Shut Down, Avg Layoff Size, % of Total Laid Off, and year-over-year change.

## Limitations

- About a third of events have no reported headcount, so all totals are minimums.
- "Shut down" means a company laid off 100% of its staff in an event. It is a strong sign of closure, not proof.
- 2026 only runs to September, so it is not comparable with full years.

## Files

- tech-layoffs-dashboard.pbix: open it in Power BI Desktop
- overview.png, insights-details.png: screenshots

## Author

[Your name] | [LinkedIn link]
