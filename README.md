# 🚕 NYC Taxi Analytics Dashboard — Power BI

An interactive **NYC Taxi Data Analytics Dashboard** built using Microsoft Power BI to analyze taxi trips, revenue, passenger behavior, trip duration, payment methods, pickup zones, and operational patterns.

The project demonstrates an end-to-end data analytics workflow including data cleaning, transformation, data modeling, DAX measures, and interactive dashboard development.

---

## 📊 Project Overview

The NYC taxi dataset contains detailed trip-level information such as:

- Pickup and drop-off timestamps
- Passenger count
- Trip distance
- Pickup and drop-off locations
- Fare amount
- Tips
- Tolls
- Taxes
- Total trip revenue
- Payment type
- Rate code
- Vendor information

The goal of this project is to transform raw taxi trip data into an interactive business intelligence dashboard that helps users understand **trip patterns, revenue performance, customer behavior, and geographic activity**.

---

## 🎯 Business Objectives

The dashboard is designed to answer questions such as:

- How many taxi trips were recorded?
- What is the total revenue generated?
- How does revenue change over time?
- Which hours have the highest trip activity?
- Which boroughs generate the most revenue?
- Which pickup zones have the highest activity?
- What is the average trip distance?
- What is the average trip duration?
- How many passengers travel per trip on average?
- Which payment methods are most frequently used?
- How much revenue is generated per mile?
- How much of the revenue comes from tips?

---

## 🗂️ Dataset

The project uses NYC taxi trip data containing trip-level transportation and financial information.

### Main dataset

**Taxi Trip Data**

Important fields include:

- `vendor_id`
- `pickup_datetime`
- `dropoff_datetime`
- `passenger_count`
- `trip_distance`
- `rate_code`
- `store_and_fwd_flag`
- `payment_type`
- `fare_amount`
- `extra`
- `mta_tax`
- `tip_amount`
- `tolls_amount`
- `surcharge`
- `total_amount`
- `pickup_location_id`
- `dropoff_location_id`

### Zone dataset

A separate taxi zone lookup table was used containing:

- `zone_id`
- `zone_name`
- `borough`

The raw datasets are not included in this repository because of their very large file sizes.

---

## 🧹 Data Preparation

The data was prepared using **Power Query in Power BI**.

### Transformations performed

- Corrected column data types
- Created trip duration
- Created trip duration in hours
- Extracted pickup date
- Extracted pickup hour
- Removed invalid trip durations
- Removed trips with invalid distance values
- Removed invalid passenger counts
- Removed unnecessary geographic geometry data
- Removed duplicate taxi zone IDs
- Created a separate date dimension
- Established relationships between fact and dimension tables

### Calculated columns

#### Trip Duration Minutes

```text
Trip Duration Minutes =
Duration.TotalMinutes(
    dropoff_datetime - pickup_datetime
)
