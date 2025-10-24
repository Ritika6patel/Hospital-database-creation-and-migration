🏥 Hospital Database Migration & Automation
📘 Overview

This project focuses on modernizing a hospital’s record management system by migrating from Excel-based files to a relational SQL database.
The new system enhances data accuracy, performance, and security, while supporting daily hospital operations such as patient management, appointments, billing, and reporting.

🎯 Objectives

Design and implement a relational database that captures all core hospital functionalities.

Migrate and clean existing Excel data to ensure data integrity and consistency.

Apply business logic, validation, and access controls that align with real-world hospital workflows.

⚙️ Key Features
1. Unique Identifiers

Introduced primary keys for Patients, Doctors, Departments, and Appointments to eliminate duplicate entries and maintain consistency.

2. Referential Integrity

Implemented foreign key relationships between entities:

Each appointment is linked to a valid Patient and Doctor.

Doctors belong to specific Departments.

Billing records are connected to corresponding Appointments and Patients.

3. Data Validation

Gender restricted to M, F, or O.

Appointment status limited to Scheduled, Completed, or Cancelled.

Consistent date formats enforced during data migration.

4. Appointment Regulation

Added constraints and triggers to prevent:

Double-booking of doctors.

Scheduling appointments in the past.

5. Access Control & Security

Designed a role-based access model to protect sensitive information:

Senior Doctors can view all patients within their department.

Regular Doctors can access only their assigned patients’ details (appointments, prescriptions, lab reports).

6. Automated Reporting

Enabled generation of:

Department-wise revenue reports

Patient billing summaries

Doctor workload and performance analytics

🧱 Database Design

Core Tables:

patients

doctors

departments

appointments

prescriptions

lab_reports

billing

user_roles

Relationships:

One Department → Many Doctors

One Doctor → Many Appointments

One Patient → Many Appointments

One Appointment → One Billing Record

🛠️ Tech Stack
Component	Technology
Database	MySQL / PostgreSQL
Data Source	Excel
Tools	SQL Workbench / pgAdmin
Techniques	Normalization (up to 3NF), Constraints, Triggers, Views, Role-Based Access Control
📊 Implementation Steps

Data Analysis & Cleaning

Reviewed Excel sheets for invalid entries, duplicates, and inconsistent data formats.

Standardized all records for compatibility with SQL schema.

Database Design

Created ER Diagram and normalized tables to eliminate redundancy.

Defined relationships using foreign keys.

Data Migration

Imported cleaned Excel data into SQL using bulk insert tools.

Verified integrity post-import.

Business Rules & Automation

Added constraints, stored procedures, and triggers for appointment validation and billing automation.

Access Management

Implemented role-based permissions using SQL GRANT and REVOKE statements.

📈 Outcomes

✅ Improved data accuracy and consistency
✅ Automated scheduling and billing workflows
✅ Enhanced data security through restricted access
✅ Simplified generation of hospital-wide reports

🧩 Future Enhancements

Build a web-based dashboard for real-time reporting and data visualization.

Integrate analytics module for patient trends and operational insights.

Automate daily data backups and audit logs.

📂 Folder Structure
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

🧠 Learnings

Gained hands-on experience in data modeling and normalization.

Improved understanding of data migration and validation techniques.

Learned to implement real-world business rules in SQL using triggers and stored procedures.

Strengthened knowledge of data governance and access control mechanisms.