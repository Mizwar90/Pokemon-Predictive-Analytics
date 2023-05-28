# Pokemon-Predictive-Analytics

# Clustering Pokemon Dataset - Mizwar

## Domain Proyek

Pada proyek kali ini, saya akan melakukan metode *Unsupervised Learning* dengan algoritma *Clustering* pada data Pokemon milik akun https://gist.github.com/armgilles/194bcff35001e7eb53a2a8b441e8b2c6#file-pokemon-csv . Dataset pokemon, saya download kemudian mengupload kembali ke akun github saya sendiri untuk selanjutnya load dataset melalui link github tersebut.

*Game* Pokemon adalah salah satu game populer di dunia saat ini, salah satu *game* populer adalah 'Pokemon Go'. Ini merupakan *game* berbasis *augmented-reality* yang dikembangkan oleh Pokemon Company bekerja sama dengan Nintendo dan Niantic.

Metode *Unsupervised Learning* adalah salah satu jenis pendekatan dalam pembelajaran mesin di mana algoritma belajar dari data yang tidak memiliki label atau informasi yang telah ditentukan sebelumnya. Dalam metode ini, algoritma ditugaskan untuk menemukan pola atau struktur tersembunyi dalam data secara mandiri.

Salah satu algoritma yang umum digunakan dalam metode *Unsupervised Learning* adalah algoritma *Clustering*. *Clustering* adalah proses pengelompokan objek atau data ke dalam kelompok-kelompok atau "klaster" yang memiliki kesamaan dalam beberapa aspek tertentu. Tujuan utama dari algoritma *Clustering* adalah mengelompokkan data berdasarkan kesamaan dan membuat kelompok yang homogen di dalam kelompok tersebut, sementara menghasilkan perbedaan yang signifikan antara kelompok-kelompok tersebut.

**Rubrik/Kriteria Tambahan**:

Masalah yang ingin saya teliti adalah terkait 'Hero' pada Pokemon, saya ingin melihat cluster/pengelompokan 'Attack' dan 'Defence' pada 'Hero' dataset Pokemon.


## Business Understanding

### Problem Statements
- Bagaimana mengidentifikasi setidaknya dua kelompok utama berdasarkan 'Attack' dan 'Defence' dengan tingkat keakuratan tertentu?
- Apakah terdapat kelompok Pokemon dengan 'Attack' dan 'Defence' yang sangat tinggi yang dapat dianggap sebagai 'Hero' Pokemon?

### Goals
- Dapat mengidentifikasi setidaknya dua kelompok utama berdasarkan 'Attack' dan 'Defence' dengan tingkat keakuratan tertentu.
- Dapat mengetahui kelompok Pokemon dengan 'Attack' dan 'Defence' yang sangat tinggi yang dapat dianggap sebagai 'Hero' Pokemon.

**Rubrik/Kriteria Tambahan**:
- “Solution Statement” untuk meraih goals: 

    ### Solution statements
    - Clustering menggunakan K-Means dan Hierarchical Clustering serta penentuan jumlah cluster menggunakan metode Elbow.
    - Metrik menggunakan Silhouette Score dan Inertia.

## Data Understanding
Pada proyek kali ini, saya mengambil data Pokemon milik akun (https://gist.github.com/armgilles/194bcff35001e7eb53a2a8b441e8b2c6#file-pokemon-csv).

### Variabel-variabel pada Pokemon dataset adalah sebagai berikut:
- Name: Nama hero Pokeomon
- Type 1: Jenis 1 atau kategori Pokemon (dalam obyek)
- Type 2: Jenis 2 atau kategori Pokemon (dalam obyek)
- Total: Jumlah total nilai Pokemon (dalam angka)
- HP: Nilai HP pada Pokémon menggambarkan jumlah kesehatan atau daya tahan Pokémon tersebut dalam pertempuran (dalam angka)
- Attack: kekuatan serangan fisik atau serangan langsung yang dimiliki oleh sebuah Pokémon dalam pertarungan melawan lawan (dalam angka)
- Defence: Kemampuan Pokémon dalam menghadapi dan mengurangi kerusakan yang diterimanya dari serangan fisik atau serangan langsung lawan (dalam angka)
- Sp. Atk: Salah satu dari dua jenis serangan utama dalam permainan Pokémon (dalam angka)
- Sp. Def: Statistik yang mengukur ketahanan Pokémon terhadap serangan khusus dari lawan (dalam angka)
- Speed: Statistik yang menentukan tingkat kecepatan sebuah Pokémon dalam pertempuran (dalam angka)
- Generation: Mengacu pada kelompok Pokémon yang diperkenalkan dalam satu periode waktu tertentu dalam sejarah franchise Pokémon (dalam angka)
- Legendary: Kategori khusus Pokémon yang dianggap langka, kuat, dan memiliki status khusus dalam dunia Pokémon (dalam boolean)

## Data Preparation
Teknik preparation:
- **Data Loading**
- **Exploratory Data Analysis - Deskripsi Variabel**
- **Membuat salinan dataframe dengan dua kolom yaitu attack dan defense**
- **Melakukan transformasi pada data**: Pada tahap ini, kita memeriksa apakah ada missing value pada data. Hasil pemeriksaan tidak ditemukan missing value.
- **Cek nilai pencilan/*outlier***: Pencilan/*Outlier* adalah data atau pengamatan yang tampak menyimpang secara nyata dari pengamatan lain dalam sampel. Biasanya pencilan terletak jauh atau sangat berbeda dari nilai-nilai lain dalam sampel acak dari suatu populasi. Dari gambar dibawah terlihat terdapat pencilan.
![download (1)](https://github.com/Mizwar90/Pokemon-Predictive-Analytics/assets/108685416/acd570a3-ffe3-4ad7-a0f8-2c2340a5b34f)
Gambar 1. Cek nilai pencilan

- Menangani *Missing Value*
- Membuat fungsi untuk menangani *outlier* dengan teknik *IQR method*
- Menangani *Missing Value* dengan fungsi dropna
- Cek nilai pencilan/*outlier* kembali: Setelah menangani pencilan dengan teknik *IQR method* sudah tidak terdapat nilai pencilan, seperti gambar dibawah.
 ![download (2)](https://github.com/Mizwar90/Pokemon-Predictive-Analytics/assets/108685416/1ec70781-a691-4832-a24b-fa03ca4724fe)
 Gambar 2. Cek nilai pencilan setelah menggunakan metode IQR

- ***Data Scaling*/normalisasi Data**: Pada tahap ini menggunakan fungsi StandarScaler dalam normalisasi data.

- ***Clustering* menggunakan K-Means**
 ![download (4)](https://github.com/Mizwar90/Pokemon-Predictive-Analytics/assets/108685416/2566f2dd-3fb9-43f1-b97b-3e02256fdc90)
 Gambar 3. Clustering menggunakan K-Means


- **Metode Elbow** jumlah cluster optimal yang dipilih adalah 3, karena setelah titik tersebut, penurunan inertia tidak signifikan lagi. Seperti pada gambar dibawah.
 ![download (3)](https://github.com/Mizwar90/Pokemon-Predictive-Analytics/assets/108685416/6bc2f43e-2405-44f6-8729-fb930ded1d06)
 Gambar 4. Metode Elbow



## Modeling
- Clustering menggunakan K-Means, dengan memilih jumlah cluster secara manual mulai dari 2, 3 dan 4.
- Membuat fungsi Metode Elbow untuk menentukan optimalisasi jumlah cluster berdasarkan metode Elbow. Jumlah cluster optimal yang dipilih adalah 3, karena setelah titik tersebut, penurunan inertia tidak signifikan lagi. Seperti pada gambar dibawah.
 ![download (3)](https://github.com/Mizwar90/Pokemon-Predictive-Analytics/assets/108685416/6bc2f43e-2405-44f6-8729-fb930ded1d06)
 Gambar 5. Metode Elbow
- ***Clustering* menggunakan K-Means**. Berdasarkan metode Elbow, dipilih jumlah cluster = 3. Visualisasi **cluster** dapat terlihat seperti gambar dibawah. 
 ![download (4)](https://github.com/Mizwar90/Pokemon-Predictive-Analytics/assets/108685416/2566f2dd-3fb9-43f1-b97b-3e02256fdc90)
 Gambar 6. Clustering menggunakan K-Means
 
- ***Clustering* menggunakan Hierarchical Clustering**. Untuk membandingkan cluster dengan metode K-Means didapatkan hasil visualisasi serupa.

![download (5)](https://github.com/Mizwar90/Pokemon-Predictive-Analytics/assets/108685416/8a40b893-88de-49a9-8133-37524d86d65b)

Gambar 7. Clustering menggunakan Hierarchical Clustering

## Evaluation
Dalam konteks clustering Pokemon, nilai Silhouette Score yang tinggi menunjukkan kualitas clustering yang lebih baik. Silhouette Score mengukur sejauh mana setiap sampel dalam kluster mendekati sampel-sampel dalam kluster lainnya, dibandingkan dengan kluster yang seharusnya. Disini saya juga menggunakan Metrik inertia sebagai pembanding, metrik inertia menggambarkan penyebaran data dalam kluster, di mana nilai inertia yang lebih rendah menunjukkan kluster yang lebih padat dan lebih baik.

Interpretasi Silhouette Score adalah sebagai berikut:

Jika Silhouette Score mendekati 1: Ini menunjukkan bahwa sampel-sampel dalam kluster saling berdekatan dengan baik dan secara jelas berbeda dengan sampel-sampel dalam kluster lainnya. Ini mengindikasikan pembagian kluster yang baik dan terpisah secara jelas dalam data Pokemon.

Jika Silhouette Score mendekati 0: Ini menunjukkan bahwa sampel-sampel memiliki keterhubungan yang tidak jelas dengan kluster tertentu atau terletak pada batas antara kluster. Ini mengindikasikan adanya ketidakpastian dalam pembagian kluster dan kemungkinan kesulitan dalam mengidentifikasi pemisahan yang jelas antara kelompok Pokemon.

Jika Silhouette Score negatif: Ini menunjukkan bahwa sebagian besar sampel mungkin telah ditempatkan dalam kluster yang salah atau terdapat overlap yang signifikan antara kluster. Ini menunjukkan bahwa pembagian kluster mungkin tidak sesuai dengan data Pokemon yang digunakan.

Berdasarkan metrik silhouette score, nilai paling besar mendekati 1 adalah 0.5967848800416774, yaitu cluster yang berjumlah 4 yang menggunakan algoritma K-Means dan nilai inertia 425.3343817537224 dengan jumlah cluster 4. Meskipun begitu jumlah cluster yang dipilih adalah 3 mempertimbangkan hasil yang didapatkan menggunakan metode Elbow diatas. Dikarenakan terdapat anomali nilai pada metrik silhouette score dan inertia, dimana semakin besar jumlah cluster maka nilai metrik semakin besar, begitu seterusnya.

## **Kesimpulan**

Setelah melakukan analisis clustering pada data Pokémon menggunakan atribut 'attack' dan 'defense', berikut adalah ringkasan kesimpulan dan rekomendasi yang dapat diambil dari penelitian ini:

1. Analisis Clustering:

    * Dilakukan clustering menggunakan metode KMeans untuk membagi Pokémon ke dalam kelompok berdasarkan atribut 'attack' dan 'defense'.
    * Jumlah cluster yang dihasilkan adalah 3.
    * Metrik evaluasi yang digunakan adalah Silhouette Score dan inertia.
    
2. Hasil Analisis:

    * Dalam analisis clustering, ditemukan 3 kelompok Pokémon berdasarkan atribut 'attack' dan 'defense'.
    * Kelompok-kelompok ini mencerminkan variasi dalam kemampuan serang dan pertahanan Pokémon.
    
3. Rekomendasi dan Insight:

    * Dengan memahami kelompok-kelompok Pokémon yang terbentuk, pemain Pokémon atau analis dapat mengidentifikasi perbedaan dan keunikan dalam atribut 'attack' dan         
      'defense'.
    * Kelompok Pokémon dengan tingkat 'attack' dan 'defense' yang tinggi dapat menjadi pilihan yang kuat untuk pertempuran atau strategi serangan.
    * Kelompok Pokémon dengan tingkat 'attack' yang rendah tetapi tingkat 'defense' yang tinggi mungkin lebih cocok untuk bertahan dan memiliki daya tahan yang baik dalam 
      pertempuran.
    * Melalui analisis clustering ini, dapat ditemukan wawasan baru tentang struktur dan karakteristik Pokémon berdasarkan atribut 'attack' dan 'defense'.
    * Rekomendasi lebih lanjut atau insight yang lebih mendalam dapat diperoleh dengan menganalisis atribut lainnya atau menggabungkan atribut 'attack' dan 'defense' dengan 
      atribut lainnya.
      
      
Hasil clustering pada data Pokémon, seperti yang dijelaskan sebelumnya, dapat memiliki potensi aplikasi dan manfaat dalam beberapa konteks, termasuk dalam permainan Pokémon atau bidang lainnya. Berikut adalah beberapa contoh potensi aplikasi dan manfaat hasil clustering ini:

1. Strategi Bermain Pokémon:

Dalam permainan Pokémon, pemain dapat menggunakan hasil clustering untuk mengidentifikasi kelompok Pokémon dengan kemampuan serang atau pertahanan yang serupa. Hal ini dapat membantu pemain dalam merencanakan strategi pertempuran dan memilih kombinasi Pokémon yang kuat berdasarkan kekuatan dan kelemahan mereka.

2. Tim Pembuatan Tim Pokémon:

Hasil clustering dapat digunakan sebagai panduan dalam pembuatan tim Pokémon yang seimbang. Pemain dapat memilih Pokémon dari berbagai kelompok dengan atribut yang berbeda untuk menciptakan tim yang kuat dengan kombinasi kemampuan serang dan pertahanan yang beragam.

3. Pengembangan Karakteristik Pokémon:

Hasil clustering dapat membantu pengembang permainan Pokémon dalam merancang karakteristik dan kemampuan Pokémon baru. Dengan memahami kelompok-kelompok yang terbentuk berdasarkan atribut 'attack' dan 'defense', pengembang dapat menciptakan Pokémon dengan kekuatan yang unik dan memperkaya pengalaman bermain pemain.

4. Analisis Pemain Pokémon:

Dalam komunitas pemain Pokémon, hasil clustering dapat digunakan untuk menganalisis preferensi dan gaya bermain pemain. Misalnya, pemain dengan preferensi terhadap Pokémon dengan serangan tinggi dapat diidentifikasi dan dipelajari pola-pola permainan mereka. Hal ini dapat memberikan wawasan tentang preferensi dan kecenderungan pemain dalam memilih Pokémon.

5. Analisis Perilaku Konsumen:

Metode clustering yang digunakan dalam analisis ini juga dapat diterapkan dalam bidang lain di luar permainan Pokémon. Contohnya adalah analisis perilaku konsumen, di mana data atribut yang relevan dapat digunakan untuk mengelompokkan konsumen ke dalam segmen berdasarkan preferensi, kebiasaan, atau karakteristik tertentu. Ini dapat membantu perusahaan dalam mengembangkan strategi pemasaran yang lebih efektif dan personalisasi pengalaman konsumen.

6. Penelitian Ilmiah:

Hasil clustering pada data Pokémon dapat digunakan dalam penelitian ilmiah terkait dengan pemahaman tentang karakteristik dan hubungan antara atribut 'attack' dan 'defense'. Ini dapat memberikan wawasan tentang pola-pola evolusi Pokémon, analisis tipe Pokémon, dan dampak atribut tertentu pada kinerja pertempuran.      
