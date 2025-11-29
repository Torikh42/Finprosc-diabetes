# 🏥 Analisis & Prediksi Deteksi Dini Diabetes

Proyek ini adalah tugas akhir Data Science yang bertujuan untuk membangun model Machine Learning (**Random Forest**) guna memprediksi risiko diabetes secara dini berdasarkan data klinis pasien.

## 📋 Daftar Isi

- [Latar Belakang](#-latar-belakang)
- [Dataset](#-dataset)
- [Teknologi](#-teknologi-yang-digunakan)
- [Alur Analisis](#-alur-analisis)
- [Hasil & Kesimpulan](#-hasil--kesimpulan)
- [Cara Menjalankan](#-cara-menjalankan)
- [Author](#-author)

## 🧐 Latar Belakang

Diabetes Melitus merupakan tantangan kesehatan global. Deteksi dini seringkali terkendala biaya dan waktu. Proyek ini memanfaatkan data historis medis untuk menciptakan sistem skrining awal yang cepat dan objektif.

**Tujuan Utama:**
1.  Menangani masalah kualitas data (*missing values* tersembunyi).
2.  Membangun model prediksi klasifikasi (Sehat vs Diabetes).
3.  Mengidentifikasi faktor risiko dominan (*Feature Importance*).

## 📊 Dataset

**Sumber:** Pima Indians Diabetes Database (UCI Machine Learning Repository).

Dataset ini terdiri dari **768 baris** dan **9 kolom**:

| Kolom | Deskripsi |
| :--- | :--- |
| `Pregnancies` | Jumlah kehamilan |
| `Glucose` | Konsentrasi glukosa plasma |
| `BloodPressure` | Tekanan darah diastolik |
| `SkinThickness` | Ketebalan lipatan kulit |
| `Insulin` | Serum insulin |
| `BMI` | Indeks Massa Tubuh |
| `DiabetesPedigreeFunction` | Fungsi riwayat diabetes |
| `Age` | Umur |
| `Outcome` | Target (0 = Sehat, 1 = Diabetes) |

> [!WARNING]
> **Isu Data:** Ditemukan banyak nilai 0 pada kolom biologis (Insulin, BMI, Tekanan Darah) yang secara medis tidak valid. Hal ini ditangani dalam tahap Data Cleaning.

## 🛠 Teknologi yang Digunakan

Proyek ini dikembangkan menggunakan **Python** di lingkungan Google Colab.

-   **Pandas & NumPy:** Manipulasi dan pembersihan data.
-   **Matplotlib & Seaborn:** Visualisasi data (EDA).
-   **Scikit-Learn:** Pembuatan model (Random Forest), Preprocessing (StandardScaler), dan Evaluasi.

## 🔄 Alur Analisis

1.  **Data Collection:**
    -   Mendukung pemuatan data otomatis dari Google Drive maupun URL publik (GitHub) sebagai fallback.
2.  **Data Cleaning (Imputasi):**
    -   Mendeteksi nilai 0 pada kolom `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, dan `BMI`.
    -   Mengganti nilai 0 dengan `NaN`, kemudian mengisinya dengan nilai **Rata-rata (Mean)** kolom tersebut.
3.  **Transformation:**
    -   Melakukan Scaling menggunakan `StandardScaler` untuk menstandarisasi rentang data.
4.  **Exploratory Data Analysis (EDA):**
    -   Menganalisis korelasi antar fitur (Heatmap).
    -   Melihat distribusi Glukosa antara pasien sehat dan diabetes.
5.  **Modeling:**
    -   Menggunakan algoritma **Random Forest Classifier** (`n_estimators=100`).
    -   Split data: 80% Training, 20% Testing.

## 📈 Hasil & Kesimpulan

### Performa Model
-   **Akurasi:** ~75.32%
-   **Evaluasi:** Model mampu membedakan pasien diabetes dan non-diabetes dengan cukup baik untuk tahap skrining awal.

### Insight Medis (Feature Importance)
Berdasarkan analisis model, 3 faktor risiko terbesar adalah:
1.  **Glukosa (Glucose):** Indikator paling dominan.
2.  **BMI:** Berat badan berlebih memiliki korelasi kuat.
3.  **Umur (Age):** Risiko meningkat seiring bertambahnya usia.

## 🚀 Cara Menjalankan

### Google Colab (Direkomendasikan)
1.  Upload file `sc-Analisisdiabetes.ipynb` ke Google Colab.
2.  Upload file `diabetes.csv` ke Google Drive Anda (atau biarkan kode mendownload otomatis dari internet jika tersedia).
3.  Jalankan semua sel secara berurutan.

## 👤 Author

**Torikh Abdullah Naser**

*   **Program studi:** S1 Sistem Informasi
*   **Universitas:** UPN "Veteran" Jakarta
*   **Email:** torikh42@gmail.com

---
*Dibuat sebagai bagian dari Final Project Data Science.*