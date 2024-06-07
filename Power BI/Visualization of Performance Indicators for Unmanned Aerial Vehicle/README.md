# Power BI Data Visualization and Interactive Reports

This repository provides a comprehensive guide on visualizing data, creating interactive reports, and utilizing various visualization techniques in Power BI.

## Table of Contents

- [Introduction](#introduction)
- [Tasks Overview](#tasks-overview)
- [Creating and Customizing Visualizations](#creating-and-customizing-visualizations)
  - [Bar Charts, Pie Charts, and Tree Maps](#bar-charts-pie-charts-and-tree-maps)
  - [Combination Charts](#combination-charts)
- [Creating Slicers](#creating-slicers)
- [Map Visualizations](#map-visualizations)
  - [Bubble Maps](#bubble-maps)
  - [Shape Maps](#shape-maps)
- [Matrices and Tables](#matrices-and-tables)
- [Specialized Charts](#specialized-charts)
  - [Scatter Charts](#scatter-charts)
  - [Waterfall Charts](#waterfall-charts)
  - [Funnel Charts](#funnel-charts)
- [Modifying Colors and Formatting](#modifying-colors-and-formatting)
  - [Conditional Formatting](#conditional-formatting)
- [Page Layout and Formatting](#page-layout-and-formatting)
  - [Adding Static Elements](#adding-static-elements)
- [Model View](#model-view)
- [Data Tab](#data-tab)
- [Report Tab](#report-tab)
- [Creating Calculated Tables and Measures](#creating-calculated-tables-and-measures)
- [Adding Images, Shapes, and Cards](#adding-images-shapes-and-cards)
- [Creating Groups](#creating-groups)
- [Conclusion](#conclusion)

## Introduction

This guide helps you understand how to visualize data, create interactive reports, and utilize various visualization tools in Power BI, enabling effective data analysis and presentation.

## Tasks Overview

### Visualizing Data

1. Create and customize simple visualizations.
2. Create new bar charts, pie charts, and tree maps.
3. Create combination charts.

### Slicers

1. Create slicers to filter data interactively.

### Map Visualizations

1. Create bubble maps.
2. Create shape maps.

### Matrices and Tables

1. Utilize matrices and tables for detailed data presentation.

### Specialized Charts

1. Create scatter, waterfall, and funnel charts.

### Modifying Colors and Formatting

1. Apply conditional formatting.

### Page Layout and Formatting

1. Add static elements such as text boxes and shapes.

## Creating and Customizing Visualizations

### Bar Charts, Pie Charts, and Tree Maps

1. Create and customize bar charts, pie charts, and tree maps for categorical data visualization.

### Combination Charts

1. Create combination charts to compare two sets of measures using dual Y-axes.

## Creating Slicers

1. Use slicers for filtering data displayed in other report visualizations.

## Map Visualizations

### Bubble Maps

1. Create bubble maps to visualize data geographically.

### Shape Maps

1. Create shape maps to show data distribution across different regions.

## Matrices and Tables

1. Use matrices and tables to display detailed data in a structured format.

## Specialized Charts

### Scatter Charts

1. Create scatter charts to show the relationship between two numerical variables.

### Waterfall Charts

1. Create waterfall charts to visualize the cumulative effect of sequential values.

### Funnel Charts

1. Create funnel charts to represent data across multiple stages.

## Modifying Colors and Formatting

### Conditional Formatting

1. Apply conditional formatting to charts and visuals to enhance data interpretation.

## Page Layout and Formatting

### Adding Static Elements

1. Add text boxes, shapes, and smart narrative visuals to reports.

## Model View

1. Use the model view to see all tables, columns, and relationships in your model.
2. Manage complex relationships between tables.

## Data Tab

1. Inspect, explore, and understand data in the Power BI Desktop model.

## Report Tab

1. Create and customize various chart types for data visualization.

## Creating Calculated Tables and Measures

1. Use DAX (Data Analysis Expressions) to create calculated columns, tables, and measures.

### Examples of Measures

1. Total Order: `Total_Order = SUM('Sales Data'[OrderQuantity])`
2. Bulk Orders: `Bulk Orders = CALCULATE([Total_Order], 'Sales Data'[OrderQuantity]>1)`
3. Red Sales: `Red Sales = CALCULATE([Quantity Sold], 'Product Lookup'[ProductColor] == "Red")`
4. Quantities Sold: `Quantities Sold = DISTINCTCOUNT('Sales Data'[ProductKey])`
5. Week End: `Week_End = CALCULATE([Total_Order], 'Calendar Lookup'[Day Name]="Saturday")`
6. Average Product Price: `Average product price = AVERAGE('Product Lookup'[ProductPrice])`
7. Overall Product Price: `Overall Product Price = CALCULATE([Average product price], ALL('Product Lookup'))`
8. High Ticket Orders: `High Ticket Orders = CALCULATE([Average product price], 'Product Lookup'[ProductPrice]>714.44)`
9. Total Revenue: `Total Revenue = SUMX('Sales Data', 'Sales Data'[Retail_price]*'Sales Data'[OrderQuantity])`
10. Average Revenue per Customer: `Average Revenue per Customer = DIVIDE([Total Revenue], [Total customer])`
11. Total Cost: `Total Cost = SUMX('Sales Data', RELATED('Product Lookup'[ProductCost])*'Sales Data'[OrderQuantity])`
12. Total Profit: `Total Profit = [Total Revenue]-[Total Cost]`
13. YTD Revenue: `YTD Revenue = CALCULATE([Total Revenue], DATESYTD('Calendar Lookup'[Date]))`
14. Day Rolling Revenue: `Day Rolling Revenue = CALCULATE([Total Revenue], DATESINPERIOD('Calendar Lookup'[Date], MAX('Calendar Lookup'[Date]), -10, DAY))`
15. Previous Month Revenue: `Previous Month Revenue = CALCULATE([Total Revenue], DATEADD('Calendar Lookup'[Date], -1, MONTH))`

## Adding Images, Shapes, and Cards

1. Insert images, shapes, and cards to enhance report visuals.

## Creating Groups

1. Group multiple visuals for better organization and presentation.

## Conclusion

This repository provides a comprehensive guide on visualizing data, creating interactive reports, and utilizing various visualization techniques in Power BI, helping you create insightful and effective data presentations.


