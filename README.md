# Analisis Profil Pelanggan Kartu Kredit (Clustering & Klasifikasi)

## Disusun Oleh: 
#### Nama: Fariz Husain Albar    
#### Instansi: UIN Sunan Kalijaga Yogyakarta

#### Submission Akhir - Dicoding Academy 

---

## Deskripsi Proyek
Proyek ini bertujuan untuk melakukan segmentasi pelanggan kartu kredit berdasarkan perilaku transaksi mereka (*Clustering*) dan membangun model prediksi untuk mengklasifikasikan pelanggan baru ke dalam segmen yang telah terbentuk (*Klasifikasi*).

Alur pengerjaan dibagi menjadi dua tahap utama:
1.  **Unsupervised Learning (Clustering):** Mengelompokkan data pelanggan mentah yang tidak memiliki label menjadi beberapa cluster karakteristik.
2.  **Supervised Learning (Klasifikasi):** Menggunakan hasil cluster tersebut sebagai "label" target untuk melatih model Machine Learning agar dapat memprediksi kategori pelanggan secara otomatis.

## Struktur File
Berikut adalah penjelasan mengenai file yang terdapat dalam repositori ini:

| Nama File | Deskripsi |
| :--- | :--- |
| `Customer Data.csv` | **Dataset Mentah**. Data transaksi kartu kredit pelanggan (8950 baris) yang belum memiliki label kelas. |
| `[Clustering]...ipynb` | **Notebook Tahap 1**. Berisi proses EDA, Preprocessing, dan pemodelan Clustering (K-Means/DBSCAN) untuk menemukan pola pelanggan. |
| `hasil_clustering.csv` | **Dataset Hasil Olahan**. Output dari tahap 1, berisi data pelanggan yang sudah bersih ditambah kolom baru: `Cluster`. |
| `[Klasifikasi]...ipynb` | **Notebook Tahap 2**. Berisi proses pelatihan model klasifikasi (Random Forest/Decision Tree) menggunakan data dari `hasil_clustering.csv`. |

## Dataset
Dataset yang digunakan berisi perilaku penggunaan kartu kredit dari 9000+ pelanggan aktif.
* **Sumber:** *Credit Card Dataset for Clustering* (Kaggle/UCI).
* **Fitur Utama:**
    * `BALANCE`: Saldo yang tersisa di akun.
    * `PURCHASES`: Jumlah pembelian yang dilakukan.
    * `CASH_ADVANCE`: Penarikan tunai kartu kredit.
    * `CREDIT_LIMIT`: Batas kredit pengguna.
    * `PAYMENTS`: Jumlah pembayaran yang dilakukan pengguna.

## Metodologi

### Tahap 1: Clustering (Segmentasi)
Pada tahap ini, kita mengubah data tanpa label menjadi data berlabel.
* **Preprocessing:** Penanganan *missing values* (terutama pada `MINIMUM_PAYMENTS` dan `CREDIT_LIMIT`) dan normalisasi data (Scaling).
* **Metode:**
    * Evaluasi jumlah cluster optimal menggunakan **Elbow Method** dan **Silhouette Score**.
    * Algoritma utama: **K-Means Clustering** (atau DBSCAN).
    * Reduksi Dimensi: **PCA** (Principal Component Analysis) untuk visualisasi cluster.

### Tahap 2: Klasifikasi (Prediksi)
Setelah setiap pelanggan memiliki label "Cluster", kita akan melatih model untuk mengenali pola tersebut.
* **Input:** `hasil_clustering.csv`
* **Target:** Kolom `Cluster`.
* **Algoritma:**
    * **Decision Tree Classifier**
    * **Random Forest Classifier**
* **Evaluasi:** Menggunakan *Confusion Matrix* dan *Accuracy Score* untuk melihat seberapa tepat model menebak grup pelanggan.

## Cara Menjalankan
1.  Pastikan Python dan Jupyter Notebook sudah terinstal.
2.  Install library yang dibutuhkan:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
3.  **Langkah 1:** Buka dan jalankan `[Clustering]_Submission_Akhir_BMLP_Fariz_Husain_Albar.ipynb` terlebih dahulu untuk menghasilkan file `hasil_clustering.csv`.
4.  **Langkah 2:** Buka dan jalankan `[Klasifikasi]_Submission_Akhir_BMLP_Fariz_Husain_Albar (1).ipynb` untuk melihat performa model prediksi.

---
*Submission Akhir - Belajar Machine Learning Pemula [Dicoding Academy]*
