# Customer Personality Segmentation using K-Means Clustering

Proyek ini merupakan implementasi **Unsupervised Learning** untuk mengelompokkan pelanggan berdasarkan karakteristik demografi (*personality*) dan perilaku transaksi menggunakan algoritma **K-Means Clustering** serta reduksi dimensi **Principal Component Analysis (PCA)**.

---

## Latar Belakang & Tujuan
Pendekatan pemasaran secara massal sering kali kurang efektif karena perbedaan daya beli dan preferensi tiap pelanggan. Proyek ini bertujuan untuk:
1. Melakukan *data preprocessing* (imputasi *missing value*, *One-Hot Encoding*, dan *StandardScaler*) pada dataset campuran numerik dan kategorikal (`cpa.csv`).
2. Menentukan jumlah klaster optimal ($k$) menggunakan **Elbow Method** dan **Silhouette Score**.
3. Memvisualisasikan segmen pelanggan ke dalam ruang 2 dimensi menggunakan **PCA**.
4. Menyusun *customer profiling* serta rekomendasi strategi bisnis berbasis data untuk setiap klaster.

---

## Struktur Repository
* `Tugas3_Arrahim.ipynb` — Notebook utama berisi eksplorasi data, preprocessing, pemodelan K-Means, visualisasi PCA, dan profiling pelanggan.
* `cpa.csv` — Dataset Customer Personality Analysis (2.240 baris × 29 kolom).
* `README.md` — Dokumentasi dan ringkasan hasil analisis proyek.

---

## Tahapan Analisis
1. **Exploratory Data Analysis (EDA):** Pengecekan struktur dataset (`2.240 × 29`), tipe data, statistik deskriptif, dan deteksi *missing value* (24 baris kosong pada fitur `Income`).
2. **Data Preprocessing:**
   * Menghapus kolom non-prediktif (`ID` dan `Dt_Customer`).
   * Imputasi *missing value* pada `Income` menggunakan nilai **median**.
   * Transformasi fitur kategorikal (`Education` & `Marital_Status`) dengan **One-Hot Encoding** (menghasilkan total 38 fitur numerik).
   * Standardisasi fitur menggunakan **StandardScaler**.
3. **Klasterisasi & Evaluasi:** Evaluasi nilai $k=2$ hingga $k=10$ menggunakan *Elbow Method* dan *Silhouette Score*, menghasilkan **$k=3$** sebagai jumlah segmen optimal.
4. **Visualisasi & Profiling:** Proyeksi klaster menggunakan PCA 2D dan analisis rata-rata fitur utama tiap klaster.

---

## Ringkasan Hasil Segmentasi (k = 3)

| Segmen Klaster | Karakteristik Utama | Rekomendasi Strategi Bisnis |
| :--- | :--- | :--- |
| **Cluster 0**<br>*(Premium / VIP Customers)* | Pendapatan tertinggi (77.440), pengeluaran sangat dominan pada produk *wine* & daging, minim penggunaan diskon, dan tingkat respons promosi tertinggi (30,18%). | Program loyalitas eksklusif (*VIP Membership*), penawaran produk edisi terbatas (*premium line*), tanpa perlu bergantung pada potongan harga. |
| **Cluster 1**<br>*(Low-Income / Budget Shoppers)* | Pendapatan terendah (34.537), mayoritas memiliki anak kecil di rumah, serta total pengeluaran belanja paling rendah di seluruh kategori. | Paket *bundling* kebutuhan pokok ekonomis, kupon diskon langsung, dan program *cashback* untuk mendorong transaksi. |
| **Cluster 2**<br>*(Middle-Class / Deal Seekers)* | Pendapatan menengah (57.925), mayoritas memiliki anak remaja, aktif berbelanja secara *online*, dan memiliki frekuensi transaksi diskon tertinggi. | Kampanye *email marketing* untuk promo *Flash Sale*, diskon khusus transaksi web, serta promo berbasis ambang batas minimal belanja. |

---

## Teknologi & Library
* **Python 3**
* **Pandas & NumPy** (Manipulasi dan pembersihan data)
* **Scikit-Learn** (`SimpleImputer`, `OneHotEncoder`, `StandardScaler`, `KMeans`, `PCA`, `silhouette_score`)
* **Matplotlib & Seaborn** (Visualisasi data)

---

## Penulis
**Arrahim** — Mahasiswa S1 Sains Data, Universitas Terbuka
