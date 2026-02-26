📦 Batch Data Ingestion & Processing with Spark

Enterprise Edition (WSL + PySpark + Data Lake + Partitioning)

📌 Project Overview

Project ini merupakan implementasi Enterprise Batch Data Pipeline menggunakan Apache Spark (PySpark) untuk memproses data transaksi e-commerce dalam skala besar.

Pipeline ini mensimulasikan praktik industri data engineering dengan pendekatan:

Batch Processing

Distributed Computing

Medallion Architecture (Raw → Clean → Curated)

Columnar Storage (Parquet)

Partitioning Strategy

Logging & Structured Output

🏗 Arsitektur Pipeline
CSV Source
   ↓
Raw Layer
   ↓
Data Cleaning & Validation
   ↓
Transformation
   ↓
Clean Layer (Parquet)
   ↓
Curated Layer (Aggregation)
   ↓
Partitioned Data Lake
📂 Struktur Project
bigdata-project/
│
├── data/
│   ├── raw/
│   ├── clean/
│   └── curated/
│
├── logs/
├── scripts/
│   └── batch_pipeline_enterprise.py
│
└── README.md
⚙️ Environment & Technology Stack

Python 3.12

Apache Spark 4.x

PySpark

OpenJDK 17

WSL (Ubuntu Linux Environment)

VS Code (Remote WSL)

🚀 Cara Menjalankan Pipeline
1️⃣ Aktifkan Virtual Environment
source venv/bin/activate
2️⃣ Jalankan Script
python3 scripts/batch_pipeline_enterprise.py

Jika berhasil, output akan menampilkan:

Spark Version

Total Raw Records

Total Cleaned Records

Top 5 Products

Category Revenue

PIPELINE COMPLETED SUCCESSFULLY

📊 Konsep yang Diimplementasikan
1️⃣ Batch Processing

Batch processing adalah pemrosesan data dalam jumlah besar secara periodik, bukan real-time.
Pipeline ini memproses file CSV transaksi harian dan menghasilkan dataset analitik.

Cocok untuk:

Rekap penjualan harian

Laporan bisnis periodik

ETL Data Warehouse

2️⃣ Mengapa Parquet Lebih Efisien

Parquet menggunakan format columnar storage, berbeda dengan CSV (row-based).

Keunggulan:

Ukuran file lebih kecil

Query lebih cepat

Mendukung compression

Membaca hanya kolom yang dibutuhkan

Hal ini membuat Parquet sangat optimal untuk kebutuhan analitik big data.

3️⃣ Partition Pruning

Data dipartisi berdasarkan kolom:

category=Computing/
category=Electronics/
category=Accessories/

Saat query difilter berdasarkan kategori tertentu, Spark hanya membaca partisi yang relevan.

Manfaat:

Performa query lebih cepat

Mengurangi disk I/O

Menghemat resource komputasi

📈 Hasil Analisis
🔝 Top 5 Produk (Berdasarkan Quantity)
Produk	Total Quantity
Tablet	40.898
Laptop	40.654
Monitor	40.629
Headphones	40.506
Phone	40.314

Produk dengan volume tertinggi adalah Tablet, diikuti oleh Laptop dan Monitor.

💰 Category Revenue

Kategori dengan total revenue terbesar adalah:

Computing

Electronics

Accessories

Kategori Computing mendominasi revenue keseluruhan.

💡 Insight Bisnis

Berdasarkan hasil analisis:

Produk kategori Computing memiliki demand tertinggi.

Tablet dan Laptop dapat menjadi fokus strategi promosi.

Potensi strategi bundling (Laptop + Headphones).

Kategori dengan revenue lebih rendah dapat diberikan diskon atau campaign khusus.

Dataset curated siap digunakan untuk dashboard BI atau data warehouse.

📦 Output Data Lake

Pipeline menghasilkan:

data/clean/parquet/
data/clean/partitioned_by_category/
data/curated/top_products/
data/curated/category_revenue/
data/curated/avg_transaction/

Semua dalam format Parquet dan siap untuk analitik lanjutan.

🧠 Enterprise Mindset yang Diterapkan

Tidak overwrite data mentah

Menggunakan explicit schema

Logging proses pipeline

Menggunakan columnar storage

Mengoptimalkan performa dengan partitioning

Membangun dataset siap BI

Pipeline ini telah memenuhi standar dasar Data Engineering Foundation Level.

📌 Status Project

✅ Spark Session berjalan
✅ Data Cleaning berhasil
✅ Aggregation berhasil
✅ Parquet & Partitioning berhasil
✅ Pipeline Completed Successfully

📎 Author

M. Delfian Tirta Nugraha
