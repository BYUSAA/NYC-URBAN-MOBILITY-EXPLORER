# NYC TLC Urban Mobility Explorer — Yellow Taxi 2019

An interactive analytics dashboard for exploring 7.6 million yellow taxi trips recorded in New York City during January 2019. Built with a focus on performance, clean design, and real-world data processing workflows.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Installation & Setup](#installation--setup)
- [Usage Guide](#usage-guide)
- [Team](8)
- [License](#license)

## Overview

The NYC TLC Urban Mobility Explorer provides comprehensive analysis of Yellow Medallion Taxi trips from January 2019. The dashboard visualizes trip patterns, fare distributions, zone activity, and temporal trends while demonstrating custom data structure implementations (max-heap for top-k queries) and a normalized database schema.
  
**Dataset Period:** January 1–31, 2019  
**Total Trips:** 7,667,792

## Dataset

The application uses two primary data sources:

1. **yellow_tripdata_2019-01.parquet** — 7.7M trip records containing:
   - Pickup/dropoff timestamps and location IDs
   - Fare components (fare, tip, tolls, surcharges)
   - Trip distance, passenger count, payment type
   - Rate codes and vendor information

2. **taxi_zone_lookup.csv** — 265 NYC taxi zones with:
   - Zone names, boroughs, and service zone classifications
   - Location IDs for foreign key relationships

## Features

### Core Analytics
- **Real-time KPIs** — Total trips, revenue, average fare, and distance with trend indicators
- **Multi-dimensional filtering** — Filter trips by borough, rate code, payment type, fare range, distance, passenger count, and time of day
- **Interactive tables** — Sortable, searchable trip records with pagination
- **Zone Explorer** — Browse all 265 taxi zones with estimated trip volumes

### Visualizations
- Daily trip volume with revenue overlay
- Borough distribution (doughnut chart)
- Hourly traffic patterns (weekday vs weekend)
- Payment type breakdown
- Fare amount distribution histogram
- Tip rate analysis by payment method
- Fare vs distance correlation scatter plot
- Revenue composition chart
- Temporal heatmap (hour × day of week)

### Technical Highlights
- **Custom Max-Heap implementation** — Finds top-k revenue zones without built-in sort functions (O(n log k) vs O(n log n))
- **Normalized database schema** — 3NF design with facts and dimensions
- **Dark/light theme toggle** — Accessible color schemes with 5 accent colors per mode
- **Responsive design** — Works on desktop and tablet screens

## Technology Stack

### Frontend
- **HTML5/CSS3** — Semantic markup with CSS variables for theming
- **Vanilla JavaScript** — No frontend frameworks, lightweight and fast
- **Chart.js** — Interactive charts and graphs
- **Google Fonts** — Inter (sans-serif)


## Project Structure

nyc-tlc-mobility-explorer/
├── index.html               # Main dashboard (single-page application)
├── README.md                 # This file
├── data/
│     ├── sample_trips.json     # Sample data for development
└──   └── taxi_zone_lookup.csv   # Zone metadata


##  Installation & Setup

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Local server (optional, for development)

### Quick Start
1. Clone the repository:
   ```bash
   git clone https://github.com/BYUSAA/
   cd nyc-tlc-mobility-explorer
   ```

2. Open `index.html` in your browser:
   ```bash
   open index.html  # macOS
   start index.html # Windows
   ```

### Data Generation
The dashboard includes a synthetic data generator (`genTrips()`) that creates realistic trip records based on zone weights and borough distributions. For production use, replace `genTrips()` with actual parquet data loading.

## Usage Guide

### Navigation
- **Sidebar** — Switch between analysis pages (Overview, Trip Records, Zone Explorer, etc.)
- **Top bar** — Shows current page, dataset context, and quick filters
- **Theme toggle** — Bottom-right corner switches between light and dark modes

### Key Pages

#### Overview Dashboard
- View high-level KPIs and trends
- Analyze daily trip volume and borough distribution
- Explore top pickup zones table

#### Trip Records
- Apply multiple filters (borough, rate code, payment, fare range, etc.)
- Search across zone names and IDs
- Sort by any column (fare, distance, tip, duration)
- Paginated results (20 trips per page)

#### Zone Explorer
- Browse all 265 zones with estimated trip volumes
- Filter by borough or search by name
- Click any zone card to view detailed analytics

#### Fare Analysis
- Examine fare distributions and tip patterns
- View fare vs distance correlation
- Analyze revenue composition by component

#### DSA Implementation
- Interactive demo of custom max-heap algorithm
- Adjust k-value slider to see top-k revenue zones
- Step-through visualization of heap operations

### Filtering & Sorting
- Use filter pills at the top for quick date/borough toggles
- Advanced filters on Trip Records page provide granular control
- Click column headers to sort tables (ascending/descending)

## Team

_____________________________________________________________________
| Member                  | Role                                    |
|-------------------------|-----------------------------------------|
| James Giir Deng         | Team Lead & Backend Developer           |
| Byusa M Martin De Poles | Frontend Developer & Database Architect |
_____________________________________________________________________

### Contributions
- **James Giir Deng**: Led the team, designed the architecture, implemented the custom max-heap algorithm, and integrated data processing pipelines.
- **Byusa M Martin De Poles**: Developed the front-end interface, created the responsive design with theme toggle, implemented all Chart.js visualizations, and designed the normalized database schema.

- ## Team Contribution
  
**Team participation sheet link: https://docs.google.com/spreadsheets/d/1Dzq8Fro2Gq8h618v-cAFG4uUeZuVvV6BlkPYUldZ-aE/edit?usp=sharing**

## the video of testing : https://drive.google.com/file/d/1cBK7RIUAqMHnr-KeBZrEODj60sBr28bt/view?usp=sharing

The application uses two primary data sources:

## License

This project is licensed under the MIT License - see the [LICENSE] file for details.

## Acknowledgments

- NYC Taxi & Limousine Commission for providing public trip data
- The TLC Trip Record User Guide for data dictionary specifications
- All contributors and reviewers who provided feedback
