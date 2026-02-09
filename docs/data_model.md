## Data Model

- Dim_Patients (1) → Fact_Visits (Many)
- Dim_Doctors (1) → Fact_Visits (Many)
- Dim_Date (1) → Fact_Visits (Many)
- Fact_Visits (1) → Fact_Treatments (Many)
- Fact_Visits (1) → Fact_LabResults (Many)

The Fact_Visits table acts as the central fact table for analytical reporting, with dimensions for Patients, Doctors, and Date.
