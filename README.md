# Pendekatan Berkelanjutan dalam Menyeimbangkan Pertumbuhan Ekonomi dan Emisi GHG

## Studi Komparatif China, Amerika Serikat, Jepang, dan Jerman sebagai Rekomendasi untuk Indonesia

## Deskripsi Proyek

Proyek ini merupakan **Final Project Startup Campus Batch 7 (MSIB)** yang dikerjakan oleh **Tim TerraBytes**.

Penelitian ini bertujuan untuk menganalisis hubungan antara pertumbuhan ekonomi, konsumsi energi, energi terbarukan, dan emisi Gas Rumah Kaca (GHG) melalui studi komparatif pada lima negara, yaitu Indonesia, China, Amerika Serikat, Jepang, dan Jerman.

Hasil analisis digunakan untuk mengidentifikasi negara yang paling efisien dalam menyeimbangkan pertumbuhan ekonomi dan pengendalian emisi, serta menghasilkan rekomendasi kebijakan yang dapat diterapkan Indonesia dalam mendukung pembangunan berkelanjutan.

---

## Latar Belakang

Pertumbuhan ekonomi sering kali diikuti oleh peningkatan konsumsi energi dan emisi Gas Rumah Kaca (GHG). Tantangan utama bagi Indonesia adalah bagaimana meningkatkan aktivitas ekonomi dan industrialisasi tanpa meningkatkan emisi secara signifikan.

Melalui analisis data ekonomi, energi, dan lingkungan dari negara-negara industri besar, proyek ini berupaya menemukan praktik terbaik yang dapat menjadi referensi bagi Indonesia dalam mempercepat transisi menuju energi bersih dan pembangunan rendah karbon.

---

## Tujuan Proyek

* Menganalisis hubungan antara pertumbuhan ekonomi dan emisi GHG.
* Membandingkan efisiensi energi antar negara.
* Mengidentifikasi faktor yang memengaruhi emisi Gas Rumah Kaca.
* Membangun model prediksi emisi menggunakan Machine Learning.
* Melakukan forecasting tren emisi Indonesia menggunakan Prophet.
* Memberikan rekomendasi kebijakan energi berkelanjutan untuk Indonesia.

---

## Dataset

### Sumber Data

Organisation for Economic Co-operation and Development (OECD)

### Jumlah Data

* 130 observasi
* 10 variabel

### Variabel Target

| Variabel                       |
| ------------------------------ |
| Production-based GHG Emissions |

### Variabel Prediktor

* Real GDP per Capita
* Renewable Energy Supply
* Energy Consumption Agriculture, Forestry and Fishing
* Energy Consumption Industry (Except Construction)
* Energy Consumption Services
* Energy Consumption Transportation and Storage
* Energy Consumption Other

---

## Data Preparation

### Data Cleaning

* Tidak ditemukan missing values.
* Tidak ditemukan data duplikat.

### Outlier Handling

Deteksi outlier dilakukan menggunakan metode **Interquartile Range (IQR)**.

* Ditemukan 5 outlier.
* Outlier diganti menggunakan nilai median untuk menjaga distribusi data.

### Feature Encoding

Variabel negara dikonversi ke bentuk numerik:

| Negara    | Kode |
| --------- | ---- |
| China     | 0    |
| Germany   | 1    |
| Indonesia | 2    |
| Japan     | 3    |
| USA       | 4    |

---

## Feature Engineering

Dua fitur baru dibuat untuk mengukur efisiensi penggunaan energi.

### 1. Energy Intensity per GDP

Mengukur jumlah energi yang digunakan untuk menghasilkan satu unit output ekonomi.

```text
Energy Intensity = Total Energy Consumption / GDP
```

### 2. Renewable Energy Intensity per GDP

Mengukur kontribusi energi terbarukan terhadap aktivitas ekonomi.

```text
Renewable Energy Intensity = Renewable Energy Supply / GDP
```

---

## Exploratory Data Analysis (EDA)

Analisis data menunjukkan bahwa:

* Sektor transportasi dan jasa merupakan kontributor utama emisi.
* Peningkatan penggunaan energi terbarukan cenderung berkaitan dengan penurunan emisi.
* China memiliki total emisi GHG tertinggi.
* Indonesia memiliki emisi relatif rendah namun pemanfaatan energi terbarukan masih terbatas.
* Jerman menunjukkan performa terbaik dalam integrasi energi terbarukan dan efisiensi energi.

---

## Machine Learning

### Model yang Digunakan

#### Linear Regression

Digunakan sebagai model baseline untuk memahami hubungan linier antar variabel.

#### Ridge Regression

Digunakan untuk mengurangi overfitting melalui regularisasi L2.

#### Lasso Regression

Digunakan untuk regularisasi sekaligus seleksi fitur.

#### Random Forest Regression

Model ensemble berbasis Decision Tree yang mampu menangkap hubungan nonlinier dan interaksi antar fitur.

---

## Hyperparameter Tuning

Optimasi model dilakukan menggunakan Grid Search untuk memperoleh kombinasi parameter terbaik pada Random Forest Regression.

---

## Hasil Evaluasi Model

| Model                    | MAPE      |
| ------------------------ | --------- |
| Linear Regression        | 40.80%    |
| Ridge Regression         | 40.84%    |
| Lasso Regression         | 41.04%    |
| Random Forest Regression | **6.60%** |

### Model Terbaik

🏆 **Random Forest Regression**

Dengan nilai **MAPE sebesar 6.60%**, model ini memberikan performa terbaik dibandingkan model regresi lainnya.

---

## Feature Importance

Hasil interpretasi model menunjukkan bahwa variabel yang paling berpengaruh terhadap emisi GHG adalah:

1. Renewable Energy Supply
2. Energy Consumption Industry
3. Energy Consumption Transportation and Storage

Temuan ini menunjukkan bahwa peningkatan penggunaan energi terbarukan memiliki peran penting dalam pengurangan emisi.

---

## Forecasting Emisi GHG

Selain regresi, proyek ini menggunakan **Facebook Prophet** untuk memprediksi tren emisi Gas Rumah Kaca Indonesia pada masa mendatang.

### Hasil Forecasting

| Metric | Nilai  |
| ------ | ------ |
| MAE    | 11.26  |
| MSE    | 162.74 |
| RMSE   | 12.76  |
| MAPE   | 2.21%  |

### Temuan Forecasting

Hasil forecasting menunjukkan bahwa emisi Gas Rumah Kaca Indonesia masih memiliki kecenderungan meningkat pada periode mendatang apabila tidak diimbangi dengan peningkatan penggunaan energi terbarukan dan kebijakan pengurangan emisi.

---

## Dashboard Visualisasi

Proyek ini juga menghasilkan dashboard interaktif yang menampilkan:

* Perbandingan emisi GHG antar negara.
* Hubungan GDP per Capita dan emisi.
* Tren energi terbarukan.
* Hubungan energi terbarukan dan emisi.
* Potensi Energi Baru Terbarukan (EBT) Indonesia.
* Insight dan rekomendasi kebijakan.

---

## Insight Utama

### Jerman Menjadi Benchmark Terbaik

Jerman menunjukkan:

* Energy Intensity rendah.
* Renewable Energy Intensity tinggi.
* Emisi relatif rendah.
* Pertumbuhan ekonomi tetap meningkat.

### Hubungan Renewable Energy dan Emisi

Analisis menunjukkan pola yang konsisten:

* Peningkatan energi terbarukan diikuti penurunan emisi.
* Negara dengan investasi energi terbarukan yang tinggi memiliki tren emisi yang lebih terkendali.

### Indonesia

Indonesia masih berada pada tahap transisi menuju energi terbarukan dan memiliki peluang besar untuk meningkatkan efisiensi energi melalui pengembangan EBT dan pengurangan ketergantungan pada energi fosil.

---

## Rekomendasi

Berdasarkan hasil penelitian, beberapa strategi yang dapat diterapkan Indonesia antara lain:

1. Optimalisasi potensi energi terbarukan daerah.
2. Pengembangan infrastruktur energi hijau.
3. Peningkatan kapasitas SDM sektor energi.
4. Pengurangan ketergantungan pada energi fosil.
5. Adopsi praktik efisiensi energi seperti yang diterapkan Jerman.

---

## Teknologi yang Digunakan

### Data Analysis

* Python
* Pandas
* NumPy

### Data Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-Learn
* Linear Regression
* Ridge Regression
* Lasso Regression
* Random Forest Regression

### Time Series Forecasting

* Prophet

### Business Intelligence

* Tableau

### Development Environment

* Jupyter Notebook

---

## Struktur Repository

```text
.
├── Project akhir msib.ipynb
├── Tim 3B - Dashboard HD.pdf
├── Tim 3B - Deck.pdf
├── dataset/
├── images/
└── README.md
```

---

## Tim TerraBytes

* Naufal Kholif Nashuha
* Arnetta Dea Suryanti
* Mohammad Rohmad Nur Khoirofiq
* Havinka Angel Salsabilla
* Muhammad Bayu Nugroho
* Wianda Puspa Putri Utami

---
Universitas Sriwijaya
