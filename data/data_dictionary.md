# Data Dictionary — TalentHub HR Retention

Dataset contains 1,983 employee records from TalentHub Indonesia (2018–2026).

| Column | Data Type | Description | Example |
|---|---|---|---|
| `employee_id` | string | Unique identifier for each employee | EMP-0012 |
| `department` | string | Department where the employee works | Customer Support |
| `join_date` | date | Date the employee joined the company | 2021-03-15 |
| `tenure` | float | Years of service at time of record | 2.5 |
| `salary` | integer | Monthly salary in IDR | 8500000 |
| `performance` | integer | Performance score (1–5 scale) | 4 |
| `satisfaction` | integer | Job satisfaction score (1–5 scale) | 3 |
| `work_hours` | float | Average weekly working hours | 42.5 |
| `promotion_history` | integer | Number of promotions received | 1 |
| `resign_status` | boolean | Whether the employee has resigned | 1 = Resigned, 0 = Active |
