# Booking_report_auto
Automated scheduling analyst tool for multi-branch operations. Features a flexible logic interface to handle dynamic peak-hour (AM/PM) definitions across different weekdays. Utilizes Pandas to transform raw "yyyy-mm-dd" booking data into professional, multi-layered Excel reports with automated grand totals and branch-specific insights.
# Booking Report Automation System (Multi-Branch)

## 📌 Project Overview
This repository contains a Python-based automation solution designed to streamline the reporting process for a multi-branch service business in Singapore. The system transforms raw appointment data into a sophisticated, multi-layered Excel dashboard, replacing hours of manual data entry and consolidation.

### The Problem
Operational staff previously had to manually filter and count bookings from different branches and time slots (AM/PM) across various locations, a process prone to human error and highly inefficient.

## 🚀 Key Technical Features

### 1. Dynamic Business Logic Interface
As seen in `BR_project_code.py`, I implemented a dedicated **Interface section** to handle shifting business requirements:
* **Flexible Time-Slot Classification:** The `get_time_slot` function allows for independent AM/PM definitions for Weekdays vs. Saturdays.
* **Configurable Parameters:** Easily adjust the 3-4 PM transition window or change branch mappings (e.g., `Scott` to `SMC`) without touching the core processing logic.

### 2. Advanced Data Transformation (ETL)
* **Pandas Power:** Utilizes complex pivot tables and Multi-Indexing to create the dual-layered header structure (Branch + Time Slot).
* **Time-Series Processing:** Converts raw `yyyy-mm-dd hh:mm:ss` timestamps into Day-of-Week (DOW) and Date formats for operational tracking.
* **Automated Aggregation:** Calculates both **Daily Totals** (across all branches) and **Grand Totals** (column-wise summaries) automatically.

### 3. Professional Report Generation
* **XlsxWriter Integration:** Produces a boardroom-ready Excel file (`output_BR.xlsx`) featuring:
    * Customized header metadata (e.g., "PREPARED BY STAFF").
    * Hierarchical column headers for intuitive reading.
    * Automated date-stamping for report version control.

## 📊 Data Structure

### Input (`input_BR.csv`)
Raw data containing:
* `Branch`: Location of the appointment (Kovan, Novena, etc.).
* `appointment_start_time`: Full timestamp of the booking.

### Output (`output_BR.xlsx`)
A structured matrix including:
* **DOW/DATES:** Primary tracking columns.
* **DAILY TOTALS:** Aggregate volume for the entire business.
* **Branch-Specific Columns:** (SMC, NMC, RP, WG, KV) broken down by AM and PM slots.

## 📈 Impact & Professionalism
* **90% Efficiency Gain:** Reduced report generation time from over an hour of manual work to a sub-second script execution.
* **Scalability:** The architecture easily supports the addition of new branches or changing business hours.
* **Privacy Conscious:** All personal client identifiers have been removed from the source code and sample data, adhering to strict data protection standards.

## 🛠️ Requirements
* Python 3.x
* Pandas
* Openpyxl / XlsxWriter
