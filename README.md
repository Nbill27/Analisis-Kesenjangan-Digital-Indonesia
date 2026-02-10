# 🇮🇩 Bridging the Digital Divide: Pemetaan Kesenjangan Infrastruktur Digital Pendidikan

![Competition](https://img.shields.io/badge/Competition-Digitalisasi_Kreatif_2025-orange?style=for-the-badge)
![Method](https://img.shields.io/badge/Method-K--Means_Clustering-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Final_Submission-success?style=for-the-badge)

> **🏆 Project ini diajukan sebagai karya final untuk Lomba Data Mining dengan tema: "Digitalisasi Kreatif: One Goal, Thousand Hopes".**

---

# Pemetaan Kesenjangan Infrastruktur Digital Pendidikan
di Indonesia di Era Society 5.0 Menggunakan K-Means

Clustering

## 👨‍💻 Identitas Tim

| Properti | Detail |
| :--- | :--- |
| **Nama Tim** | BISMILLAH JUARA 1 WKWK |
| **Institusi** | Universitas Bina Insani |

### 👥 Anggota Tim

| Nama Anggota | Peran | Fokus & Tanggung Jawab |
| :--- | :--- | :--- |
| **Renaldi Triharsono** | *Data Engineer* | Pengumpulan data (Data Collection), pembersihan data (Cleaning), dan integrasi dataset (Data Merging). |
| **Muhammad Nabil Deja** | *Data Scientist* | Pemodelan (Clustering K-Means), evaluasi model (Silhouette Score), dan visualisasi data interaktif (Mapping & Charting). |
| **Aditya Dwi Setiawan** | *Research Analyst* | Riset literatur, analisis kebijakan, penyusunan laporan ilmiah, dan pengembangan materi presentasi. |
---

## 📌 Latar Belakang Masalah
Menyongsong era **Society 5.0**, pendidikan berbasis teknologi menjadi prasyarat mutlak untuk mencetak SDM unggul menuju **Indonesia Emas 2045**. Pemerintah telah merespons dengan berbagai kebijakan digitalisasi pendidikan.

Namun, realitas di lapangan menunjukkan adanya **Kesenjangan Digital (*Digital Divide*)** yang tajam antarwilayah.
* **Masalah:** Banyak sekolah menerima bantuan perangkat (laptop/komputer), namun infrastruktur dasar (Listrik & Sinyal) di daerah tersebut belum siap.
* **Dampak:** Inefisiensi anggaran dan ketidaktepatan sasaran bantuan.
* **Solusi:** Project ini menggunakan **Data Mining** untuk memetakan kondisi infrastruktur secara objektif, sehingga pemerintah dapat menentukan prioritas penanganan yang tepat (apakah butuh Sinyal dulu, atau Perangkat dulu?).

---

## 🎯 Tujuan Penelitian
1.  **Memetakan** 34 provinsi di Indonesia ke dalam zona prioritas (Merah, Kuning, Hijau) berdasarkan kesiapan infrastruktur.
2.  **Mendiagnosis** akar masalah ketertinggalan di daerah 3T (apakah karena faktor ekonomi, fisik, atau digital?).
3.  **Memberikan rekomendasi** kebijakan berbasis data (*data-driven*) yang presisi.

---

## 🗂️ Dataset & Fitur
Dataset merupakan hasil agregasi (*data blending*) dari sumber resmi pemerintah (BPS & Kemendikbud) tahun 2021-2024.

**5 Indikator Utama yang Digunakan:**
| Atribut | Deskripsi | Peran dalam Model |
| :--- | :--- | :--- |
| `Pengeluaran_per_Kapita` | Rata-rata pengeluaran penduduk (Ribuan Rp). | Indikator Ekonomi |
| `Sumber_Listrik_PLN` | Persentase rumah tangga pengguna PLN. | Infrastruktur Fisik Dasar |
| `BTS_Sinyal_Kuat` | Jumlah Menara BTS (Khusus 4G & 5G). | Infrastruktur Konektivitas |
| `Proporsi_Internet_Sekolah` | Persentase SD yang memiliki akses internet. | Fasilitas Digital |
| `Rasio_Komputer_Sekolah` | Rata-rata ketersediaan komputer per sekolah. | Fasilitas Hardware |

---

## ⚙️ Metodologi
Penelitian ini menggunakan metode **Unsupervised Learning** dengan alur kerja sebagai berikut:

1.  **Data Preprocessing:** Cleaning, Normalisasi nama provinsi, dan Scaling (StandardScaler).
2.  **Feature Engineering:** Memisahkan sinyal 2G/3G (lemah) dan hanya menggunakan 4G/5G (kuat) agar relevan dengan kebutuhan pendidikan digital.
3.  **Modeling (K-Means):**
    * Penentuan K Optimal menggunakan **Elbow Method** (Didapat K=3).
    * Validasi model menggunakan **Silhouette Score**.
4.  **Prescriptive Analytics:** Ranking provinsi berdasarkan skor kesiapan gabungan.

---

## 📊 Hasil Analisis & Visualisasi

Berdasarkan algoritma K-Means, Indonesia terbagi menjadi 3 Zona Realitas:

### 1. Peta Zonasi Kesenjangan Digital
*Visualisasi spasial sebaran zona di seluruh kepulauan Indonesia*
![Peta ](Visualisasi/Visual_2_Peta.png)

### 2. Peta Sebaran (Scatter Plot)
*Hubungan antara Ekonomi vs Ketersediaan Internet. Terlihat Zona Merah tertinggal di kedua aspek*
![Scatter Plot](Visualisasi/Visual_1_Scatter.png)

### 3. Profil Karakteristik Zona
| Zona | Status | Karakteristik Utama | Rekomendasi Kebijakan |
| :--- | :--- | :--- | :--- |
| **Cluster 0** | 🔴 **Prioritas Tinggi** (Tertinggal) | Infrastruktur fisik (Listrik & Sinyal) minim, Ekonomi rendah. | **Fokus Fisik:** Pembangunan Tower BTS 4G & Gardu Listrik. |
| **Cluster 1** | 🟡 **Transisi** (Sedang) | Infrastruktur dasar memadai, namun rasio perangkat di sekolah masih kurang. | **Fokus Akses:** Pengadaan Laptop/PC & Pelatihan Guru. |
| **Cluster 2** | 🟢 **Maju** (Aman) | Ekosistem digital matang, Ekonomi tinggi. | **Fokus Kualitas:** Peningkatan konten LMS & Kurikulum Digital. |

### 4. Top 5 Provinsi Prioritas Penanganan
Daerah dengan skor kesiapan terendah yang membutuhkan intervensi segera:
1.  **Papua Barat**
2.  **Papua**
3.  **Maluku**
4.  **Maluku Utara**
5.  **Sulawesi Barat**

---

## 🛠️ Tools & Libraries
* **Bahasa:** Python 3.10
* **Data Processing:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (KMeans, PCA, Metrics)
* **Visualization:** Matplotlib, Seaborn, Geopandas

---

## 📂 Struktur File
* `MASTER v2.csv`: Dataset utama yang sudah bersih.
* `Analisis_Kesenjangan.ipynb`: Source code lengkap (Jupyter Notebook).
* `HASIL_AKHIR.csv`: Hasil clustering beserta label zonanya.
* `/Visualisasi`: Folder berisi gambar output (Peta, Grafik).

---
*Project ini dibuat dengan ❤️ untuk kemajuan pendidikan Indonesia.*
