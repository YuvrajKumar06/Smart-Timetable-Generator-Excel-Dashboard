# Smart Timetable Dashboard

An automated, data-driven scheduling and resource management dashboard designed to optimize university timetables. This project processes relational data across teachers, classes, rooms, and subjects to maximize resource utilization, track workloads, and eliminate scheduling conflicts.

---

## 📊 Project Overview

Managing academic timetables involves complex constraints—balancing teacher availability, matching room capacities with class sizes, and ensuring fair workload distribution. The **Smart Timetable Dashboard** serves as a centralized operational tool to monitor, analyze, and simulate these parameters seamlessly.

### Key Performance Indicators (KPIs)
* **Total Capacity Managed:** 20 Teachers, 30 Subjects, 20 Classes, and 15 Rooms.
* **Operational Load:** 900 automated sessions scheduled weekly.
* **Balanced Workload:** Tracks average teacher workload (~14.7 hours/week) and instantly flags optimization anomalies (e.g., overloaded/underloaded staff).

---

## 🗂️ Data Architecture & Schema

The dashboard relies on a structured relational data model spread across the following core modules:

* **`MasterData` / `Timetable`**: The core engine combining schedules, session IDs (`SES-XXXX`), duration tracking, and spatial-temporal mappings.
* **`TeacherWorkload`**: Monitors teacher utilization percentages, tracking caps, baseline capacities (`MaxHours`), and scheduled availability ranges.
* **`Rooms` & `Classes`**: Validates structural constraints by mapping class strengths against room capacities across distinct facility zones (`Lecture` vs `Lab` spaces in `Block A` / `Block B`).
* **`Subjects` & `TimeSlots`**: Defines hourly per-week requirements, credit weights, and standard period distributions.

---

## 🛠️ Key Features

### 1. Resource Utilization Analytics
* Tracks department-specific metrics showing average utilization across branches (**CE**, **CSE**, **ECE**, **EE**, **ME**).
* Segregates allocation trends by day and location types to prevent spatial bottlenecks.

### 2. Teacher Workload Status Distribution
Classifies educators dynamically into three performance categories:
* 🟢 **Balanced**: Optimal allocation matching target capacities.
* 🟡 **Underloaded**: Available for additional proxy or elective handling.
* 🔴 **Overloaded**: Triggers conflict warnings when assigned hours exceed maximum capacity thresholds.

### 3. Interactive Teacher Session Simulator
A built-in simulator tool allowing administrators to query a specific `TeacherID` (e.g., `T007`) to instantaneously pull:
* Comprehensive weekly schedules.
* Live utilization metrics.
* Room allocations and assigned subject mappings.

---

## 🚀 Getting Started

### Prerequisites
To interact with or run analytics on the source sheets, ensure you have one of the following setups:
* **Microsoft Excel** (2021 or later for fully optimized Pivot Charts/Dashboards)
  ```bash
  pip install pandas openpyxl matplotlib
