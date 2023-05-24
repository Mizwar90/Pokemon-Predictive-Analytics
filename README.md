# Pokemon-Predictive-Analytics

# Clustering Pokemon Dataset - Mizwar

## Domain Proyek

Pada proyek kali ini, saya akan melakukan metode Unsupervised Learning dengan algoritma Clustering pada data Pokemon milik akun https://gist.github.com/armgilles/194bcff35001e7eb53a2a8b441e8b2c6#file-pokemon-csv . Dataset pokemon, saya download kemudian mengupload kembali ke akun github saya sendiri untuk selanjutnya load dataset melalui link github tersebut.

Game Pokemon adalah salah satu game populer di dunia saat ini, salah satu game populer adalah 'Pokemon Go'. Ini merupakan game berbasis augmented-reality yang dikembangkan oleh Pokemon Company bekerja sama dengan Nintendo dan Niantic *.

**Rubrik/Kriteria Tambahan**:

Masalah yang ingin saya teliti adalah terkait 'Hero' pada Pokemon, saya ingin melihat cluster/pengelompokan 'Attack' dan 'Defence' pada 'Hero' dataset Pokemon.

*Artikel ini telah tayang di Kompas.com dengan judul "Apa Itu Pokemon Go?", Klik untuk baca: https://tekno.kompas.com/read/2016/07/09/13200047/apa.itu.pokemon.go.?page=all. Penulis : Deliusno


## Business Understanding

### Problem Statements
- Melihat karakteristik 'Attack' dan 'Defence' yang dimiliki oleh 'Hero' Pokemon.

### Goals
- Dapat melakukan cluster/pengelompokan data 'Attack' dan 'Defence', pada 'Hero' Pokemon.

**Rubrik/Kriteria Tambahan**:
- “Solution Statement” untuk meraih goals: 

    ### Solution statements
    - Clustering menggunakan K-Means dan penentuan jumlah cluster menggunakan metode Elbow.
    - Metrik menggunakan Silhouette Score

## Data Understanding
Pada proyek kali ini, saya mengambil data Pokemon milik akun (https://gist.github.com/armgilles/194bcff35001e7eb53a2a8b441e8b2c6#file-pokemon-csv).

### Variabel-variabel pada Pokemon dataset adalah sebagai berikut:
- Name: Nama hero Pokeomon
- Attack: Serangan pokemon yang akan merusak hero lain (dalam angka).
- Defence: Seberapa besar kerusakan yang ditahan hero pokemon (dalam angka).

## Data Preparation
Teknik preparation:
- Data Loading
- Exploratory Data Analysis - Deskripsi Variabel
- Membuat salinan dataframe dengan dua kolom yaitu attack dan defense
- Melakukan transformasi pada data
- Cek nilai pencilan/outlier
- Menangani Missing Value
- Membuat fungsi untuk menangani outlier dengan teknik IQR method
- Menangani Missing Value dengan fungsi dropna
- Cek nilai pencilan/outlier kembali
- Data Scaling/normalisasi Data

## Modeling
- Clustering menggunakan K-Means, dengan memilih jumlah cluster secara manual mulai dari 2, 3 dan 4.
- Membuat fungsi Metode Elbow untuk menentukan optimalisasi jumlah cluster berdasarkan metode Elbow.
- Menggunakan metrik Silhouette Score, skor silhouette dalam algoritma pengelompokan K-Means adalah antara -1 dan 1. Skor ini menunjukkan seberapa baik titik data telah dikelompokkan, dan skor di atas 0 dianggap baik, sedangkan poin negatif berarti algoritme K-means Anda telah menempatkannya di titik data cluster yang salah).

## Evaluation
Kasus pada proyek kali ini menggunakan clustering/pengelompokan, sehingga menggunakan metrik Silhouette Score. Skor silhouette dalam algoritma pengelompokan K-Means adalah antara -1 dan 1. Skor ini menunjukkan seberapa baik titik data telah dikelompokkan, dan skor di atas 0 dianggap baik, sedangkan poin negatif berarti algoritme K-means Anda telah menempatkannya di titik data cluster yang salah.

Berdasarkan metrik silhouette score, nilai paling besar mendekati 1 adalah 0.5967848800416774, yaitu cluster yang berjumlah 4 yang menggunakan algoritma K-Means.


**---Ini adalah bagian akhir laporan---**

Dari hasil klustering diatas, kita dapat mengambil kesimpulan sebagai berikut:

- Berdasarkan Elbow Method kita dapat mengambil jumlah cluster optimal sebesar 2 cluster karna lebih mencerminkan segmentasi kelompok data defence dan attack secara keseluruhan jika kita mengeneralisasi data.
- Berdasarkan metrik silhouette score, yang mendekati nilai 1 adalah cluster yang berjumlah 4 yang menggunakan algoritma K-Means.

Kesimpulan: Kedua metode diatas bisa digunakan salah satu atau keduanya tergantung permasalahan apa yang ingin dipecahkan. Disini saya ingin menjabarkan hasil yang didapatkan clustering (pengelompokan) algoritma K-Means yang memiliki jumlah cluster 4. Sekilas dapat kita lihat visualisasi, jika semakin kecil attack maka semakin kecil pula defence dan semakin besar attack maka semakin besar pula defence. Hanya sebagian kecil cluster 3 (color = yellow) defence tinggi namun attack berada di tengah, begitu pula cluster 2 (color = blue) attack tinggi namun defence berada di tengah. Secara keseluruhan, dapat disimpulkan 'Attack' dan 'Defence' pada 'Hero' dataset pokemon berbanding lurus jika dilihat dari pengelompokan yang ada.
