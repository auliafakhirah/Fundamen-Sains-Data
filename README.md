# Fundamen-Sains-Data
# Tugas Dimensionality Reduction - PCA dan t-SNE

📋 Identitas
- **Mata Kuliah**: Fundamen Sains Data
- **Kelompok**: brazil
- **Anggota**:
  1. Aulia Fakhirah Hendraini - 24523020
  2. Maulidya Iftitah - 24523236
 

📝 Deskripsi Kasus
Proyek ini mengimplementasikan teknik **dimensionality reduction** menggunakan **PCA** dan **t-SNE** pada **Dataset Wine** untuk melakukan eksplorasi cluster dan visualisasi data berdimensi tinggi.

Masalah yang Dihadapi
Dataset Wine memiliki 13 fitur kimiawi, sehingga sulit untuk:
- Memvisualisasikan data secara langsung
- Mengidentifikasi pola alami dalam data
- Melihat apakah ada pengelompokan berdasarkan jenis wine

Mengapa Dimensionality Reduction Dibutuhkan?
- Mengurangi dimensi data dari 13 menjadi 2-3 dimensi
- Memudahkan visualisasi dan interpretasi
- Membantu mengidentifikasi cluster alami
- Dapat digunakan sebagai preprocessing untuk modeling

📊 Dataset
- **Nama**: Wine Dataset (dari scikit-learn)
- **Jumlah Sampel**: 178
- **Jumlah Fitur**: 13 (alkohol, asam malat, abu, dll.)
- **Jumlah Kelas**: 3 (Class 0, 1, 2)
- **Link Dataset**: [Scikit-learn Wine Dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_wine.html)
- 
Fitur-fitur Dataset:
1. Alcohol
2. Malic acid
3. Ash
4. Alcalinity of ash
5. Magnesium
6. Total phenols
7. Flavanoids
8. Nonflavanoid phenols
9. Proanthocyanins
10. Color intensity
11. Hue
12. OD280/OD315 of diluted wines
13. Proline

🔬 Metode yang Digunakan

### 1. PCA (Principal Component Analysis)
- **Tujuan**: Reduksi dimensi secara linear
- **Parameter**: n_components=2 dan 3
- **Kelebihan**: Interpretable, cepat, mempertahankan varians
- **Kekurangan**: Linear, tidak menangkap struktur non-linear

2. t-SNE (t-Distributed Stochastic Neighbor Embedding)
- **Tujuan**: Reduksi dimensi secara non-linear
- **Parameter**: n_components=2, perplexity=30
- **Kelebihan**: Mempertahankan struktur lokal, cluster jelas
- **Kekurangan**: Lambat, stochastic, sulit diinterpretasi


📈 Hasil dan Analisis

 Visualisasi PCA (2D)
![PCA 2D](images/pca_2d.png)

**Analisis**:
- Total variance yang dijelaskan oleh 2 komponen: **~55.5%**
- PC1 menjelaskan ~36.2% variance
- PC2 menjelaskan ~19.3% variance
- Kelas 0 terpisah dengan jelas dari kelas 1 dan 2
- Kelas 1 dan 2 masih mengalami overlap
- PCA cukup baik tetapi masih kehilangan informasi

Visualisasi PCA (3D)
![PCA 3D](images/pca_3d.png)

**Analisis**:
- Total variance yang dijelaskan oleh 3 komponen: **~66.5%**
- Penambahan dimensi ke-3 membantu pemisahan
- Kelas 1 dan 2 mulai terpisah lebih baik

 Visualisasi t-SNE
![t-SNE 2D](images/tsne_2d.png)

**Analisis**:
- Pemisahan cluster sangat jelas
- Semua 3 kelas terpisah dengan baik
- Cluster lebih kompak dibanding PCA
- t-SNE berhasil menangkap struktur non-linear data

 Perbandingan PCA vs t-SNE
![Perbandingan](images/comparison.png)

**Perbedaan**:
| Aspek | PCA | t-SNE |
|-------|-----|-------|
| Linearitas | Linear | Non-linear |
| Kecepatan | Cepat | Lambat |
| Reproducibility | Deterministik | Stochastic |
| Interpretasi | Komponen bermakna | Dimensi abstrak |
| Kualitas Cluster | Baik | Sangat Baik |

### Efek Perplexity pada t-SNE
![Efek Perplexity](images/perplexity_experiment.png)

**Analisis**:
- Perplexity kecil (5): cluster terlalu fragmentasi
- Perplexity optimal (30): cluster jelas dan seimbang
- Perplexity besar (50-100): cluster mulai menyatu

---

💡 Kesimpulan

1. **Untuk kasus eksplorasi cluster pada dataset Wine, t-SNE lebih sesuai** karena:
   - Menunjukkan pemisahan cluster yang lebih jelas
   - Mampu menangkap struktur non-linear data
   - Memperlihatkan 3 cluster yang terpisah sempurna

2. **PCA tetap berguna untuk**:
   - Interpretasi fitur (mengetahui kontribusi tiap fitur)
   - Data dengan struktur linear
   - Preprocessing sebelum modeling (karena cepat)

3. **Rekomendasi**:
   - Gunakan t-SNE untuk visualisasi dan eksplorasi
   - Gunakan PCA untuk interpretasi dan preprocessing
   - Kombinasikan kedua metode untuk analisis yang komprehensif

## 🚀 Cara Menjalankan

1. Clone repository:
   ```bash
   git clone https://github.com/[username]/dimensionality-reduction-tugas.git
