# Deteksi Phishing Menggunakan Machine Learning

## Judul Penelitian

Evaluasi Pengaruh Fitur URL-Only dan Validasi Berbasis Domain terhadap Deteksi Phishing Menggunakan Machine Learning

## Deskripsi

Penelitian ini bertujuan mengevaluasi pengaruh penggunaan fitur URL-Only dan strategi pembagian data berbasis domain terhadap performa model Machine Learning dalam mendeteksi URL phishing.

Algoritma yang digunakan:
- Logistic Regression
- Random Forest

Dataset yang digunakan adalah PhiUSIIL Phishing URL Dataset.

## Dataset

Sumber:
https://www.kaggle.com/datasets/kaggleprollc/phishing-url-websites-dataset-phiusiil

Karakteristik dataset awal:
- Jumlah sampel: 235.795
- Jumlah kolom: 56
- Kelas phishing: 100.945
- Kelas legitimate: 134.850

Setelah penghapusan URL duplikat:
- Jumlah sampel: 235.370

Dataset tidak disertakan secara langsung dalam repository.

## Struktur Proyek

```text
TTKI-Phishing-Detection/
├── data/
├── notebooks/
│   ├── 01_Data_Audit.ipynb
│   ├── 02_EDA.ipynb
│   ├── 03_Data_Preprocessing.ipynb
│   └── 04_Baseline_Model.ipynb
├── results/
├── figures/
├── logs/
├── references/
├── requirements.txt
└── environment-freeze.txt
```

## Environment

Penelitian menggunakan Python dan Jupyter Notebook melalui Visual Studio Code.

Instalasi dependencies:

```bash
pip install -r requirements.txt
```

## Tahapan Penelitian

1. Data Auditing
2. Exploratory Data Analysis
3. Data Preprocessing
4. Baseline Model
5. Eksperimen URL-Only Features
6. Eksperimen Domain-Aware Validation
7. Evaluasi dan Analisis Hasil

## Baseline Model

Skenario A:
- Feature Type: Full Features
- Validation: Stratified Random Split
- Split Ratio: 70:30
- Random State: 42

### Hasil Baseline

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---|---|---|---|---|
| Logistic Regression | 99.9278% | 99.9768% | 99.8541% | 99.9154% | 0.999964 |
| Random Forest | 99.9830% | 99.9867% | 99.9735% | 99.9801% | 0.999998 |

Random Forest menghasilkan performa klasifikasi tertinggi pada pengujian baseline.

Hasil ini merupakan baseline penelitian yang telah diadaptasi dan belum dinyatakan sebagai reproduksi identik dari GitHub referensi.

## Rencana Eksperimen

| Skenario | Fitur | Pembagian Data |
|---|---|---|
| A | Full Features | Random Split |
| B | URL-Only | Random Split |
| C | URL-Only | Domain-Grouped Split |
| D | Full Features | Domain-Grouped Split |

## Reproduksi Eksperimen

1. Unduh dataset dari Kaggle.
2. Simpan dataset dengan nama `PhiUSIIL_Phishing_URL_Dataset.csv` pada folder `data/`.
3. Instal dependencies menggunakan `requirements.txt`.
4. Jalankan notebook secara berurutan dari `01_Data_Audit.ipynb` sampai `04_Baseline_Model.ipynb`.
5. Periksa hasil evaluasi pada folder `results/` dan visualisasi pada folder `figures/`.

## Referensi Baseline

https://github.com/pradhyumnaag30/PhiUSIIL-Phishing-URL-Detection

## Catatan

Penelitian masih dalam tahap pengembangan.

Hasil baseline diperoleh dari eksperimen menggunakan dataset PhiUSIIL dengan stratified random split.

Eksperimen selanjutnya akan mengevaluasi pengaruh penggunaan fitur URL-only dan domain-aware validation.