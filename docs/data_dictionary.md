## Data Dictionary

### Dim_Patients
- Patient ID (Primary Key)
- Gender
- Age
- City, State, Country
- Chronic Conditions
- Insurance Provider

### Dim_Doctors
- Doctor ID (Primary Key)
- Doctor Name
- Specialty
- Hospital / Clinic
- Years of Experience

### Fact_Visits
- Visit ID (Primary Key)
- Patient ID (Foreign Key)
- Doctor ID (Foreign Key)
- Visit Date
- Visit Type
- Visit Status
- Diagnosis

### Fact_Treatments
- Treatment ID (Primary Key)
- Visit ID (Foreign Key)
- Treatment Type
- Cost
- Outcome

### Fact_LabResults
- Lab Result ID (Primary Key)
- Visit ID (Foreign Key)
- Test Name
- Test Result
- Is_Abnormal (Derived)

