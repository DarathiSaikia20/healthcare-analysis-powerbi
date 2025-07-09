# 🏥 Empowering Healthcare Decisions with Data-Driven Insights

![Screenshot 2025-07-09 202258](https://github.com/user-attachments/assets/e17dad29-9557-4f19-9913-f8e47a3d1e33)

## 🔍 Tracking Patient Care, Treatment Costs, and Hospital Performance with Power BI

---

## 📋 Project Overview

In today’s data-driven healthcare environment, delivering high-quality, cost-effective care requires deep insights into patient behavior, treatment outcomes, and hospital operations. This project leverages **Microsoft Power BI** to transform complex medical records into a comprehensive, interactive dashboard that helps healthcare providers make informed decisions.

Using two integrated datasets—**Patient Medical Records** and **Hospital Treatment Details**—this solution uncovers key trends across demographics, diagnoses, treatment types, billing, and recovery scores. The goal is to support strategic improvements in patient care and hospital efficiency.

---

## 💾 Project Files

| File Name                    | Description                                                     |
|-----------------------------|-----------------------------------------------------------------|
| `Healthcare_Performance.pbix` | Power BI file containing the complete interactive dashboard     |
| `dashboard_screenshot.png`  | Snapshot of the final dashboard for quick reference             |
| `README.md`                 | Project documentation including objective, process, and insights |

---

## 🧾 Dataset Description

This project uses two structured CSV files that capture patient-level clinical data and hospital performance metrics.

### 📁 Patient Medical Records (`HealthcareDataset1.csv`)

| Column Name             | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| `PatientID`             | Unique identifier for each patient (Primary Key)                            |
| `PatientName`           | Full name of the patient                                                    |
| `Age`                   | Age of the patient                                                          |
| `Gender`                | Gender (Male/Female/Other)                                                  |
| `BloodType`             | Blood group (A+, B-, O+, etc.)                                              |
| `Diagnosis`             | Medical diagnosis (e.g., Diabetes, Flu, Covid-19)                           |
| `Treatment`             | Initial treatment information (later dropped post-merge)                    |
| `AdmissionDate`         | Date of hospital admission                                                  |
| `DischargeDate`         | Date of hospital discharge                                                  |
| `TotalBill`             | Total billing amount in ₹                                                   |
| `FullPrescriptionDetails` | Detailed medication info (name, dosage, frequency, duration)             |
| `LengthOfStay`          | Derived column: number of days between admission and discharge              |
| `AgeGroup`              | Derived column: categorized as Child, Adult, or Senior                      |

---

### 🏥 Hospital Treatment Details (`HealthcareDataset2.csv`)

| Column Name        | Description                                                                      |
|--------------------|----------------------------------------------------------------------------------|
| `PatientID`        | Foreign Key corresponding to Patient Medical Records                             |
| `Hospital`         | Name of the hospital where treatment was provided                                |
| `DoctorName`       | Name of the treating doctor                                                       |
| `RoomNumber`       | Room assigned to the patient                                                      |
| `DailyCost`        | Cost per day charged by the hospital                                              |
| `TreatmentType`    | Type of treatment (e.g., Surgery, Counseling, Medication, Physical Therapy)       |
| `RecoveryRating`   | Patient's recovery rating scored from 1 to 10                                     |

---

## ❓ Problem Statement

Healthcare organizations need to answer critical questions:

- How do patient demographics affect treatment outcomes?
- Which treatments yield the best recovery scores?
- What is the relationship between treatment cost and patient recovery?
- How can hospital performance be measured and improved?

This project aims to address these questions through a data-driven approach.

---

## 🧼 Data Cleaning Summary

| Action                  | Column(s) Affected          | Justification                                                 |
|-------------------------|-----------------------------|----------------------------------------------------------------|
| Imputed missing values  | `PatientName` → 'Unknown'   | Used for display only                                          |
| Removed null records    | `TotalBill`, `Hospital`     | Essential for financial and hospital-level analysis            |
| Imputed missing values  | `RecoveryRating`            | Filled using diagnosis-wise mean to preserve data relevance    |
| Dropped column          | `Treatment` (from Patients) | Replaced by more detailed `TreatmentType` from merged dataset  |
| Created new features    | `LengthOfStay`, `AgeGroup`  | Calculated stay duration and categorized age (Child/Adult/Senior) |

---

## 🧭 Project Workflow

### 1. Data Preparation
- Cleaned, merged, and transformed both datasets
- Handled missing values and derived new fields

### 2. Exploratory Analysis
- Examined recovery trends, billing patterns, and patient volumes
- Identified treatment performance and hospital effectiveness

### 3. Dashboard Design
- Built a user-friendly Power BI dashboard with slicers and filters
- Included key KPIs, visual trends, and drill-down capabilities

---

## 📊 Dashboard Features

### 💡 Visual Components
- **KPI Cards**: Total Patients, Average Recovery Score, Mean Billing, Hospital Count
- **Donut Charts**: Recovery Rating by Treatment Type, Billing Distribution by Age Group
- **Bar Charts**: Diagnosis Frequency, Recovery Rating by Hospital, Average Billing
- **Line Charts**: Monthly Patient and Cost Flow Trends
- **Ranking Table**: Top Doctors by Recovery Score

### 🧩 Interactive Filters
- Hospital
- Age Group
- Gender
- Diagnosis
- Treatment Type
- Year

---

## 📌 Key Insights

- 👥 **Patient Flow**: 869 total cases across 5 hospitals
- 📈 **Mean Recovery Score**: 5.44 out of 10
- 💸 **Average Billing**: ₹10,000 per patient
- 🧑‍⚕️ **Top Performing Treatment**: Counseling showed the highest recovery score (5.66)
- 🏥 **Highest Rated Hospital**: Riverside Clinic with a score of 5.60
- 🛏 **Billing Variation**: Cedar Sinai Clinic had the highest average billing (₹10.4K)
- 🔄 **Seasonal Patterns**: Highest patient flow in April–July, lower toward year-end
- ⚠️ **Note**: All top doctors show a recovery rating of 10.0 — this may indicate imputation bias or scoring limitation

---

## 🎯 Conclusion

This Power BI dashboard enables healthcare professionals to:

- Evaluate hospital and doctor performance
- Analyze treatment cost-effectiveness
- Understand recovery trends by age, gender, and diagnosis
- Make informed, data-driven decisions to improve patient care

📊 **Better healthcare decisions start with better data visibility.**

---

## 🔮 Future Scope

- Integrate patient satisfaction or feedback data
- Add insurance type and payment method analysis
- Enable real-time hospital data integration via Power BI service
- Implement predictive analytics for recovery forecasting
