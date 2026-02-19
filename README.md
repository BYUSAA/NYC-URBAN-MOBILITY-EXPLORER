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
- 

The application uses two primary data sources:

## License

This project is licensed under the MIT License - see the [LICENSE] file for details.

## Acknowledgments

- NYC Taxi & Limousine Commission for providing public trip data
- The TLC Trip Record User Guide for data dictionary specifications
- All contributors and reviewers who provided feedback

















































# Team Participation & Task Tracking Sheet

## Project: NYC TLC Urban Mobility Explorer — Yellow Taxi 2019

---

## 👥 Team Members & Roles

| Team Members | Role/Responsibility | Email |
|---|---|---|
| Byusa M Martin De Poles | Frontend Developer & Database Architect | m.byusa@alustudent.com |
| James Giir Deng | Team Lead & Backend Developer | j.deng1@alustudent.com |

---

## ✅ Task Allocation and Tracker

| Task Allocated | Assigned Member | Deadline | Reviewed by Team? (Yes/No) | Comments |
|---|---|---|---|---|
| **Project Setup & Repository Initialization** – Create GitHub repo, setup structure, initialize documentation | James Giir Deng | Feb 10, 2025 | Yes | Repository created with README and folder structure |
| **Zone Data Integration** – Import taxi_zone_lookup.csv, map zone IDs to names/boroughs | Byusa M Martin De Poles | Feb 12, 2025 | Yes | All 265 zones integrated with metadata |
| **Data Processing Pipeline** – Parse parquet, clean 7.7M records, generate synthetic data | James Giir Deng | Feb 15, 2025 | Yes | 1.42% rejection rate; synthetic generator working |
| **Frontend Architecture & Base Layout** – Sidebar, top bar, page routing, CSS variables | Byusa M Martin De Poles | Feb 18, 2025 | Yes | Responsive navigation with theme toggle |
| **Overview Dashboard Development** – KPI cards, mini-charts, top zones table | Byusa M Martin De Poles | Feb 22, 2025 | Yes | All KPIs functional; table sortable |
| **Chart.js Visualizations** – Daily trips, borough dist, hourly pattern, payment, fare dist | Byusa M Martin De Poles | Feb 25, 2025 | Yes | 8+ interactive charts implemented |
| **Trip Records Page with Filtering** – Advanced filters (10+), pagination, search, sorting | James Giir Deng | Feb 28, 2025 | Yes | Full filtering and pagination working |
| **Zone Explorer Page** – Zone grid, borough filter, search, detail modal with charts | Byusa M Martin De Poles | Mar 02, 2025 | Yes | All 265 zones displayed; modal functional |
| **Custom Max-Heap Algorithm** – Heapify functions, top-k zone revenue, interactive demo | James Giir Deng | Mar 05, 2025 | Yes | O(n log k) algorithm with step-through |
| **Fare Analysis Page** – Fare distribution, tip rate, scatter plot, revenue composition | Byusa M Martin De Poles | Mar 07, 2025 | Yes | All fare charts with tooltips |
| **Modal System Implementation** – Trip detail modal, zone detail modal, fare breakdown | James Giir Deng | Mar 08, 2025 | Yes | Both modals functional with dynamic content |
| **Temporal Patterns Page** – Tabs (hourly/daily/weekly/heatmap), hourly fare, day-of-week, heatmap | Byusa M Martin De Poles | Mar 09, 2025 | Yes | Four tabs working; demand heatmap |
| **Database Schema Design** – ER diagram (SVG), fact/dimension tables, indexes | Byusa M Martin De Poles | Mar 12, 2025 | Yes | 3NF schema with SVG diagram |
| **Data Processing & Quality Page** – Exclusion reasons, completeness, derived features, audit log | James Giir Deng | Mar 14, 2025 | Yes | Full data quality dashboard |
| **Dark/Light Theme Implementation** – CSS variables for both modes, theme toggle, 5-color palette | Byusa M Martin De Poles | Mar 15, 2025 | Yes | Smooth theme switching; accessible colors |
| **Insights Page & Key Findings** – Three evidence-backed insights with supporting charts | James Giir Deng | Mar 16, 2025 | Yes | Manhattan dominance, rush hour asymmetry, airport tip paradox |
| **Technical Report Page** – Problem framing, architecture, reflection, diagrams | Both (James & Byusa) | Mar 18, 2025 | Yes | Comprehensive documentation with SVG diagrams |
| **Responsive Design & Cross-browser Testing** – Test Chrome/Firefox/Safari, fix overflow | Byusa M Martin De Poles | Mar 19, 2025 | Yes | Works on all modern browsers |
| **README.md & Documentation** – Comprehensive README, team roles, setup instructions | Both (James & Byusa) | Mar 20, 2025 | Yes | Complete documentation with all sections |
| **Final Integration & Bug Fixes** – Test navigation, verify charts, fix JS errors | Both (James & Byusa) | Mar 22, 2025 | Yes | All systems operational; minor edge cases fixed |

---

## 📅 Meeting Attendance Log

| Meeting Date | Agenda | Facilitator | Attendees | Next Steps |
|---|---|---|---|---|
| Feb 08, 2025 | **Kickoff & Project Scope** – Discuss dataset, assign roles, set communication | James Giir Deng | James Giir Deng, Byusa M Martin De Poles | James: explore parquet schema; Byusa: create HTML skeleton |
| Feb 15, 2025 | **Data Pipeline & Frontend** – Review data progress, zone integration, color scheme | James Giir Deng | James Giir Deng, Byusa M Martin De Poles | James: implement data quality checks; Byusa: build base layout |
| Feb 22, 2025 | **Charts & Algorithm** – Review Chart.js, discuss max-heap approach, page structure | Byusa M Martin De Poles | James Giir Deng, Byusa M Martin De Poles | James: write heap pseudo-code; Byusa: build overview charts |
| Mar 01, 2025 | **Filtering & Zone Explorer** – Review filter panel, pagination, test zone search | James Giir Deng | James Giir Deng, Byusa M Martin De Poles | James: optimize filters; Byusa: add zone detail modal |
| Mar 08, 2025 | **Algorithm Demo & Schema** – Review heap, discuss ER diagram, plan insights | Byusa M Martin De Poles | James Giir Deng, Byusa M Martin De Poles | James: finalize algorithm page; Byusa: build schema page |
| Mar 15, 2025 | **Theme Implementation** – Review dark/light mode, test color consistency | James Giir Deng | James Giir Deng, Byusa M Martin De Poles | Byusa: fix responsive issues; James: begin documentation |
| Mar 20, 2025 | **Final Review** – Walk through all pages, verify no emoji, finalize roles | Byusa M Martin De Poles | James Giir Deng, Byusa M Martin De Poles | Both: final bug fixes; prepare submission |
| Mar 22, 2025 | **Project Wrap-up** – Final testing, package deliverables, submit | James Giir Deng | James Giir Deng, Byusa M Martin De Poles | Project submitted; schedule post-mortem |

---

## 📊 Summary

| Metric | Value |
|--------|-------|
| **Total Tasks** | 20 |
| **Completed Tasks** | 20 |
| **In Progress** | 0 |
| **Team Meetings** | 8 |
| **Completion Rate** | 100% |

---

**Prepared by:** James Giir Deng & Byusa M Martin De Poles  
**Date:** March 22, 2025  
**Project:** NYC TLC Urban Mobility Explorer — Yellow Taxi 2019
