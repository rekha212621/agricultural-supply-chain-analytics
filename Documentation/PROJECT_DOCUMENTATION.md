# Agricultural Supply Chain Analytics Dashboard

## 1. Project Overview

The Agricultural Supply Chain Analytics Dashboard is a Power BI project designed to analyze agricultural production, distributor supply performance, wastage, and retail sales.

The dashboard brings together three datasets to provide insights into crop production, supply efficiency, district-level performance, and retail demand.

## 2. Project Objectives

- Analyze agricultural production across crops, districts, and years.
- Monitor quantities dispatched and received by distributors.
- Calculate supply efficiency and wastage percentages.
- Analyze retail sales, revenue, and crop-wise selling prices.
- Present insights through interactive Power BI visualizations and filters.

## 3. Tools and Technologies

- Microsoft Power BI
- Power Query for data preparation
- DAX for calculations and measures
- CSV files for dataset storage
- GitHub for project version control and documentation

## 4. Datasets

### 4.1 Farm Production

*Data type:* Real agricultural data.

This dataset supports the analysis of agricultural production across different crops, districts, seasons, and years.

Key fields include:
- Year
- District
- Crop
- Season
- Area cultivated (hectares)
- Production (tonnes)
- Yield (tonnes per hectare), where available

The original dataset source and applicable license should be recorded before public redistribution.

### 4.2 Distributor Supply

*Data type:* Synthetic data created for demonstration.

Key fields:
- Date
- District
- Crop
- Quantity dispatched (kg)
- Quantity received (kg)
- Quantity wasted (kg)

This dataset is used to evaluate distributor supply performance and wastage.

### 4.3 Retail Sales

*Data type:* Synthetic data created for demonstration.

Key fields include:
- Date
- District
- Crop
- Season
- Quantity available
- Quantity sold
- Price per kg
- Sales revenue

This dataset supports retail demand, sales, and pricing analysis.

*Data disclaimer:* Distributor Supply and Retail Sales data are simulated and should not be interpreted as verified real-world transactions.

## 5. Dashboard Pages

### Page 1: Farm Production

KPIs:
- Total Production
- Total Cultivated Area
- Average Yield

Visualizations:
- Total production by crop
- Cultivated area by district
- Production by district

Filters:
- Crop
- District
- Year

### Page 2: Distributor Supply

KPIs:
- Total Quantity Dispatched
- Total Quantity Received
- Total Quantity Wasted
- Supply Efficiency (%)
- Wastage (%)

Visualizations:
- Dispatched versus received quantity by district
- Supply trends over time

Filters:
- Crop
- District

### Page 3: Retail Sales

KPIs:
- Total Quantity Sold
- Total Sales Revenue
- Average Selling Price
- Total Quantity Available

Visualizations:
- Quantity sold by crop
- Sales trends over time
- Average selling price by crop

Filters:
- Crop
- District

## 6. Key DAX Measures

### Supply Efficiency %

DAX
Supply Efficiency % =
DIVIDE(
    SUM('Distributor Supply'[Quantity_Received_kg]),
    SUM('Distributor Supply'[Quantity_Dispatched_kg]),
    0
)


This measure calculates the percentage of dispatched quantity that was received.

### Wastage %

DAX
Wastage % =
DIVIDE(
    SUM('Distributor Supply'[Quantity_Wasted_kg]),
    SUM('Distributor Supply'[Quantity_Dispatched_kg]),
    0
)


This measure calculates recorded wastage as a percentage of dispatched quantity.

Format both measures as percentages in Power BI.

## 7. Data Model

A shared Crop table connects to the Crop columns in the Farm Production, Distributor Supply, and Retail Sales tables.

This model enables crop-based filtering across all three dashboard pages.

District and date filters should be configured according to the relationships and intended behavior of the dashboard.

## 8. Repository Structure

- Agricultural_Supply_Chain_Analytics.pbix : Power BI dashboard
- data/ : CSV datasets and dataset notes
- docs/PROJECT_DOCUMENTATION.md : Project documentation
- README.md : Project overview

## 9. Limitations

- Distributor Supply and Retail Sales datasets are synthetic.
- Results from synthetic data demonstrate analytical functionality, not actual market performance.
- Conclusions from the Farm Production dataset depend on its coverage, accuracy, source, and reporting period.

## 10. Conclusion

This project demonstrates the use of Power BI, data modeling, DAX, and interactive visualizations to analyze agricultural production and downstream supply-chain performance in a single dashboard.

## 11. Future Enhancements

- Integrate verified distributor and retail transaction data.
- Add forecasting for crop demand and production.
- Analyze seasonal price variations.
- Add more detailed supply-chain performance indicators.
