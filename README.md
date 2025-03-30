# Laporan Proyek Machine Learning - Ridho Nur Fauzi

## Domain Proyek

Penyakit jantung merupakan salah satu penyebab utama kematian di seluruh dunia. Deteksi dini penyakit jantung sangat penting untuk mencegah komplikasi serius dan meningkatkan harapan hidup pasien. Dengan kemajuan teknologi, **machine learning** dapat digunakan untuk **memprediksi kemungkinan seseorang mengalami penyakit jantung** berdasarkan data medis.

Referensi:
- [World Health Organization: Cardiovascular Diseases (CVDs)](https://www.who.int/news-room/fact-sheets/detail/cardiovascular-diseases-(cvds))
- [Heart Disease Prediction Using Machine Learning](https://ieeexplore.ieee.org/document/9091690)

## Business Understanding

### Problem Statements

- Bagaimana cara memprediksi kemungkinan seseorang mengalami penyakit jantung berdasarkan parameter medis?
- Model machine learning apa yang memberikan prediksi terbaik untuk penyakit jantung?
- Fitur medis mana yang memiliki pengaruh paling besar terhadap risiko penyakit jantung?

### Goals

- Mengembangkan model machine learning untuk memprediksi penyakit jantung berdasarkan dataset yang tersedia.
- Membandingkan berbagai model machine learning seperti **K-Nearest Neighbors (KNN), Support Vector Machine (SVM), Decision Tree, Random Forest, dan Neural Network**.

### Solution Statements

- Menggunakan beberapa model machine learning untuk mendapatkan prediksi terbaik.

## Data Understanding

Dataset yang digunakan berasal dari Kaggle:  
🔗 **[Heart Disease Dataset](https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset)**  

Dataset ini memiliki  **14 fitur** yang menjelaskan kondisi kesehatan pasien.

### Variabel-variabel dalam dataset:

| No | Fitur | Deskripsi |
|----|-------|-----------|
| 1 | `age` | Umur pasien |
| 2 | `sex` | Jenis kelamin (0 = perempuan, 1 = laki-laki) |
| 3 | `cp` | Tipe nyeri dada (4 kategori) |
| 4 | `trestbps` | Tekanan darah istirahat (mm Hg) |
| 5 | `chol` | Kadar kolesterol serum (mg/dl) |
| 6 | `fbs` | Gula darah puasa (> 120 mg/dl = 1, jika tidak = 0) |
| 7 | `restecg` | Hasil elektrokardiografi istirahat (0,1,2) |
| 8 | `thalach` | Detak jantung maksimum yang dicapai |
| 9 | `exang` | Angina akibat olahraga (1 = ya, 0 = tidak) |
| 10 | `oldpeak` | Depresi ST akibat olahraga dibandingkan istirahat |
| 11 | `slope` | Kemiringan segmen ST puncak latihan |
| 12 | `ca` | Jumlah pembuluh utama (0-3) yang terdeteksi oleh fluoroskopi |
| 13 | `thal` | 0 = normal, 1 = fixed defect, 2 = reversible defect |
| 14 | `target` | 1 = memiliki penyakit jantung, 0 = tidak memiliki penyakit jantung |

Visualisasi data menggunakan **histogram, boxplot, dan heatmap korelasi** akan dilakukan untuk memahami distribusi dan hubungan antar fitur.

## Data Preparation


### Heatmap Korelasi
Untuk melihat hubungan antar fitur:

![Heatmap Korelasi](img/heatmap.png)

---


Langkah-langkah yang dilakukan dalam data preparation:
1. **Menghapus data yang hilang (missing values)**.
2. **Melakukan normalisasi fitur numerik** agar memiliki skala yang seragam.
3. **Memvisualisasikan Data**
3. **Membagi dataset menjadi training set dan testing set** (misalnya 80% training dan 20% testing).
4. **Menyeimbangkan dataset jika ada ketidakseimbangan kelas**
5. **Membandingkan Hasil setiap Algoritma** untuk menemukan model terbaik

## Modeling

### Perbandingan Akurasi Model
Grafik berikut menunjukkan hasil evaluasi berbagai model:

![Perbandingan Model](path/to/model_comparison.png)

---

Model yang akan digunakan dalam proyek ini:
1. **K-Nearest Neighbors (KNN)**  
   - Kelebihan: Sederhana dan mudah dipahami  
   - Kekurangan: Sensitif terhadap skala data dan memerlukan tuning `k` yang optimal  

2. **Support Vector Machine (SVM)**  
   - Kelebihan: Cocok untuk dataset kecil dan kompleks  
   - Kekurangan: Waktu komputasi tinggi jika jumlah data besar  

3. **Decision Tree**  
   - Kelebihan: Interpretasi mudah dan tidak memerlukan normalisasi data  
   - Kekurangan: Rentan terhadap overfitting  

4. **Random Forest**  
   - Kelebihan: Lebih stabil daripada Decision Tree dan dapat menangani missing values  
   - Kekurangan: Memerlukan lebih banyak waktu untuk training  

5. **Neural Network**  
   - Kelebihan: Dapat menangkap hubungan kompleks antar fitur  
   - Kekurangan: Memerlukan banyak data dan tuning hyperparameter  

## Evaluation

Metrik evaluasi yang digunakan dalam proyek ini adalah:
- **Akurasi**: Proporsi prediksi yang benar dari total prediksi.
- **Precision**: Seberapa akurat model dalam memprediksi kasus positif.
- **Recall**: Seberapa baik model dalam menangkap semua kasus positif.
- **F1-score**: Rata-rata harmonik dari precision dan recall.

Formula perhitungan metrik evaluasi:

- **Precision** = TP / (TP + FP)  
- **Recall** = TP / (TP + FN)  
- **F1-score** = 2 * (Precision * Recall) / (Precision + Recall)  

Hasil evaluasi akan dibandingkan untuk menentukan model terbaik dalam memprediksi penyakit jantung.

---
