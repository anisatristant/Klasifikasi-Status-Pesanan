# 🍔 Analisis Mitigasi Risiko Transaksi Food Delivery: Prediksi Pembatalan & Refund

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Random Forest](https://img.shields.io/badge/Algorithm-Random%20Forest-blue?style=for-the-badge)

## 📌 Deskripsi Proyek
Proyek Data Mining ini bertujuan untuk membangun model prediktif yang mampu mengidentifikasi potensi kegagalan transaksi (pembatalan atau refund) pada layanan *Food Delivery*. Dengan memprediksi risiko ini lebih awal, perusahaan dapat melakukan intervensi proaktif untuk menjaga kepuasan pelanggan dan menekan kerugian finansial.

**Masalah Bisnis:** 
Tingginya angka refund dan pembatalan pesanan secara mendadak mengakibatkan kerugian operasional dan menurunnya tingkat kepercayaan pelanggan.

**Tujuan:** 
Membangun klasifikasi status pesanan (Selesai, Dibatalkan, Refund) berdasarkan variabel operasional seperti keluhan pelanggan, rating, jarak, dan harga.

---

## 📊 Dataset & Fitur
Dataset yang digunakan berasal dari **Kaggle** (Synthetic Food Delivery Dataset) yang mencakup:
- **Fitur Utama:** Harga Pesanan, Jarak Kirim (KM), Waktu Tunggu (Menit), Status Promo, Tingkat Keluhan, Kategori Menu, dan Rating Pelanggan.
- **Target:** `Status_Pesanan` (Selesai, Dibatalkan, Refund).

---

## 🛠️ Metodologi & Tahapan Kerja
1. **Data Preprocessing:**
   - Handling missing values menggunakan median.
   - Outlier capping pada fitur `Harga_Pesanan`.
   - Encoding data kategorikal (Label Encoding).
2. **Handling Class Imbalance:** 
   - Menggunakan parameter `class_weight='balanced_subsample'` pada algoritma Random Forest untuk menangani jumlah data "Refund" yang sangat sedikit dibanding "Selesai".
3. **Modeling:** 
   - Algoritma: **Random Forest Classifier** (200 Estimators).
   - Validasi: Train-Test Split (80:20).
4. **Evaluasi:** 
   - Menggunakan Confusion Matrix dan F1-Score untuk mengukur performa pada kelas-kelas minoritas (Refund & Batal).

---

## 📈 Hasil & Insight Utama

### 1. Performa Model
Model mencapai akurasi **87%**. Meskipun akurasi tinggi, analisis **Confusion Matrix** menunjukkan bahwa model sangat kuat dalam memprediksi pesanan "Selesai", namun masih memiliki tantangan dalam mendeteksi kelas "Refund" karena keterbatasan data historis pada kategori tersebut.

### 2. Faktor Kunci (Feature Importance)
Berdasarkan analisis model, dua faktor utama yang paling memicu kegagalan transaksi adalah:
- **Rating Pelanggan:** Rating rendah merupakan sinyal terkuat terjadinya refund.
- **Tingkat Keluhan:** Kenaikan tingkat keluhan berbanding lurus dengan probabilitas pembatalan.

### 3. Rekomendasi Bisnis
- **Sistem Early Warning:** Perusahaan dapat mengintegrasikan model ini ke sistem operasional. Jika sistem mendeteksi pesanan dengan probabilitas "Refund" tinggi, tim Customer Service dapat segera memberikan kompensasi atau prioritas layanan.
- **Audit Vendor:** Restoran dengan pola pembatalan tinggi yang terdeteksi oleh model harus dievaluasi kualitas layanannya.

---

## 🚀 Cara Menjalankan Project
1. Clone repository ini.
2. Upload file `.ipynb` ke [Google Colab](https://colab.research.google.com/).
3. Pastikan dataset `synthetic_fooddelivery_dataset.csv` tersedia di path yang sesuai.
4. Jalankan semua cell.

---

## 👤 Penulis
**[Annisa Tristanti]**  
*Data Science Enthusiast | [https://www.linkedin.com/in/annisatristanti/]*
