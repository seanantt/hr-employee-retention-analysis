## Data Cleaning Log — TalentHub HR Retention

**Tool:** Google Sheets
**Link:** [View Spreadsheet](https://docs.google.com/...)

### Anomali yang ditemukan
| Jenis Anomali | Jumlah | Action |
|---|---|---|
| Missing values (Salary/Perf/Satisfaction) | 20 | Exclude |
| Duplicate rows | 10 | Keep first, drop rest |
| **Total anomali** | **30** | |

### Hasil
- Raw rows: 2,011
- Clean rows: 1,983
- Formula: `COUNTBLANK(Salary) + COUNTBLANK(Perf) + COUNTBLANK(Sat)`
