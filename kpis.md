
# Key Performance Indicators (KPIs) – Hospital Operations Dashboard

This document defines the core KPIs used in the **Hospital Patient Flow & Efficiency Dashboard**, including calculation logic, business interpretation, and target benchmarks.  
Each KPI aligns with operational goals for reducing wait times, improving patient experience, and optimizing workflow efficiency.

---

## Primary KPIs (Displayed on Dashboard)

| **KPI Name** | **Formula / Logic** | **Goal / Target** | **Interpretation** |
|---------------|----------------------|--------------------|--------------------|
| **Average Wait (min)** | `AVERAGE(Wait_Time_Minutes)` | ≤ 90 min | Represents the overall time patients wait before being seen. Lower is better; over 90 min indicates system congestion. |
| **% of Patients Waiting Over 1 Hour** | `COUNTIF(Wait_Time_Minutes ≥ 60) / COUNT(All)` | ≤ 35% | Measures how often patients experience long waits. High percentages indicate workflow inefficiencies. |
| **% of Patients Arriving On Time** | `COUNTIF(Arrival_Status = "On Time") / COUNT(All)` | ≥ 75% | Tracks patient punctuality and scheduling accuracy. Higher is better. |
| **Time from Arrival → Check-in (min)** | `AVERAGE(CheckInTime - ActualArrivalTime)` | ≤ 5 min | Indicates how quickly patients are registered after arrival. |
| **Total Time Spent in Hospital (min)** | `AVERAGE(Total_Time_Hospital)` | ≤ 150 min | Represents complete visit duration, including waiting, treatment, and discharge. Lower values show faster patient flow. |


---

## Supporting Operational Metric (Used in Analysis Only)

| **Metric Name** | **Formula / Logic** | **Purpose / Use Case** |
|------------------|----------------------|--------------------------|
| **Peak Hour Load** | `COUNT(Appointments by Arrival_Hour)` | Identifies the busiest hours of the day to support staffing and scheduling optimization. |

---

## Notes
- Targets are based on realistic hospital operational benchmarks and serve as reference thresholds for performance evaluation.  
- Lower values for wait-related KPIs indicate improved patient flow and operational efficiency.  
- The dashboard visualizes these KPIs with conditional color formatting (green = on target, red = off target) for quick interpretation.
