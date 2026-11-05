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

_Akan diisi setelah analisis selesai._

| Text Representation | Algoritma | Hyperparameter | Metrik 1 | Metrik 2 | Metrik 3 | Metrik 4 |
|---|---|---|---|---|---|---|
| TBD | TBD | TBD | TBD | TBD | TBD | TBD |

## Struktur Repositori

```
├── data/
│   └── reviews.csv
├── notebooks/
│   └── text_mining.ipynb
├── README.md
└── .gitignore
```

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

Dikerjakan sebagai bagian dari mata kuliah Text Mining (BINUS University). Penggunaan AI dalam proses pengerjaan dideklarasikan sesuai ketentuan mata kuliah.
