# Key Insights – Hospital Patient Flow & Efficiency Dashboard

This analysis evaluates operational efficiency across hospital departments using patient wait time, arrival punctuality, and visit duration data.  
The findings reveal where workflow adjustments could significantly improve patient experience and throughput efficiency.

---

## Executive Summary

- **Patients wait an average of 152 minutes**, exceeding the updated hospital benchmark of **90 minutes**.  
  This indicates widespread bottlenecks in post-check-in processes and department scheduling.

- **77% of patients arrive on time**, yet **90% still wait over one hour** — suggesting the issue lies in operational flow after arrival rather than patient punctuality.

- **Neurology (164 min)** and **General Surgery (160 min)** have the longest waits, while **Radiology (138 min)** and **Pediatrics (145 min)** demonstrate efficient patient movement.  
  These high-performing departments can be modeled for best practices.

- **Peak patient volume occurs between 8 AM and 3 PM**, especially on **Mondays and Sundays**, where both patient load and delays increase sharply.  
  Performance improvements should focus on these windows.

- **Staff-to-patient ratio shows minimal correlation with wait times**, indicating that **process design and scheduling efficiency**, not headcount, are the primary drivers of delay.

---

## Recommendations

| Action | Objective | Responsible Team | Timeline |
|--------|------------|------------------|-----------|
| Review triage and provider assignment workflows in Neurology and General Surgery | Identify sources of post-check-in delay | Department Heads | Within 1 month |
| Adjust shift coverage and scheduling for 8 AM–3 PM | Reduce bottlenecks during peak hours | Operations & HR | Next scheduling cycle |
| Benchmark Radiology and Pediatrics workflows | Replicate efficient intake and discharge processes | Analytics & Operations | Ongoing |
| Track KPI progress monthly | Validate improvements and sustain performance | Data Analytics | 30-day intervals |

---

## Expected Outcomes

- Reduce **average wait time** from 152 → ≤ 90 minutes (40% improvement target)  
- Reduce **long-wait share (≥ 60 min)** to below **35%**  
- Improve **on-time rate** from 77% → ≥ 80%  
- Decrease **average total time in hospital** from 164 → ≤ 150 minutes  
- Increase overall patient satisfaction and operational consistency

---

## Deeper Analysis

To move beyond descriptive reporting, I performed exploratory and correlation-based analysis to uncover the operational factors driving patient delays.  

- **Bottleneck Identification:**  
  Using the time-based columns (`ActualArrivalTime`, `CheckInTime`, `TriageCompleteTime`, `ProviderStartTime`), I calculated time deltas between each process step. Results showed that **post-triage delays** accounted for nearly half of total patient waiting time, confirming that inefficiencies occur **after** initial intake, not at registration.

- **Correlation Testing:**  
  Using Excel’s CORREL function, I measured the relationship between `Wait_Time_Minutes` and variables like `StaffToPatientRatio`, `ProvidersOnShift`, and `FacilityOccupancyRate`. The **correlation coefficient (r = –0.05)** indicated a **very weak relationship**, confirming that staffing levels are not the main determinant of patient delays.

- **Variance and Equity Analysis:**  
  I compared wait time variance across departments and insurance types. **Neurology** and **General Surgery** showed wait time variances nearly **2× higher** than other departments, while **Medicaid** and **Self-pay** patients experienced **average waits 20–25 minutes longer** than those with private insurance. This suggests a potential equity gap in service speed.

- **What-If Scenario Modeling:**  
  By simulating a **20% reduction** in average wait time (using a derived “Reduced_Wait” column), I modeled the potential operational impact. This reduction would **lower the long-wait share (≥ 60 min)** from 90% to approximately **65%**, aligning the hospital closer to target performance levels.

**Summary:**  
These analyses demonstrate that wait time inefficiencies stem primarily from **process flow and scheduling patterns**, not staffing shortages. Prioritizing **workflow redesign** between triage and provider start — and optimizing morning scheduling during 8 AM–3 PM — would yield the largest performance gains.

---
 
_Last updated: May 2025_
