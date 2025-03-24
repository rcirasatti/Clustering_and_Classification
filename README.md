# Project: Clustering dan Klasifikasi Data Navigasi Kapal

## Deskripsi Proyek
Proyek ini bertujuan untuk mengelompokkan data navigasi kapal menggunakan algoritma **DBSCAN** untuk clustering dan mengklasifikasikan hasilnya menggunakan **Random Forest** serta **Decision Tree**. Data yang digunakan mencakup berbagai fitur navigasi seperti kecepatan, daya mesin, dan efisiensi perjalanan.

## Dataset
Dataset yang digunakan berisi informasi terkait pergerakan kapal, termasuk:
- **Speed_Over_Ground_knots**: Kecepatan kapal dalam knot.
- **Engine_Power_kW**: Daya mesin dalam kilowatt.
- **Distance_Traveled_nm**: Jarak yang telah ditempuh dalam nautical miles.
- **Efficiency_nm_per_kWh**: Efisiensi kapal dalam nautical miles per kilowatt-hour.
- **Average_Load_Percentage**: Rata-rata beban mesin dalam persen.
- **Efficiency_per_Power**: Efisiensi berdasarkan daya mesin.
- **Speed_per_Distance**: Kecepatan relatif terhadap jarak.

## Metode yang Digunakan
1. **Clustering dengan DBSCAN**
   - DBSCAN digunakan untuk menemukan kelompok kapal berdasarkan perilaku navigasinya.
   - Parameter utama: `eps` dan `min_samples` disesuaikan agar sesuai dengan karakteristik dataset.
   
2. **Klasifikasi dengan Random Forest dan Decision Tree**
   - Hasil clustering digunakan sebagai label untuk membangun model klasifikasi.
   - **Random Forest** digunakan sebagai model utama karena kemampuannya menangani fitur non-linear.
   - **Decision Tree** digunakan untuk perbandingan karena lebih mudah diinterpretasikan.

## Evaluasi Model
### Hasil Sebelum dan Sesudah Hyperparameter Tuning

| Metric      | Random Forest (Baseline) | Random Forest (Tuned) | Decision Tree (Baseline) | Decision Tree (Tuned) |
|------------|-------------------------|----------------------|-------------------------|----------------------|
| Accuracy   | 0.970266                 | 0.971831            | 0.956182                 | 0.956182            |
| Precision  | 0.961910                 | 0.962885            | 0.967444                 | 0.967444            |
| Recall     | 0.970266                 | 0.971831            | 0.956182                 | 0.956182            |
| F1-Score   | 0.962433                 | 0.963358            | 0.958302                 | 0.958302            |

### Analisis Kinerja Model
- **Random Forest menunjukkan kinerja lebih baik dibandingkan Decision Tree**, terutama setelah tuning.
- **Hyperparameter tuning pada Random Forest memberikan sedikit peningkatan akurasi dan F1-Score.**
- **Decision Tree tidak mengalami perubahan kinerja setelah tuning**, kemungkinan karena kompleksitas modelnya lebih rendah dibandingkan Random Forest.

## Identifikasi Kelemahan Model
1. **Precision rendah untuk beberapa kelas**
   - Model mengalami kesulitan dalam membedakan kapal dengan karakteristik mirip.
   - Hal ini bisa disebabkan oleh distribusi data yang tidak seimbang atau jumlah sampel yang kurang banyak.

2. **Potensi overfitting pada Random Forest setelah tuning**
   - Meskipun akurasi meningkat, perlu dicek apakah model terlalu menyesuaikan diri dengan data latih.
   - Bisa dilakukan dengan melihat perbedaan performa pada data uji dan validasi.

## Rekomendasi Tindakan Lanjutan
1. **Menambah jumlah data atau melakukan augmentasi**
   - Jika jumlah sampel masih terbatas, model bisa diperbaiki dengan lebih banyak data.

2. **Menguji algoritma lain selain Decision Tree dan Random Forest**
   - Coba **Gradient Boosting atau XGBoost** untuk melihat apakah ada peningkatan performa.
   
3. **Memperbaiki preprocessing data**
   - Memastikan semua fitur relevan dan mempertimbangkan teknik normalisasi atau standarisasi.

4. **Menyesuaikan parameter DBSCAN**
   - DBSCAN sensitif terhadap parameter `eps` dan `min_samples`, sehingga tuning lebih lanjut bisa dilakukan.

---
**Kesimpulan:**
DBSCAN berhasil mengelompokkan data navigasi kapal berdasarkan pola pergerakan, dan hasilnya dapat diklasifikasikan dengan baik menggunakan Random Forest dan Decision Tree. Random Forest menunjukkan hasil yang lebih baik, terutama setelah tuning. Namun, perlu dilakukan perbaikan lebih lanjut agar model lebih optimal dan tidak mengalami overfitting.

---
### Author
Rucirasatti Nariswana 😊

