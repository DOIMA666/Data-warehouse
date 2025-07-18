# Data-warehouse

# 🛡️ Cybersecurity Attack Data Warehouse Project

This project was developed as part of a final assignment for the Data Warehouse course at Ho Chi Minh City University of Technology and Education (HCMUTE). The main goal is to design and implement a data warehouse and analysis pipeline for global cyberattack data from 2020 to 2023 using tools like SQL Server, SSIS, SSAS, Power BI, and Google Data Studio.

---

## 📊 Project Objectives

- Build a star schema data warehouse to analyze cybersecurity attack trends.
- Process, clean, and transform raw attack data from Kaggle.
- Load data into a structured warehouse using SQL Server Integration Services (SSIS).
- Deploy cubes and perform OLAP queries with SQL Server Analysis Services (SSAS).
- Visualize data using Power BI and Google Data Studio.
- Answer business questions related to network threats and anomalies.

---

## 📁 Dataset

- **Title**: Cyber Security Attacks  
- **Source**: [Kaggle](https://www.kaggle.com/datasets/teamincribo/cyber-security-attacks)  
- **Rows**: ~40,000  
- **Attributes**: 25 columns including:
  - `Timestamp`, `Source IP`, `Destination IP`, `Protocol`, `Packet Length`, `Attack Type`, `Severity Level`, `Country`, etc.
- Dataset cleaned and enriched with IP geolocation data via [ipinfo.io API](https://ipinfo.io/)

---

## 🧠 Technologies & Tools

- **Data Processing**: `Python`, `Pandas`, `Requests`
- **ETL**: `SQL Server Integration Services (SSIS)`
- **Data Warehouse**: `SQL Server 2022`, `Star Schema`
- **OLAP**: `SQL Server Analysis Services (SSAS)`, `Multidimensional Cube`
- **Visualization**:
  - `Power BI` (drill-down by attack type, time, severity)
  - `Google Data Studio` (top countries, anomaly scores, protocols)

---

## 🏗️ Data Warehouse Schema

- **Fact Table**:
  - `Fact_CyberSecurity`: Measures like `Packet Length`, `Anomaly Score`

- **Dimension Tables**:
  - `Dim_Timestamp` – date, month, year breakdown
  - `Dim_Address` – country locations
  - `Dim_Attack` – protocol, type, proxy info
  - `Dim_Victim` – device info, severity, action taken

---

## ⚙️ How to Run the Project

### 1. Data Preprocessing (Python)
- Located in: `Notebook/Tien_xu_ly.ipynb`
- Cleans nulls, enriches IPs with geolocation, splits country fields

### 2. Create Data Warehouse (SSIS)
- Open `Visual Studio 2022`
- Load project: `SSIS/ETL_DataWarehouse.dtsx`
- Configure SQL Server destination (`CyberSecurity` DB)
- Run `Data Flow Tasks` to load DIM and FACT tables

### 3. Deploy OLAP Cube (SSAS)
- Open SSAS project
- Set up dimensions and measures
- Deploy and browse using SSAS browser

### 4. Create Reports
- Open `Power BI` → connect to deployed SSAS cube
- Use provided filters to explore:
  - Attack trends by protocol and year
  - Top 10 attack types
  - Anomaly score distributions
- Or open `.pbix` file in `Report/`

---

## 🔍 Example Business Questions Answered

- Top 5 highest scoring cyberattacks and their methods?
- How many attacks were blocked per year?
- Which protocol generated the largest packets?
- Which country suffered the most attacks in 2022?
- Are malware attacks increasing over time?

---

## 👨‍💻 Authors (Team 15 – HCMUTE)

- Lê Hồ Quốc Huy – ETL & Data Processing  
- Nguyễn Duy Nam – Cube design & OLAP  
- Trần Bảo Việt – Power BI & Google Studio Visualization  
- Lê Quỳnh Nhựt Vinh – Schema design & SSIS

---

## 📌 Instructor  
**ThS. Nguyễn Văn Thành**  
Faculty of Information Technology, HCMUTE

---

## 📬 Contact

For further questions or collaboration, feel free to reach out via GitHub or email.

