# 🏢 TalentHub HR Retention Analysis

> Analisis attrition karyawan pada perusahaan HR consulting untuk mengidentifikasi faktor risiko resign dan memberikan rekomendasi strategis berbasis data.

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Tool](https://img.shields.io/badge/Tool-Google%20Sheets-34A853?logo=googlesheets&logoColor=white)
![Domain](https://img.shields.io/badge/Domain-HR%20Analytics-blue)
![Period](https://img.shields.io/badge/Data%20Period-2018--2026-orange)

---

## 📌 Background

Setiap karyawan yang resign bukan hanya kehilangan satu orang — tetapi juga berarti hilangnya produktivitas, meningkatnya biaya rekrutmen, terganggunya stabilitas tim, dan berkurangnya kualitas layanan kepada klien.

**TalentHub Indonesia** adalah perusahaan HR consulting yang melayani lebih dari 100 klien korporat. Tingginya attrition rate berpotensi menciptakan risiko operasional dan menghambat pertumbuhan perusahaan. Oleh karena itu, analisis ini dilakukan untuk:

- Memahami pola resign karyawan berdasarkan departemen dan tenure
- Mengidentifikasi faktor risiko utama yang mendorong attrition
- Membantu manajemen mengambil keputusan berbasis data

**Presented to:** Pak Hendro — HR Director, TalentHub Indonesia

---

## ❓ Key Questions

1. Departemen mana yang paling banyak kehilangan karyawan?
2. Profil karyawan seperti apa yang paling berisiko resign?
3. Faktor apa yang paling berpengaruh terhadap attrition?

---

## 📊 Dataset

| Info | Detail |
|---|---|
| Periode data | 2018 – 2026 |
| Total karyawan | 1.980 (setelah cleaning) |
| Raw rows | 2.011 |
| Anomali ditemukan | 30 baris (missing values + duplikat) |
| Kolom utama | `department`, `salary`, `satisfaction`, `performance`, `work_hours`, `promotion_history`, `resign_status`, `tenure` |

> ⚠️ Data bersifat internal perusahaan. Dataset tidak dipublikasikan secara penuh. Tersedia versi sample untuk keperluan review portofolio.

---

## 🛠️ Tools Used

| Tool | Fungsi |
|---|---|
| **Google Sheets** | Data cleaning, preprocessing, pivot analysis, dan dashboard |
| **Canva** | Visualisasi laporan & storytelling presentasi |

🔗 [Lihat Google Sheets (view only)](https://docs.google.com/spreadsheets/d/1Y5oFu8jkWHvGFuRvMw_ZcAjYE6GOuiql/edit?usp=sharing)

---

## 🧹 Data Cleaning Summary

Cleaning dilakukan sepenuhnya di Google Sheets menggunakan formula bawaan.

| Jenis Anomali | Jumlah | Action | Formula |
|---|---|---|---|
| Missing values (Salary / Perf / Satisfaction) | 20 | Exclude baris | `COUNTBLANK(Salary) + COUNTBLANK(Perf) + COUNTBLANK(Sat)` |
| Duplicate rows (exact match) | 10 | Keep first, drop rest | `COUNTA(rows) - ROWS(UNIQUE(all cols))` |
| **Total anomali** | **30** | | |

**Hasil:** 2.011 raw rows → **1.980 clean rows** (cross-check via `COUNTA` pada clean data)

---

## 🔍 Key Findings

### 1. Attrition Rate per Departemen

| Departemen | Total Karyawan | Resigned | Attrition Rate |
|---|---|---|---|
| Customer Support | 270 | 57 | **21.1%** ← tertinggi |
| HR | 276 | 58 | 21.0% |
| Finance | 302 | 62 | 20.5% |
| Marketing | 260 | 53 | 20.4% |
| Operations | 311 | 61 | 19.6% |
| Sales | 298 | 55 | 18.5% |
| Engineering | 263 | 45 | **17.1%** ← terendah |
| **Grand Total** | **1.980** | **391** | **19.75%** |

![Attrition by Department](reports/figures/attrition_by_dept.png)

---

### 2. Satisfaction sebagai Prediktor Utama

Karyawan dengan satisfaction score rendah jauh lebih rentan resign:

| Satisfaction Score | Total | Resigned | Resign Rate |
|---|---|---|---|
| 1 | 45 | 34 | 75.6% |
| 2 | 392 | 211 | 53.8% |
| 3 | 748 | 145 | 19.4% |
| 4 | 585 | 1 | 0.2% |
| 5 | 208 | 0 | 0.0% |

**Summary:**
- Satisfaction < 3 (Low): 437 karyawan → **56.1% resign rate**
- Satisfaction ≥ 3 (High): 1.542 karyawan → **9.5% resign rate**

![Satisfaction vs Resign](reports/figures/satisfaction_vs_resign.png)

---

### 3. Critical Tenure Window: Tahun Ke-2

| Tenure Bucket | Total Karyawan | Resigned | Attrition Rate |
|---|---|---|---|
| 0–2 tahun | 171 | 28 | 16.4% |
| **2–3 tahun** | **299** | **70** | **23.4%** ← tertinggi |
| 3–5 tahun | 561 | 119 | 21.2% |
| 5+ tahun | 947 | 174 | 18.4% |

Risiko resign paling tinggi terjadi di **tahun ke-2 hingga ke-3**, mengindikasikan adanya *critical early tenure window* yang perlu diintervensi lebih awal.

![Attrition by Tenure](reports/figures/tenure_attrition.png)

---

## 💡 Recommendations

### 1. Prioritaskan Retention di Customer Support
Departemen dengan attrition tertinggi (21.1%). Langkah yang direkomendasikan: exit interview mendalam, review workload, dan pembuatan career path yang jelas dari support → team lead → manager.

### 2. Implementasi Early Warning System Berbasis Satisfaction
Karyawan dengan satisfaction < 3 memiliki resign rate 56.1%. Jalankan pulse survey bulanan dan buat watchlist otomatis untuk karyawan berisiko tinggi agar mendapat 1-on-1 session dengan manager.

### 3. Retention Program di Tahun Ke-2
Attrition tertinggi terjadi di tenure 2–3 tahun (23.4%). Buat program **"Year 2 Check-in"** yang mencakup career conversation, compensation review, dan personal development plan.

---

## 📈 Business Impact

Implementasi ketiga rekomendasi di atas berpotensi menghasilkan:
- **Penurunan attrition rate** secara signifikan
- **Penghematan biaya rekrutmen** (estimasi: biaya rekrut = 50–200% gaji tahunan per posisi)
- **Peningkatan stabilitas tim** dan kepuasan klien korporat TalentHub

---

## 📁 Project Structure

```
talenthub-hr-retention/
├── README.md
├── .gitignore
│
├── data/
│   ├── talenthub_clean.csv        ← export dari Google Sheets
│   └── data_dictionary.md
│
├── cleaning/
│   ├── cleaning_log.md            ← dokumentasi langkah cleaning
│   └── google_sheets_link.md      ← link view-only Sheets
│
├── analysis/
│   ├── attrition_by_department.md
│   ├── attrition_driver_satisfaction.md
│   └── attrition_by_tenure.md
│
└── reports/
    ├── figures/
    │   ├── attrition_by_dept.png
    │   ├── satisfaction_vs_resign.png
    │   └── tenure_attrition.png
    └── TalentHub_HR_Retention.pdf  ← deck presentasi lengkap
```

---

## 👤 Author

**Rafly Sean Antonio** — Data Analyst

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sean%20Antonio-0A66C2?logo=linkedin)](https://linkedin.com/in/seanantonio)
[![Email](https://img.shields.io/badge/Email-rseanantonio@gmail.com-D14836?logo=gmail&logoColor=white)](mailto:rseanantonio@gmail.com)

---

*Project ini merupakan bagian dari portofolio data analyst. Data bersifat simulasi untuk keperluan pembelajaran dan demonstrasi kemampuan analisis.*
