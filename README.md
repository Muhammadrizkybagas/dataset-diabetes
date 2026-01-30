# NHANES Dataset (XPT to CSV)

Repository ini berisi **dataset NHANES (National Health and Nutrition Examination Survey)** yang telah **dikonversi dari format `.xpt` (SAS Transport File) menjadi `.csv`** agar lebih mudah digunakan melalui GitHub.


## Struktur Dataset
- `.csv` → Dataset NHANES hasil konversi dari file `.xpt`
- Setiap file CSV merepresentasikan data yang sama dengan file XPT aslinya

Dataset dikonversi dari format `.xpt` ke `.csv` menggunakan Python, tanpa mengubah isi maupun struktur variabel aslinya.

```
import pandas as pd

file_names = ["DEMO_J", "BMX_J", "GHB_J", "GLU_J"]

for name in file_names:
    df_temp = pd.read_sas(f"{name}.xpt", format="xport")
    df_temp.to_csv(f"{name}.csv", index=False)

```

> **Catatan:** Konversi hanya mengubah format file, **tidak mengubah isi data**.

## Sumber Data
Data berasal dari situs resmi NHANES (CDC):  
https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/7

---
