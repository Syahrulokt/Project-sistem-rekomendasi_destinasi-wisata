# Laporan Proyek Machine Learning - Mochammad Syahrul Abidin

## Project Overview

Yogyakarta adalah salah satu destinasi wisata terpopuler di Indonesia, yang dikenal dengan kekayaan budaya, sejarah, dan keindahan alamnya. Namun, sektor pariwisata di Yogyakarta mengalami tantangan signifikan akibat pandemi COVID-19 yang menyebabkan penurunan jumlah wisatawan dan gangguan pada aktivitas pariwisata. Seiring dengan pemulihan sektor ini sejak Oktober 2021, banyak wisatawan mulai kembali, namun preferensi mereka terhadap destinasi wisata kini semakin beragam. Oleh karena itu, penting untuk mengembangkan sistem yang dapat memberikan rekomendasi destinasi wisata yang relevan dan sesuai dengan minat serta preferensi pengguna [1][2].

Proyek ini bertujuan untuk mengembangkan sistem rekomendasi destinasi wisata di Yogyakarta yang memanfaatkan data pengguna dan penilaian terhadap destinasi wisata yang ada. Sistem rekomendasi ini bertujuan untuk membantu wisatawan dalam memilih tempat wisata berdasarkan ulasan pengguna sebelumnya, popularitas tempat, dan faktor-faktor lain seperti lokasi geografis, harga, serta ketersediaan fasilitas. Dengan sistem rekomendasi yang cerdas, wisatawan tidak hanya mendapatkan informasi yang sesuai dengan preferensi pribadi mereka, tetapi juga dapat mengoptimalkan pengalaman berwisata mereka dengan memilih tempat yang menawarkan nilai terbaik sesuai dengan harapan mereka.

Solusi yang Ditawarkan:
Sistem rekomendasi yang dikembangkan dalam proyek ini menggunakan data penilaian dan ulasan pengguna terhadap destinasi wisata di Yogyakarta untuk memberikan rekomendasi yang lebih terarah dan relevan bagi wisatawan. Sistem ini akan mempertimbangkan berbagai faktor, seperti rating tempat wisata, jenis aktivitas yang ditawarkan, lokasi geografis, dan preferensi pengguna untuk memberikan rekomendasi yang lebih personal [3].

Daftar referensi:
[1] E. Suhailah and H. Hartatik, "Pembuatan Sistem Rekomendasi Pariwisata Yogyakarta Menggunakan Triangle Multiplaying Jaccard," JACIS: Journal Automation Computer Information System, vol. 3, no. 2, pp. 115-126, Nov. 2023.
[2] H. Hartatik, S. D. Nurhayati, and W. Widayani, "Sistem Rekomendasi Wisata Kuliner di Yogyakarta dengan Metode Item-Based Collaborative Filtering," JACIS: Journal Automation Computer Information System, vol. 1, no. 2, pp. 55-63, Nov. 2021.
[3] I. Suryadi, D. H. Gutama, D. Danianti, and A. S. Yazid, "Sistem Rekomendasi Tempat Wisata Alam di Gunung Kidul Menggunakan Algoritma Content Based Filtering Berbasis Web," JATI (Jurnal Mahasiswa Teknik Informatika), vol. 9, no. 2, pp. 97-105, Apr. 2025.

## Business Understanding

Pada bagian ini, menjelaskan proses klarifikasi masalah dengan proyek rekomendasi destinasi wisata di Yogyakarta. Berdasarkan proyek yang diangkat, tujuan utama adalah membangun sistem yang dapat memberikan rekomendasi destinasi wisata yang relevan dan sesuai dengan preferensi pengguna. Sistem ini mempertimbangkan faktor-faktor penting, seperti rating pengguna, kategori destinasi wisata, dan harga tiket.

Bagian laporan ini mencakup:

### Problem Statements

Pernyataan masalah yang ada dalam proyek ini adalah sebagai berikut:
1. Banyak wisatawan mengalami kesulitan dalam memilih destinasi wisata yang sesuai dengan preferensi mereka di Yogyakarta karena terdapat begitu banyak pilihan destinasi yang ada. Hal ini semakin rumit dengan adanya pandemi COVID-19 yang mengubah pola wisatawan dan mengubah preferensi mereka terhadap jenis tempat wisata yang dikunjungi.
2. Tidak adanya sistem yang dapat memanfaatkan data ulasan dan penilaian pengguna untuk memberikan rekomendasi yang personal. Wisatawan sering kali bergantung pada sumber informasi yang terbatas dan kurang tepat untuk memilih destinasi yang sesuai.
3. Keberagaman jenis destinasi wisata di Yogyakarta, seperti wisata alam, budaya, kuliner, dan sejarah, membuat sulit bagi wisatawan untuk memilih tempat yang tepat tanpa informasi yang relevan dan terperinci yang dapat menyesuaikan dengan keinginan atau kebutuhan mereka.


### Goals

Berdasarkan pernyataan masalah yang ada, berikut adalah tujuan proyek yang diharapkan dapat menyelesaikan masalah-masalah tersebut:
1. Membangun sebuah sistem rekomendasi destinasi wisata yang personal dan relevan berdasarkan ulasan pengguna sebelumnya, untuk memudahkan wisatawan dalam memilih destinasi wisata sesuai dengan preferensi pribadi mereka, meskipun ada banyak pilihan destinasi wisata di Yogyakarta.
2. Menggunakan data ulasan dan penilaian pengguna untuk memberikan rekomendasi destinasi yang lebih personal. Sistem rekomendasi ini akan memanfaatkan algoritma yang berbasis pada data pengguna untuk menghasilkan rekomendasi yang sesuai dengan keinginan dan minat pengguna.
3. Menyusun sistem rekomendasi yang dapat menyesuaikan dengan berbagai jenis destinasi wisata, sehingga wisatawan dapat dengan mudah menemukan destinasi yang sesuai dengan minat mereka berdasarkan analisis data.

### Solution Approach
Untuk mencapai tujuan yang telah ditetapkan, pendekatan yang digunakan adalah Collaborative Filtering, yang diimplementasikan menggunakan teknik Matrix Factorization dengan embedding. Berikut adalah pendekatan yang akan digunakan dalam proyek ini:
- Proyek ini menggunakan model berbasis Matrix Factorization yang disebut RecommenderNet. Model ini memanfaatkan teknik embedding untuk pengguna dan tempat wisata untuk memetakan keduanya ke dalam ruang vektor yang lebih rendah, yang memungkinkan model untuk memprediksi rating yang akan diberikan pengguna terhadap tempat-tempat yang belum mereka kunjungi.
- Dengan pendekatan ini, model menghasilkan rekomendasi destinasi wisata untuk setiap pengguna berdasarkan rating yang diberikan oleh pengguna lain yang memiliki preferensi serupa.
- Model ini menggunakan layer embedding untuk pengguna dan tempat wisata, serta bias untuk pengguna dan tempat wisata. Selanjutnya, model menghitung perkalian dot dari embedding pengguna dan tempat wisata untuk menghasilkan skor prediksi.

#### Proses:
1. Data pengguna dan destinasi wisata di-encode menjadi format numerik menggunakan teknik encoding agar dapat digunakan dalam model.
2. Rating pada destinasi wisata diprediksi berdasarkan input pengguna dan tempat wisata yang belum dikunjungi, menghasilkan rekomendasi berdasarkan prediksi rating tertinggi.
3. Hasil akhir dari sistem rekomendasi adalah 7 destinasi dengan rating tertinggi yang dapat dikunjungi oleh pengguna.

## Data Understanding
Pada bagian ini, menjelaskan dataset yang digunakan dalam proyek sistem rekomendasi destinasi wisata di Yogyakarta. Dataset ini terdiri dari tiga file utama yang digunakan dalam analisis:
- tourism_with_id.csv: Berisi informasi mengenai destinasi wisata di Yogyakarta, termasuk kategori wisata, harga, dan rating.
- user.csv: Berisi informasi mengenai pengguna yang memberikan penilaian terhadap destinasi wisata.
- tourism_rating.csv: Berisi penilaian yang diberikan oleh pengguna terhadap berbagai destinasi wisata.

1. tourism_with_id.csv
File ini berisi informasi tentang destinasi wisata di Yogyakarta, dengan kolom-kolom sebagai berikut:
- Place_Id: ID unik untuk setiap destinasi wisata.
- Place_Name: Nama dari destinasi wisata.
- Description: Deskripsi destinasi wisata.
- Category: Kategori destinasi wisata.
- City: Kota destinasi wisata.
- Price: Harga tiket atau biaya masuk destinasi wisata.
- Rating: Rating keseluruhan destinasi wisata berdasarkan ulasan pengunjung.
- Coordinate: Kombinasi dari dua angka, yaitu latitude (lintang) dan longitude (bujur).
- Lat: Koordinat geografis destinasi yang menunjukkan posisi utara atau selatan dari garis khatulistiwa (lintang).
- Long: Koordinat geografis destinasi yang menunjukkan posisi timur atau barat dari garis meridian utama (bujur).

Data dalam file ini menunjukkan berbagai kategori destinasi wisata di Yogyakarta, dari wisata alam hingga wisata budaya. Proses Pembersihan Data meliputi, Beberapa kolom yang tidak relevan atau memiliki data yang tidak terpakai seperti Unnamed: 11 dan Unnamed: 12 telah dihapus. Dataset ini difilter hanya untuk destinasi wisata di Yogyakarta, sesuai dengan tujuan proyek ini.

2. user.csv
File ini berisi informasi pengguna yang memberikan ulasan terhadap destinasi wisata:
- User_Id: ID unik untuk setiap pengguna.
- Age: Umur pengguna.
- Location: Lokasi pengguna, yang menunjukkan asal kota pengguna.

Pembersihan Data meliputi, Data pengguna yang memberikan ulasan untuk destinasi wisata Yogyakarta dipilih, dan hanya pengguna yang memberikan rating di Yogyakarta yang dipertahankan.

3. tourism_rating.csv
File ini berisi informasi mengenai penilaian yang diberikan oleh pengguna terhadap destinasi wisata di Yogyakarta:
- User_Id: ID pengguna yang memberikan rating.
- Place_Id: ID destinasi wisata yang diberi rating.
- Place_Ratings: Nilai rating yang diberikan oleh pengguna untuk destinasi wisata.

Proses Pembersihan Data meliputi, Data ini digabungkan dengan file tourism_with_id.csv untuk memastikan bahwa hanya destinasi wisata di Yogyakarta yang digunakan. Rating pada destinasi wisata dinormalisasi agar memiliki nilai yang konsisten untuk analisis lebih lanjut.

### Jumlah Total Baris Data:
- tourism_with_id.csv: 437 baris data.
- user.csv: 300 baris data.
- tourism_rating.csv: 10.000 baris data.

### Kondisi Data:
- Missing Values: Terdapat beberapa nilai yang hilang dalam beberapa kolom, terutama pada kolom yang terkait dengan skor ulasan dan informasi pengguna.
- Data Cleaning: Beberapa kolom numerik, seperti Price, disimpan dalam format string dengan simbol atau karakter yang tidak relevan (misalnya "$" atau ",") yang perlu diubah menjadi format numerik.

### Distribusi Data:
- Price: Harga tiket atau biaya masuk destinasi wisata di Yogyakarta sangat bervariasi, dengan sebagian besar destinasi memiliki harga antara Rp 50.000 hingga Rp 200.000 per malam. Namun, ada beberapa destinasi dengan harga yang lebih tinggi, yang mungkin merupakan outlier.
- Ratings: Distribusi rating juga bervariasi, dengan sebagian besar destinasi memiliki jumlah ulasan yang relatif sedikit, namun ada beberapa destinasi yang memiliki banyak ulasan (lebih dari 500 ulasan).

### Masalah Umum pada Data:
- Missing Values: Beberapa kolom memiliki nilai yang hilang, terutama pada kolom-kolom yang terkait dengan informasi ulasan dan host.
- Data Format: Beberapa kolom numerik disimpan sebagai string dengan simbol seperti "$", ",", atau "%", yang perlu dibersihkan untuk analisis lebih lanjut.
- Boolean Encoding: Beberapa kategori boolean disimpan dalam format string yang perlu diubah menjadi format numerik (0/1).

### Exploratory data analysis:
Berdasarkan hasil eksplorasi data yang telah dilakukan, beberapa insight yang dapat diperoleh adalah:
- Kategori Wisata: Ada variasi yang jelas dalam jumlah destinasi wisata yang tersedia berdasarkan kategori. Ini memberi gambaran tentang jenis wisata yang lebih banyak diminati di Yogyakarta.

gambar 1

- Usia Pengunjung: Sebagian besar pengunjung berasal dari rentang usia tertentu, yang dapat membantu dalam menyesuaikan jenis rekomendasi destinasi berdasarkan segmen pasar usia.

gambar 2


- Harga Tiket: Rentang harga tiket sangat bervariasi, dengan beberapa destinasi menawarkan harga yang lebih terjangkau sementara destinasi lainnya memiliki harga premium, yang harus dianalisis lebih lanjut untuk memutuskan strategi harga.

gambar 3

- Asal Kota Pengunjung: Mengetahui asal kota pengunjung dapat membantu dalam strategi pemasaran, mengingat kota mana yang paling banyak memberikan pengunjung ke Yogyakarta.

gambar 4

## Data Preparation
Berikut adalah teknik yang digunakan untuk mempersiapkan data dalam proyek sistem rekomendasi destinasi wisata di Yogyakarta:
1. Melakukan Encoding dengan mengubah kolom User_Id dan Place_Id yang awalnya berupa data kategorikal menjadi angka untuk memudahkan pemrosesan oleh model machine learning. Proses ini dilakukan dengan menggunakan fungsi encoding. Karena Encoding data kategorikal (seperti User_Id dan Place_Id) menjadi nilai numerik adalah langkah penting karena model machine learning tidak dapat bekerja dengan data teks atau kategorikal secara langsung. Mengonversi nilai tersebut ke angka memungkinkan model untuk memproses data secara efisien.
2. Mengonversi rating ke format numerik, memastikan bahwa kolom Place_Ratings berada dalam format numerik, karena model memerlukan data numerik untuk melakukan perhitungan. Rating pada destinasi wisata pada awalnya bisa jadi dalam format yang tidak cocok untuk analisis numerik, seperti dalam bentuk string atau integer dengan simbol. Mengonversinya menjadi float memastikan bahwa data dapat dihitung dan diproses oleh model yang akan digunakan.
3. Data kemudian diacak (shuffle) untuk memastikan bahwa urutan data tidak mempengaruhi hasil pelatihan model. Pengacakan ini juga membantu dalam menghindari overfitting. Karena Pengacakan data diperlukan untuk memastikan bahwa model tidak terpengaruh oleh urutan data yang mungkin memiliki pola tertentu. Misalnya, jika data dikelompokkan berdasarkan kategori, model bisa saja terjebak dalam pola tersebut, sehingga tidak dapat belajar dari data yang lebih luas.

## Modeling
Tahapan Modeling ini membahas mengenai pembangunan sistem rekomendasi yang digunakan untuk memberikan solusi terhadap permasalahan dalam memilih destinasi wisata yang sesuai dengan preferensi pengguna. Dua algoritma rekomendasi yang berbeda akan dibahas, yaitu Matrix Factorization menggunakan Neural Network dan Collaborative Filtering.

A. Matrix Factorization dengan Neural Network (RecommenderNet)
Salah satu pendekatan yang digunakan dalam model ini adalah Matrix Factorization, yang diterapkan dengan menggunakan Neural Network. Model ini dikenal dengan nama RecommenderNet dan dirancang untuk memetakan pengguna dan tempat wisata ke dalam ruang vektor yang lebih rendah menggunakan teknik embedding. Dengan demikian, model ini dapat memprediksi rating yang akan diberikan oleh pengguna terhadap tempat wisata yang belum mereka kunjungi, berdasarkan interaksi antara pengguna dan tempat wisata di masa lalu.
* Proses Model RecommenderNet:
    - Embedding User dan Place: Data pengguna dan tempat wisata di-encode ke dalam vektor berdimensi rendah menggunakan embedding layers. Ini memungkinkan model untuk belajar dari interaksi antara pengguna dan destinasi wisata.
    - Bias Pengguna dan Tempat: Model ini juga memperhitungkan bias untuk masing-masing pengguna dan tempat wisata, yang mencerminkan kecenderungan individu dan destinasi wisata dalam memberikan rating.
    - Perkalian Dot dan Penambahan Bias: Untuk mendapatkan prediksi rating, model menghitung perkalian dot antara vektor pengguna dan tempat wisata, kemudian menambahkan bias untuk pengguna dan tempat wisata.
* Kelebihan Model Matrix Factorization dengan Neural Network:
    - Model ini dapat memberikan rekomendasi yang sangat personal, memanfaatkan interaksi historis antara pengguna dan destinasi.
    - Model ini dapat menangani dataset besar karena menggunakan embedding, yang memungkinkan representasi vektor rendah dimensi.
* Kekurangan:
    - Jika tidak diatur dengan benar, model ini bisa mengalami overfitting pada data training, terutama jika data pengguna sangat terbatas.

B. Collaborative Filtering
Selain Matrix Factorization, pendekatan lain yang dapat digunakan untuk sistem rekomendasi adalah Collaborative Filtering. Algoritma ini bekerja dengan cara menganalisis kesamaan antara pengguna yang memiliki preferensi serupa dan memberikan rekomendasi berdasarkan penilaian yang diberikan oleh pengguna lain yang mirip.
* Proses Collaborative Filtering:
    - Kesesuaian Pengguna: Collaborative Filtering berfokus pada kesamaan antara pengguna, menggunakan teknik seperti user-based atau item-based untuk menemukan pengguna atau item yang memiliki kesamaan dengan yang lain.
    - Prediksi Rating: Berdasarkan kesamaan ini, algoritma memprediksi rating yang akan diberikan oleh pengguna pada item yang belum mereka beri rating.
* Kelebihan Collaborative Filtering:
    - Berbeda dengan teknik Matrix Factorization, Collaborative Filtering tidak memerlukan proses pelatihan yang kompleks.
    - Jika banyak pengguna memberikan penilaian terhadap tempat wisata yang sama, rekomendasi yang dihasilkan dapat sangat relevan.

* Kekurangan:
    - Cold Start Problem: Sulit untuk memberikan rekomendasi kepada pengguna baru atau item baru yang belum memiliki cukup banyak interaksi.
    - Keterbatasan dalam Menangani Data Sparse: Jika data yang ada sangat jarang (seperti hanya sedikit pengguna yang memberikan rating untuk destinasi tertentu), Collaborative Filtering mungkin tidak efektif.

C. Top-N Recommendation
Sebagai hasil dari model rekomendasi, sistem ini dapat memberikan Top-N Recommendation, yaitu daftar 7 destinasi wisata teratas yang direkomendasikan untuk setiap pengguna berdasarkan model yang telah dilatih. 
* Kelebihan Top-N Recommendation:
    - Dengan memberikan Top-N destinasi wisata, sistem ini mempermudah pengguna untuk memilih dari pilihan yang relevan dan dipersonalisasi.
    - Sistem ini dapat dengan mudah memberikan rekomendasi kepada banyak pengguna dengan mengoptimalkan proses prediksi.
* Kekurangan:
    - Sistem ini membutuhkan data pengguna dan rating yang cukup untuk menghasilkan rekomendasi yang baik. Jika data terbatas, kualitas rekomendasi akan berkurang.

gambar top-N

## Evaluation
Pada bagian Evaluation, menjelaskan metrik evaluasi yang digunakan untuk menilai kinerja model sistem rekomendasi destinasi wisata di Yogyakarta. Menggunakan Root Mean Squared Error (RMSE) sebagai metrik evaluasi utama untuk menilai kualitas prediksi rating yang diberikan oleh model. Selain itu, juga menggunakan Binary Crossentropy sebagai fungsi loss dalam proses pelatihan.
A. Root Mean Squared Error (RMSE)
RMSE adalah salah satu metrik yang paling umum digunakan dalam sistem rekomendasi untuk mengevaluasi kesalahan prediksi antara rating yang diprediksi oleh model dengan rating asli yang diberikan oleh pengguna. RMSE menghitung akar kuadrat dari rata-rata kesalahan kuadrat, yang memberikan gambaran tentang seberapa besar kesalahan rata-rata dari model dalam memprediksi rating.
* Alasan Penggunaan RMSE:
    - RMSE memberikan kesalahan rata-rata yang mudah dipahami karena berada dalam satuan yang sama dengan rating, sehingga bisa memberikan gambaran langsung tentang kualitas prediksi model.
    - RMSE lebih sensitif terhadap kesalahan besar, sehingga model akan berusaha mengurangi kesalahan besar yang dapat sangat mempengaruhi kualitas rekomendasi.

B. Binary Crossentropy (Loss Function)
Sebagai fungsi loss, menggunakan Binary Crossentropy untuk meminimalkan perbedaan antara rating yang diprediksi oleh model dan rating asli. Fungsi ini cocok karena kita menganggap rating sebagai probabilitas dan model bertujuan untuk menghasilkan rating yang sebanding dengan rating asli yang diberikan oleh pengguna.
* Alasan Penggunaan Binary Crossentropy:
    - Binary Crossentropy efektif untuk menghitung kesalahan dalam probabilitas, yang sesuai untuk konteks ini di mana kita berusaha memprediksi rating antara 0 dan 1.

Berikut adalah hasil evaluasi model:

| Epoch | Train RMSE |	Validation RMSE | Train Loss | Validation Loss |
|:-----:|:-----:|:-----:|:-----:|:-----:|
| 100 | 0.32 | 0.35 | 0.65 | 0.70 |

gambar evaluasi
