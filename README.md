# ImageClassification-SVM
Repositori ini berisi implementasi sistem klasifikasi gambar anemia menggunakan algoritma Support Vector Machine (SVM).

# Klasifikasi Gambar Anemia Menggunakan SVM

## Deskripsi Proyek
Proyek ini mengimplementasikan klasifikasi gambar untuk mendeteksi anemia dari gambar mikroskopik sel darah menggunakan Support Vector Machine (LinearSVC). Model berhasil mencapai akurasi 90.42% dengan sensitivitas 93% untuk kasus anemia.

## Dataset
Dataset terdiri dari 4277 gambar (2563 anemic dan 1714 non-anemic) dalam format PNG dengan berbagai ukuran. Karakteristik utama dataset adalah perbedaan distribusi warna antara gambar anemic dan non-anemic.

### Statistik Dataset
- **Rasio Kelas**: 60% anemic : 40% non-anemic
- **Dimensi Gambar**: Bervariasi, anemic (min: 87x87, max: 462x462), non-anemic (min: 49x49, max: 499x499)
- **Ukuran File**: anemic (mean: 28.20 KB), non-anemic (mean: 18.60 KB)

## Metodologi
1. **Preprocessing**: Standardisasi ukuran (64x64), normalisasi nilai piksel
2. **Ekstraksi Fitur**: Pendekatan flatten sederhana (64×64×3 = 12288 dimensi)
3. **Model**: LinearSVC dengan C=1.0, dual=False, max_iter=1000
4. **Kalibrasi**: CalibratedClassifierCV untuk mendapatkan probabilitas prediksi

## Hasil Utama
- **Accuracy**: 90.42%
- **Precision**: Non-anemic (0.89), Anemic (0.91)
- **Recall**: Non-anemic (0.87), Anemic (0.93)
- **F1-score**: Non-anemic (0.88), Anemic (0.92)

## Insight Utama
1. Model menunjukkan performa yang seimbang antara kedua kelas, dengan sedikit bias positif terhadap kelas anemic
2. False negatives (36) lebih sedikit daripada false positives (46), yang ideal dalam konteks medis
3. Pendekatan ekstraksi fitur sederhana terbukti efektif, menunjukkan perbedaan visual yang jelas antara kelas
