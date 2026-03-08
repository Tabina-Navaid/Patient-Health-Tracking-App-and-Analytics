# 🏥 Patient Health Tracking App and Analytics


A full end-to-end patient monitoring system built from scratch for a Canadian elderly care startup. The project spanned database design, app development, and analytics, covering an ERD-designed MySQL database, a Google AppSheet mobile app used by two clinical teams for visit-by-visit data entry, and a Power BI dashboard for patient vitals monitoring. The system gave doctors and nurses a structured, digital workflow to record and track patient health metrics including blood pressure, glucose levels, respiratory readings, oximetry, BMI, and temperature across every visit..

---

## 🧩 Problem Statement

Clinical staff had no unified digital system for recording or reviewing a patient's health trajectory over time. Vital signs recorded across multiple visits were scattered across paper forms and disconnected records, making it difficult for care teams to:

- Detect deteriorating trends across visits
- Compare readings over time for a single patient
- Quickly brief a new team member on a patient's history
- Make timely, evidence-based clinical decisions

---

## 🏗️ System Architecture

The project was built across three layers:
```
MySQL Database (Google Cloud hosting)
        ↓
Google AppSheet Mobile App     ← Clinical staff log vitals here
        ↓
Microsoft Power BI Dashboard   ← Care teams monitor trends here
```

---

## 🗄️ Layer 1 — Database Design (MySQL on Google Cloud)

The foundation of the system is a **MySQL relational database**, designed to support patient-level tracking across visits, care teams, medications, and clinical examinations.

### ERD Schema

<img width="1216" height="843" alt="Screenshot 2026-03-09 024044" src="https://github.com/user-attachments/assets/2760041f-05e5-4ea3-b4cb-dc98021d2863" />

> 📁 Add your ERD screenshot to `/images` as `erd-schema.png`

### ☁️ Cloud Hosting

The MySQL database is hosted on **Google Cloud Platform (Cloud SQL)** — providing a managed, scalable, and secure environment that keeps patient data available across devices and care teams in real time. All data entered through the mobile app writes directly to this database, and Power BI connects to it as its live data source.

---

## 📱 Layer 2 — Mobile App (Google AppSheet)

The data entry layer was built using **Google AppSheet**, a platform, enabling clinical staff to log patient vitals and visit records directly from their mobile devices — no technical knowledge required.

The app connects directly to the Cloud SQL database, meaning every entry made in the field is immediately available for reporting and monitoring.

**Key app features:**
- Patient search and profile lookup
- Vitals entry per visit (BP, glucose, temperature, oximetry, BMI, respiratory rate)
- Visit history view per patient
- Real-time sync to the Cloud SQL MySQL database

### App Screenshots

| Home | Patient Profile | Vitals Entry |
|------|----------------|--------------|
| <img width="390" height="832" alt="Screenshot 2026-03-09 023250" src="https://github.com/user-attachments/assets/5a73ec0e-6425-4c07-89dc-aa5d5f8e555b" />| <img width="392" height="864" alt="Screenshot 2026-03-09 023257" src="https://github.com/user-attachments/assets/a8c2fd5a-9ab7-436d-b6b1-e0669dfb4624" /> | <img width="418" height="865" alt="Screenshot 2026-03-09 023314" src="https://github.com/user-attachments/assets/19c7bfec-be40-4977-9fc2-87da49c6f4dc" />|


---

## 📊 Layer 3 — BI Dashboard (Microsoft Power BI)

With the database live and data flowing in through the app, a ** Power BI dashboard** was built to give care teams a real-time monitoring view. Tabs cover **Vitals**, **History**, **Examination**, and **Medication** — each pulling directly from the Cloud SQL database.

**Design decisions:**
- **Line charts** for trend-sensitive indicators like blood pressure and respiratory/oximetry readings
- **Gauge visuals** to communicate average systolic and diastolic BP against clinical ranges
- **Patient context panel** surfacing care team and identification details at the top of every view
- **Name and visit date filters** for instant patient-level drill-down

### Dashboard Screenshot

<img width="1436" height="879" alt="Screenshot 2026-02-26 031524" src="https://github.com/user-attachments/assets/4c90ba2e-a034-47a8-ab54-f8a1bec3764d" />

---

## 📈 Business Outcomes

- Clinical staff can **log vitals on the go** from any mobile device, replacing paper-based workflows entirely
- Care teams can pull up a **complete vitals history for any patient in seconds**
- Enables identification of concerning trends (e.g., elevated systolic BP averaging **133**, or a glucose spike to **245** in April 2023)
- Supports more informed, **data-driven clinical decisions**
- Reduces the risk of **missed warning signs** between visits

---

## 🔗 Live Dashboard

View the interactive dashboard on Power BI:

[![Open in Power BI](https://img.shields.io/badge/Power%20BI-View%20Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiOGI0OGVlN2UtNGIwMi00ZTM1LWIwNDAtYjc0NDU1NjhhY2RkIiwidCI6ImZlZTNiOTE2LTAxYzEtNDk4Ny1hNjQ2LWUxOTM0MzJiOWVhYSIsImMiOjl9)



---

## 🧰 Stack & Tools

| Layer | Technology |
|-------|-----------|
| **Database** | MySQL |
| **Cloud Hosting** | Google Cloud Platform (Cloud SQL) |
| **Mobile App** | Google AppSheet |
| **BI & Visualisation** | Microsoft Power BI |
| **Data Connection** | Power BI → Cloud SQL (MySQL connector) |

---

## 🗂️ Repository Structure
```
├── images/
│   ├── erd-schema.png
│   ├── app-screen-1.png
│   ├── app-screen-2.png
│   ├── app-screen-3.png
│   └── dashboard.png
├── PowerBI_Clinical_Dashboard.pbix
└── README.md
```
