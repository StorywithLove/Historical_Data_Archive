# Historical Data Archive

> This repository archives **historical data** from the real-time database.

---

## 🔗 Real-Time Database

- Repository: [StorywithLove/workflow](https://github.com/StorywithLove/workflow)  
- Retention: Only keeps **the latest 1 year** of data  
- Purpose: All historical data **beyond one year** will be archived in this repository

---

## 🗂️ Archive Structure

- Data is organized by **source** and **date**. **source** contains CNEMC, ZJEMC, ... etc.

- Each day has **one folder**, ideally containing **24 hourly CSV files**.
```
Archive/  
  CNEMC/  
    YYYY-MM-DD/
      YYYY-MM-DDT00.csv
      YYYY-MM-DDT01.csv
    ...
```
---

## ⚙️ Sync Rule

- **Automatic synchronization**:  
- Runs at **09:00 AM on the 1st day of each month**
- Synchronizes **all data of the previous month** from the real-time database to this archive
- **Historical data handling**:  
- If certain hourly files are missing, the task **skips missing files** but continues syncing other files
- Only existing date folders are synced

---

## 📌 Notes

- CNEMC and ZJEMC follow the **same folder structure**  
- The repository is **read-only for historical data**; all updates come from automated monthly sync  
- You can manually trigger a sync for a specific month via **GitHub Actions** workflow

---

## 🏷️ Quick Overview

| Feature                  | Description                                   |
|---------------------------|-----------------------------------------------|
| Source repo               | [StorywithLove/workflow](https://github.com/StorywithLove/workflow) |
| Sync frequency            | Monthly (1st day of month, 09:00 AM)         |
| Default sync data         | Previous month's historical data              |
| Folder structure          | `Archive/<Source>/<YYYY-MM-DD>/<Hourly CSV>` |
| Missing files handling    | Skipped, with warnings                        |

---

*Maintained by the automation workflow for historical data archival.*
