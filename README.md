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
- Name: nama hero Pokeomon
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
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

Kasus pada proyek kali ini menggunakan clustering/pengelompokan, sehingga menggunakan metrik Silhouette Score. Skor silhouette dalam algoritma pengelompokan K-Means adalah antara -1 dan 1. Skor ini menunjukkan seberapa baik titik data telah dikelompokkan, dan skor di atas 0 dianggap baik, sedangkan poin negatif berarti algoritme K-means Anda telah menempatkannya di titik data cluster yang salah.

Berdasarkan metrik silhouette score, nilai paling besar mendekati 1 adalah 0.5967848800416774, yaitu cluster yang berjumlah 4 yang menggunakan algoritma K-Means.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
