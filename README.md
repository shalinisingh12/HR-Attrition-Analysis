# 📊 HR Attrition Analysis: A Strategic Approach to Employee Retention

## 📝 Project Overview  
This project focuses on analyzing employee attrition at **TechIT Solutions**, a service-based company with **10,000 employees**.  
The company was facing a **22.47% attrition rate**, causing financial losses, disruption in projects, and low employee morale.  

The goal of this project is to **identify the key drivers of attrition** and provide **data-backed recommendations** for HR and leadership to improve employee retention.  

---

## 🎯 Business Objectives  
- What is the overall attrition rate?  
- Which department faces the highest attrition and why?  
- How do **job roles** influence attrition?  
- Is **overtime** contributing to attrition?  
- Does **distance from home** affect attrition?  
- How do **job satisfaction** and **environment satisfaction** impact retention?  
- Are employees with **frequent business travel** more likely to leave?  
- Do **salary hikes** influence employee retention effectively?  

---

## 🔧 Tools & Techniques Used  
- **SQL (PostgreSQL):** Data Modification 
- **Power BI:** Dashboard creation, data visualization, and KPI tracking.  
- **Business Analysis Approach:** Identifying stakeholders, asking the right questions, and converting data into actionable insights.  

---

## 👥 Stakeholders  
- **HR Department:** Improve retention strategies.  
- **Department Heads & Team Leads:** Reduce workload issues and improve team management.  
- **Recruitment Team:** Plan hiring effectively for high-attrition roles.  
- **Business Leaders/Executives:** Make informed workforce decisions.  

---

## 📊 Dashboard Preview  
 
(https://github.com/shalinisingh12/HR-Attrition-Analysis/blob/main/Screenshot%202025-09-24%20144423.png)

---

## 📈 Key Insights  
- Employees working **overtime** show higher attrition rates.  
- Certain **departments and roles** face significantly higher turnover.  
- Employees living **farther from the office** are more likely to leave.  
- **Job satisfaction** and **work environment** strongly impact retention.  

---

## 🚀 Business Impact  
- Helped identify **root causes of attrition**.  
- Enabled HR to **design targeted strategies** (timely promotions, role changes, tailored benefits).  
- Improved decision-making for executives with **data-backed insights**.  
- Reduced costs associated with hiring, onboarding, and training new employees.  

---

## 📂 Repository Structure    
- `README.md` → Documentation of the project.
- `dashboard_screenshot.png` → Power BI dashboard preview.
- - `presentation.pdf` → Project presentation slides

---

  

## 🙌 Acknowledgments  
This project was created as part of my learning journey in **Business Analytics** and showcases how data can drive better decision-making in HR.  


SQL Code:
-- 1. Create Database
CREATE DATABASE project;

-- Connect to the database
\c project

-- 2. Create Table
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    age INT,
    attrition VARCHAR(3),
    business_travel VARCHAR(20),
    department VARCHAR(30),
    distance_from_home INT,
    education VARCHAR(15),
    environment_satisfaction INT,
    gender VARCHAR(10),
    salary NUMERIC,
    job_involvement INT,
    job_level INT,
    job_role VARCHAR(50),
    job_satisfaction INT,
    marital_status VARCHAR(30),
    number_of_companies_worked_previously INT,
    overtime VARCHAR(5),
    salary_hike_in_percent INT,
    total_working_years_experience INT,
    work_life_balance INT,
    no_of_years_worked_at_current_company INT,
    no_of_years_in_current_role INT,
    years_since_last_promotion INT
);

-- 3. Import CSV file
-- If running in pgAdmin, use \copy for client-side import
\copy employees 
FROM 'C:/Users/dell/Downloads/HR_Attrition_Analysis/archive/HR_Attrition_dataset.csv' 
DELIMITER ',' CSV HEADER;

-- 4. Insert extra records manually
INSERT INTO employees (
    employee_id, age, attrition, business_travel, department, distance_from_home, education,
    environment_satisfaction, gender, salary, job_involvement, job_level, job_role, job_satisfaction,
    marital_status, number_of_companies_worked_previously, overtime, salary_hike_in_percent,
    total_working_years_experience, work_life_balance, no_of_years_worked_at_current_company,
    no_of_years_in_current_role, years_since_last_promotion
)
VALUES
(10001, 29, 'No', 'Travel Rarely', 'Sales', 8, 'Graduation', 3, 'Male', 55000, 3, 1, 'HR', 4, 'Single', 1, 'No', 12, 5, 3, 2, 2, 1),
(10002, 41, 'Yes', 'Travel Frequently', 'IT', 15, 'Postgraduate', 2, 'Female', 73000, 2, 2, 'IT', 3, 'Married', 3, 'Yes', 20, 12, 2, 4, 3, 2),
(10003, 34, 'No', 'Non-Travel', 'Finance', 5, 'Doctorate', 4, 'Male', 91000, 4, 3, 'Manager', 4, 'Divorced', 4, 'No', 15, 9, 4, 6, 4, 1),
(10004, 26, 'Yes', 'Travel Rarely', 'Marketing', 20, 'Graduation', 1, 'Female', 48000, 2, 1, 'Developer', 2, 'Single', 2, 'Yes', 10, 3, 2, 1, 1, 0),
(10005, 38, 'No', 'Travel Frequently', 'Operations', 10, 'Postgraduate', 3, 'Male', 82000, 3, 3, 'Business Analyst', 3, 'Married', 5, 'No', 17, 11, 3, 5, 5, 3);

-- 5. Verify records
SELECT COUNT(*) AS total_employees FROM employees;
SELECT * FROM employees LIMIT 10;
