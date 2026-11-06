# Crunchyroll Review Rating Prediction (Text Mining)

Proyek text mining untuk memprediksi rating (1-5) dari review aplikasi **Crunchyroll** di Google Play Store, dengan membandingkan dua metode representasi teks dan dua algoritma machine learning.

## Latar Belakang

Banyak aplikasi streaming film dan anime di Play Store, sehingga pengguna sulit memilih aplikasi yang layak diunduh. Proyek ini memanfaatkan review pengguna untuk membangun model yang memprediksi rating dari teks review.

## Dataset

- Sumber: scraping review Play Store dengan `google-play-scraper`
- Aplikasi: Crunchyroll
- Bahasa: Inggris
- Jumlah: 1000 review dengan berbagai nilai rating
- Kolom: `content` (teks review), `score` (rating), `at` (waktu review)

## Tahapan

1. **Scraping data**: pengambilan 1000 review berbahasa Inggris
2. **Exploratory data analysis**: kata dominan per rating, pemeriksaan kata non-baku
3. **Preprocessing**: pembersihan teks, tokenisasi, normalisasi, dan lemmatization
4. **Text representation**:
   - TF-IDF (bobot pentingnya kata dalam dokumen)
   - Word2Vec (vektor berdasarkan konteks kata di sekitarnya)
5. **Modeling**: dua algoritma ML dengan hyperparameter tuning (minimal 2 hyperparameter per algoritma)
6. **Evaluasi**: perbandingan performa antar kombinasi representasi dan algoritma
7. **Penanganan imbalance**: treatment pada data tidak seimbang, training ulang, dan perbandingan hasil
8. **Kesimpulan**: model terbaik dan analisisnya

## Hasil

### Hasil Hyperparameter Terbaik

| Treatment | Text Representation | Algoritma | Hyperparameter Terbaik | Accuracy | Precision (macro) | Recall (macro) | F1 (macro) |
|---|---|---|---|---|---|---|---|
| Tanpa SMOTE | TF-IDF | Logistic Regression | `C=10`, `solver=liblinear` | 0.603 | 0.394 | 0.362 | 0.358 |
| Tanpa SMOTE | TF-IDF | Random Forest | `max_depth=None`, `n_estimators=300` | 0.608 | 0.312 | 0.330 | 0.295 |
| Tanpa SMOTE | Word2Vec | Logistic Regression | `C=10`, `solver=lbfgs` | 0.653 | 0.462 | 0.355 | 0.317 |
| Tanpa SMOTE | Word2Vec | Random Forest | `max_depth=None`, `n_estimators=300` | 0.658 | 0.371 | 0.358 | 0.322 |
| SMOTE | TF-IDF | Logistic Regression | `C=0.1`, `solver=liblinear` | 0.497 | 0.392 | 0.381 | 0.377 |
| SMOTE | TF-IDF | Random Forest | `max_depth=None`, `n_estimators=(isi)` | 0.618 | 0.518 | 0.423 | 0.442 |
| SMOTE | Word2Vec | Logistic Regression | `C=10`, `solver=liblinear` | 0.503 | 0.414 | 0.415 | 0.393 |
| SMOTE | Word2Vec | Random Forest | `max_depth=20`, `n_estimators=100` | 0.573 | 0.400 | 0.394 | 0.395 |


## Cara Menjalankan

1. Buka notebook di Google Colab atau Jupyter.
2. Install dependensi:
   ```
   pip install google-play-scraper pandas scikit-learn nltk gensim matplotlib
   ```
3. Jalankan sel notebook secara berurutan.

## Tools

Python, pandas, scikit-learn, NLTK, Gensim, Matplotlib, google-play-scraper

## Catatan

Dikerjakan sebagai bagian dari mata kuliah Text Mining (BINUS University).
