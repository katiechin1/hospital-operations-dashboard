## Dataset Overview

**Source:** Synthetic Patient Wait Time Records for Hospital (Kaggle)
**Rows:** 5,000  
**Date Range:** Jan–Mar 2024  
**Last Updated:** May 2025

## Schema Summary

**Key Fields Reviewed:**
- `PatientID` – Unique identifier per patient visit  
- `Department` – Department visited (e.g., Neurology, Surgery)  
- `AppointmentType` – Visit category (New, Referral, Follow-up, Urgent Care)  
- `ArrivalMethod` – Scheduled or Walk-in  
- `VisitDate`, `AppointmentTime`, `ActualArrivalTime`, `CheckInTime` – Time-based fields used to calculate delays  
- `Wait_Time_Minutes`, `TotalDelayTime`, `Total_Time_Hospital` – Quantitative performance measures  


## Wait Time Distribution Summary

|**Metric** | **Value (minutes)** |
|---------|----------------|
| Min | -14 |
| Median | 145 |
| 95th Percentile | 285 |
| 99th Percentile | 360 |
| Max | 497 |

*Note:* Negative waits (e.g., -14 min) occur when patients arrive before scheduled appointments.


## Outlier Handling
- **Maximum observed wait**: 497 min
- **95th percentile**: 285 min
- **99th percentile**: 359 min
- **Decision:** Cap `TotalDelayTime` values at **360 minutes** to prevent extreme synthetic outliers from distorting averages, while preserving realistic long-wait cases.


## Audit Conclusion

The dataset is clean, normalized, and ready for Power Query transformation and PivotTable analysis.  
All time-based fields are standardized, extreme delays are capped at 360 minutes, and nulls are minimal and non-critical.