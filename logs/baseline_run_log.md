
# Baseline Run Log

## 1. Informasi Penelitian

**Judul:**
Evaluasi Pengaruh Fitur URL-Only dan Validasi Berbasis Domain terhadap Deteksi Phishing Menggunakan Machine Learning

**Dataset:** PhiUSIIL Phishing URL Dataset

**Skenario:** A — Full Features + Random Split

**Tanggal pencatatan:** 2026-11-21 16:23:19

## 2. Environment

- Operating System: Windows-10-10.0.26200-SP0
- Python Version: 3.11.15
- Pandas Version: 3.1.1
- NumPy Version: 2.4.6
- Scikit-learn Version: 1.9.1

## 3. Konfigurasi Eksperimen

- Dataset awal: 235.795 sampel
- Dataset setelah menghapus URL duplikat: 235.370 sampel
- Full Features: 47 fitur
- Training: 70%
- Testing: 30%
- Random State: 42
- Positive Class: Phishing

## 4. Konfigurasi Model

### Logistic Regression
- StandardScaler
- max_iter = 1000
- random_state = 42

### Random Forest
- n_estimators = 100
- random_state = 42
- n_jobs = -1

## 5. Hasil Eksperimen


### Logistic Regression

- Accuracy: 0.999278
- Precision: 0.999768
- Recall: 0.998541
- F1-Score: 0.999154
- ROC-AUC: 0.999964
- Training Time: 0.390694 detik
- Inference Time: 0.022785 detik
- True Negative: 40448
- False Positive: 7
- False Negative: 44
- True Positive: 30112


### Random Forest

- Accuracy: 0.999830
- Precision: 0.999867
- Recall: 0.999735
- F1-Score: 0.999801
- ROC-AUC: 0.999998
- Training Time: 4.184473 detik
- Inference Time: 0.084865 detik
- True Negative: 40451
- False Positive: 4
- False Negative: 8
- True Positive: 30148


## 6. Kesimpulan

Berdasarkan hasil eksperimen baseline, Random Forest
menghasilkan performa klasifikasi yang lebih tinggi
dibandingkan Logistic Regression.

Namun, Logistic Regression memiliki waktu pelatihan
dan inferensi yang lebih rendah.

Performa kedua model masih perlu dievaluasi menggunakan
URL-only features dan domain-grouped split.

## 7. Catatan Metodologis

- Dataset menggunakan PhiUSIIL dari Kaggle.
- URL duplikat dihapus sebelum pembagian data.
- Fitur yang berpotensi menyebabkan data leakage dikecualikan.
- Pembagian data menggunakan stratified random split.
- Eksperimen ini merupakan baseline penelitian yang telah
  diadaptasi, bukan reproduksi identik GitHub referensi.
