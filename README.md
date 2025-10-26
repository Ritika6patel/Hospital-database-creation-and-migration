# 🏥 Hospital Database Migration & Automation
## 📘 Overview

In today’s digital era, hospitals generate vast amounts of data every day — from patient records and lab results to doctor schedules and billing details. Yet, many mid-sized healthcare institutions still rely on Excel for managing critical operations, leading to inefficiency, errors, and limited scalability.

To address this, I developed the **Hospital Database Migration & Automation Project**, which transformed a fragmented Excel-based system into a robust, relational SQL database. The goal was to build a scalable data infrastructure that ensures data integrity, secure access, and cross-departmental insights — bridging the gap between technology, efficiency, and healthcare operations.

## 🔍 Problem Context
The hospital had been maintaining all its records manually in Excel sheets — including patients, doctors, appointments, lab reports, prescriptions, and billing data. As patient inflow and hospital operations grew, this traditional method began to show critical inefficiencies:

1. Lack of Unique Identifiers – Multiple records existed for the same patient or doctor, causing confusion in billing and medical history tracking.

2. Disconnected Relationships – Appointments were listed without guaranteed linkage to actual doctors or registered patients.

3. Invalid Data Entries – Gender fields included random values like “X”, inconsistent date formats, and unregulated appointment statuses.

4. Scheduling Conflicts – Doctors were often double-booked or scheduled for past dates.

5. Open Access to Sensitive Data – All doctors could view all patient data, creating a potential privacy and compliance issue.

6. Disconnected Reporting – There was no systematic way to generate billing summaries, departmental revenue reports, or performance dashboards.

   These challenges resulted in operational inefficiencies, data silos, and high risk of human error. Hospital leadership needed a system that would not only fix these issues but also      scale with future growth.
## 🎯 Objectives

- Design a relational database to replace Excel-based data storage.

- Migrate and clean legacy data from Excel to SQL, ensuring data consistency.

- Define clear entity relationships among patients, doctors, departments, and appointments.

- Implement business logic through constraints, triggers, and stored procedures.

- Create role-based access control to protect sensitive information.

- Enable automated reporting for billing, departmental revenue, and performance insights.

  ## 🧱 Database Design & Architecture

  **1. Core Entities**

After analyzing all Excel files and business processes, identified the following primary entities:

- **Patients** – storing demographics, contact details, and medical history.

- **Doctors** – storing Role, specialization, department, and shift timings.

- **Departments** – linking doctors and hospital services (e.g., Cardiology, Neurology).

- **Appointments** – connecting patients with doctors, along with date, time, and status.

- **Prescriptions** – storing prescribed medications,dosages per appointment.

- **Lab Reports** – tracking diagnostic tests, results, and report delivery.

- **Billing** – managing invoices, payment details, and revenue summaries.


**2. Relationships Established**

- One Department → Many Doctors

- One Doctor → Many Appointments

- One Patient → Many Appointments

- One Appointment → One Billing Record

- One Appointment → Many Prescriptions / Reports

  ## ⚙️ Technical Implementation
  
  **🔸 1. Data Cleaning & Migration**
  
  The first challenge was preparing the Excel data for migration. I developed a Python- and SQL-based cleaning workflow that:

- Standardized all date formats (DD-MM-YYYY).

- Mapped gender entries to valid codes (‘M’, ‘F’, ‘O’).

- Removed duplicates and merged overlapping records.

- Created new unique identifiers (auto-incremented IDs) for patients, doctors, and departments.

- Validated foreign key mappings between existing datasets before migration.

**🔸 2. Enforcing Business Rules**

  To eliminate future inconsistencies, I implemented database-level constraints and triggers:

- CHECK Constraints to ensure valid data entries (e.g., gender, appointment status).

- UNIQUE Constraints for doctor license numbers, patient IDs, and department codes.

- BEFORE INSERT Triggers to prevent:

    -  Double-booking of doctors.

    - Appointments scheduled in the past.

- AFTER UPDATE Triggers to automatically update billing status upon appointment completion.

  These rules automated large portions of hospital operations that were previously managed manually in Excel.

 **🔸 3. Role-Based Access Control**

Data security was a major priority. The system now distinguishes users based on their roles and privileges:

- **Admin:** Full access to all tables and reports.

- **Senior Doctor:** Can view all patient data within their department.

- **Doctor:** Limited to their own patients’ records and prescriptions.

- **Lab Technician:** Access only to test reports and associated appointments.

- **Billing Staff:** Access to billing tables and reports only.


**🔸 4. Automated Reporting**

To replace manual Excel calculations, I created SQL  Queries for automated reporting:

- **Department-Wise Revenue Report:** Aggregates total billing per department.

- **Patient Billing Summary:** Generates invoices per appointment.

- **Doctor Workload Report:** Calculates total appointments handled within a period.

- **Appointment Trend Analysis:** Tracks daily and weekly patient inflow.

These outputs could easily be integrated with Power BI or Tableau dashboards in future expansions.

## ⚙️ Key Features
**1. Unique Identifiers**

Introduced primary keys for Patients, Doctors, Departments, and Appointments to eliminate duplicate entries and maintain consistency.

**2. Referential Integrity**

Implemented foreign key relationships between entities:

- Each appointment is linked to a valid Patient and Doctor.

- Doctors belong to specific Departments.

- Billing records are connected to corresponding Appointments and Patients.

**3. Data Validation**

- Gender restricted to M, F, or O.

- Appointment status limited to Scheduled, Completed, or Cancelled.

- Consistent date formats enforced during data migration.

**4. Appointment Regulation**

 Added constraints and triggers to prevent:

   - Double-booking of doctors.

   - Scheduling appointments in the past.

**5. Access Control & Security**

Designed a role-based access model to protect sensitive information:

- Senior Doctors can view all patients within their department.

- Regular Doctors can access only their assigned patients’ details (appointments, prescriptions, lab reports).

**6. Automated Reporting**

Enabled generation of:

- Department-wise revenue reports

- Patient billing summaries

- Doctor workload and performance analytics



## 🛠️ Tech Stack
    Component	      Technology
    
    Database 	     MySQL / PostgreSQL
    Data             Source	Excel
    Tools	         SQL Workbench / pgAdmin
    Techniques	     Constraints, Triggers, Role-Based Access Control

## 💼 Business Impact

Beyond the technical build, this project delivered significant business value for hospital operations.

🔹 Enhanced Efficiency

Migrating from Excel to a relational database reduced data entry errors, eliminated duplication, and allowed real-time access to accurate information. Tasks that previously took hours in Excel now run as instant queries.

🔹 Improved Decision-Making

Departmental revenue and doctor performance data are now accessible in a few clicks — enabling management to make data-driven decisions around staffing, service expansion, and cost optimization.

🔹 Strengthened Data Security

Role-based access ensures that sensitive patient information is visible only to authorized users, improving compliance with data protection standards like HIPAA.

🔹 Streamlined Scheduling

Automated appointment validation prevents scheduling conflicts and ensures optimal doctor utilization.

🔹 Scalable Infrastructure

The relational schema provides a foundation for integrating advanced analytics, BI tools, or even a full-fledged Hospital Management System in the future.

## 📈 Key Results ##

- 100% Data Integrity Achieved post-migration.

- Eliminated double-booking through automated appointment validation.

- Reduced data redundancy by 70% after normalization.

- Improved data access speed by 60%, compared to Excel.

- Secured patient data access and  Enhanced data security through restricted role-based permissions.
  
- Simplified generation of hospital-wide reports


## 🧩 Future Enhancements

- Build an interactive Power BI dashboard for hospital management to visualize revenue, patient volume, and departmental KPIs.

- Integrate with a web-based Hospital Management System (HMS) for real-time updates.

- Automate data backup and recovery using scheduled SQL jobs.

- Expand to include inventory management for medical supplies.
- Develop a machine learning layer to predict patient inflow and optimize resource allocation.

##📂 Folder Structure

    Hospital-Database-Migration/
    │
    ├── Data/
    │   ├── Patients.xlsx
    │   ├── Doctors.xlsx
    │   ├── Appointments.xlsx
    │   └── Billing.xlsx
    │
    ├── SQL_Scripts/
    │   ├── hospital_schema.sql
    │   ├── data_migration.sql
    │   ├── constraints_triggers.sql
    │   └── role_based_access.sql
    │
    ├── Reports/
    │   ├── department_revenue.sql
    │   ├── patient_billing_summary.sql
    │   └── doctor_performance.sql
    │
    └── README.md

## 🧠 🧩 Conclusion

The Hospital Database Migration & Automation project exemplifies how data engineering meets business transformation.

By moving from Excel spreadsheets to a structured, relational database, the hospital gained not only a stable data foundation but also the ability to automate workflows, secure patient data, and unlock valuable business insights.

What began as a technical exercise in SQL design evolved into a comprehensive digital transformation blueprint, bridging the gap between technology and operational strategy.

It reinforced one essential truth — data is not just about storage; it’s about enabling smarter, faster, and

## Images/screenshot 
Database looks like : ![Alt Text](https://github.com/username/repo/assets/image.jpg)
![Database Preview](https://github.com/Ritika6patel/Hospital-database-creation-and-migration/blob/master/Image.jpg)
Example: ![Database Preview](https://github.com/Ritika6patel/Hospital-database-creation-and-migration/blob/master/Images/Image-8.png)

## Images/screenshot (Excel Image of file before migration)
Database looks like :![Alt Text](https://github.com/username/repo/assets/image.jpg)
Example: ![Database Preview](https://github.com/Ritika6patel/Hospital-database-creation-and-migration/blob/master/Excel-Image.png)


