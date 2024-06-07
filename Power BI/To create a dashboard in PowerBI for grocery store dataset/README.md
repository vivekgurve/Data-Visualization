# Power BI Dashboard for Grocery Store Dataset

This repository contains instructions and resources for creating a comprehensive dashboard in Power BI using a grocery store dataset.

## Table of Contents

- [Introduction](#introduction)
- [Data Modeling](#data-modeling)
  - [Conceptual Data Modeling](#conceptual-data-modeling)
  - [Logical Data Modeling](#logical-data-modeling)
  - [Physical Data Modeling](#physical-data-modeling)
  - [Core Modeling Features](#core-modeling-features)
  - [Usability Features](#usability-features)
- [Steps to Create the Dashboard](#steps-to-create-the-dashboard)
  - [Import Sample Data](#import-sample-data)
  - [Configure Table and Column Properties](#configure-table-and-column-properties)
  - [Create Calculated Columns and Tables](#create-calculated-columns-and-tables)
  - [Create Quick Measures](#create-quick-measures)
  - [Create Visualization](#create-visualization)
- [Data Transformation Techniques](#data-transformation-techniques)
- [Save Your Work](#save-your-work)
- [Power BI Desktop Views](#power-bi-desktop-views)
  - [Report View](#report-view)
  - [Data View](#data-view)
  - [Model View](#model-view)
- [Creating Calculated Tables and Measures](#creating-calculated-tables-and-measures)
- [Adding Relationships](#adding-relationships)
- [Creating Visuals](#creating-visuals)
  - [Adding Images, Shapes, and Cards](#adding-images-shapes-and-cards)
  - [Creating Slicers](#creating-slicers)
  - [Creating Various Charts](#creating-various-charts)
- [Conclusion](#conclusion)
- [License](#license)

## Introduction

This guide walks you through the process of creating a dashboard in Power BI for a grocery store dataset, from data modeling to creating visualizations.

## Data Modeling

### Conceptual Data Modeling

Defines the overall structure of your business data. Entities such as customers, products, and transactions are identified and their relationships are established.

### Logical Data Modeling

Adds specific attributes to each entity and defines relationships between these attributes.

### Physical Data Modeling

Implements the logical data model in a specific database tool and data storage technology.

### Core Modeling Features

- Support for different types of data models
- Custom field creation
- User-defined relationships
- Model subsets and validation

### Usability Features

- Object query
- Import/export capabilities
- Graphical interface
- Diagram auto-layout
- Query creation with ordering, grouping, filters, and joins

## Steps to Create the Dashboard

### Import Sample Data

1. Go to `Get Data` and import the grocery store dataset.
2. Remove empty rows and use the first row as headers.

### Configure Table and Column Properties

1. Define column quality.
2. Remove duplicates and errors.

### Create Calculated Columns and Tables

1. Create new columns such as `Delivery Days` and tables like `State_Total_Orders`.

### Create Quick Measures

1. Use DAX expressions to create measures for calculations and filters.

### Create Visualization

Design visual representations of your data using Power BI's visualization tools.

## Data Transformation Techniques

- Remove null values
- Replace values
- Extract components (e.g., month and year from date columns)
- Group by specific attributes
- Reverse rows
- Move columns
- Sort data

## Save Your Work

Save and apply your changes from the Power Query Editor.

## Power BI Desktop Views

### Report View

Build visualizations using your data queries.

### Data View

View and manage data in the report in data model format.

### Model View

Visualize and manage the relationships in your data model.

## Creating Calculated Tables and Measures

- **Bulk Orders**: `Bulk Orders = CALCULATE([Total_Order], 'Orders'[Quantity] > 3)`
- **Total Profit**: `Total Profit = SUM(Orders[Profit])`
- **Total Order**: `Total_Order = SUM(Orders[Quantity])`

## Adding Relationships

Create relationships between tables either by managing relationships or by dragging and dropping columns.

## Creating Visuals

### Adding Images, Shapes, and Cards

Insert images, shapes, and create cards for key metrics like total orders, sales, profit, and returns.

### Creating Slicers

Create slicers for filtering data, such as by product year.

### Creating Various Charts

- **Doughnut Chart**: Displays the relationship of parts to a whole.
- **Pie Chart**: Round-shaped chart showing category data.
- **Clustered Column Chart**: Combines line and column charts.
- **Clustered Bar Chart**: Horizontal bar chart showing clusters of data.
- **Map Visualizations**: Bubble maps showing data by city and country.

## Conclusion

This repository provides a comprehensive guide to creating a Power BI dashboard for a grocery store dataset, helping you transform and visualize your data effectively.


