# Laporan Proyek Machine Learning - Tika Putri Marsanti
# Prediksi Harga Berlian Menggunakan Algoritma Machine Learning

## Domain Proyek
Industri perhiasan merupakan salah satu sektor bernilai tinggi dalam perekonomian global, dengan perdagangan berlian sebagai salah satu komoditas utamanya. Penetapan harga berlian tidak hanya bergantung pada pasar, namun juga sangat dipengaruhi oleh karakteristik fisik berlian itu sendiri, seperti berat (carat), kualitas potongan (cut), kejernihan (clarity), dan warna (color). Secara tradisional, proses penilaian harga dilakukan oleh para ahli gemologi menggunakan metode manual berdasarkan panduan standar seperti 4C (Carat, Cut, Color, Clarity). Namun demikian, proses ini dapat menimbulkan beberapa kendala seperti keterbatasan sumber daya manusia ahli, potensi subjektivitas dalam penilaian, serta inkonsistensi harga antar pihak yang berbeda.

Teknologi Machine Learning (ML) dapat digunakan untuk membangun sistem prediksi harga berlian berbasis data, yang mampu mengestimasi harga berdasarkan karakteristik fisiknya secara objektif. Hal ini tidak hanya meningkatkan efisiensi dan akurasi penilaian harga, tetapi juga membuka peluang integrasi sistem ke berbagai platform seperti e-commerce perhiasan, layanan appraisal digital, hingga penilaian aset dalam asuransi atau pembiayaan.

Berbagai studi sebelumnya telah membuktikan efektivitas algoritma berbasis pohon keputusan seperti Random Forest dapat menyelesaikan masalah regresi, terutama pada data non-linear dengan banyak variabel. Model ensemble seperti Random Forest dapat menghasilkan prediksi yang lebih stabil dan akurat dibandingkan metode regresi linier klasik, terutama dalam kasus prediksi harga aset dengan variabilitas tinggi. 

Dengan demikian, penerapan machine learning dalam prediksi harga berlian merupakan solusi potensial untuk meningkatkan efisiensi, konsistensi, dan skala dalam industri perhiasan. Proyek ini bertujuan untuk membangun model prediktif yang dapat mempelajari pola hubungan antara atribut fisik berlian dan harga jualnya berdasarkan data historis, serta mengevaluasi kinerja model berdasarkan metrik yang relevan.

## Referensi
- [Machine Learning Algorithms](https://www.researchgate.net/publication/363621267_A_Survey_of_Ensemble_Learning_Concepts_Algorithms_Applications_and_Prospects)
- [Diamond Price Prediction Using Machine Learning Algorithms](https://www.researchgate.net/profile/Ayush-Vispute/publication/371171793_Diamond_Price_Prediction_Using_Machine_Learning_Algorithms/links/67bcadb48311ce680c738593/Diamond-Price-Prediction-Using-Machine-Learning-Algorithms.pdf)
- [Analysis Comparison of K-Nearest Neighbor, Multi-LayerPerceptron, and Decision Tree Algorithms in Diamond Price Prediction](https://cogito.unklab.ac.id/index.php/cogito/article/view/532/350)

## Business Understanding

Penilaian harga berlian merupakan aspek krusial dalam industri perhiasan. Harga berlian ditentukan oleh kombinasi berbagai atribut fisik yang dikenal dengan konsep 4C: carat, cut, color, dan clarity. Namun dalam praktiknya, penilaian harga oleh ahli gemologi masih bersifat subjektif dan memerlukan pengalaman yang tinggi. Hal ini membuka peluang bagi solusi otomatis berbasis teknologi, khususnya Machine Learning, untuk menghasilkan prediksi harga yang lebih objektif, efisien, dan konsisten.Dengan data historis penjualan berlian yang mencakup atribut fisik dan harga aktual, kita dapat mengembangkan model prediktif untuk mengestimasi harga berlian baru secara otomatis.

Bagian laporan ini mencakup:

## Problem Statements
1. Bagaimana cara memprediksi harga berlian secara akurat berdasarkan atribut fisiknya?

2. Fitur-fitur apa saja yang memiliki pengaruh paling signifikan terhadap harga berlian?

3. Model Machine Learning mana yang paling efektif dalam melakukan prediksi harga berlian?

## Goals
Mengembangkan model prediktif berbasis Machine Learning untuk memperkirakan harga berlian menggunakan data historis.

Mengidentifikasi atribut (fitur) yang paling berpengaruh terhadap harga, baik secara statistik maupun melalui teknik interpretabilitas model.

Menentukan model terbaik berdasarkan hasil evaluasi untuk digunakan sebagai solusi akhir dalam prediksi harga.

## Solution Statements
Untuk menjawab problem statements dan mencapai goals di atas, pendekatan solusi dilakukan melalui tahapan berikut:

1. Pemodelan menggunakan berbagai algoritma regresi, yaitu:

- Linear Regression sebagai baseline model yang sederhana dan mudah ditafsirkan.

- Decision Tree Regressor, algoritma berbasis pohon keputusan yang dapat menangani data non-linear.

- Random Forest Regressor, model ensemble yang menggabungkan banyak decision tree untuk meningkatkan akurasi dan mengurangi overfitting.

- K-Nearest Neighbors Regressor (KNN), algoritma instance-based yang menggunakan jarak antar sampel untuk prediksi.

2. Hyperparameter Tuning dan Validasi Silang (Cross-Validation)
Dilakukan untuk mengoptimalkan performa model, khususnya Random Forest dan KNN, dengan menggunakan teknik seperti Grid Search atau Randomized Search agar hasil prediksi tidak hanya akurat tetapi juga andal di data baru.

3. Evaluasi menggunakan metrik regresi, yaitu:

- MAE (Mean Absolute Error): untuk mengetahui rata-rata selisih absolut antara prediksi dan nilai aktual.

- RMSE (Root Mean Squared Error): untuk memperhatikan penalti terhadap error besar.

- R² Score: untuk mengukur proporsi variasi data yang dapat dijelaskan oleh model.

3. Analisis fitur penting (feature importance) dari model Random Forest untuk mengetahui atribut-atribut yang paling berpengaruh terhadap harga.

## Data Understanding
Proyek ini menggunakan dataset publik yang tersedia di Kaggle: Diamonds Dataset by Shivam Bansal. Dataset ini berisi informasi detail mengenai lebih dari 50.000 berlian, termasuk harga dan karakteristik fisiknya. Dataset ini sering digunakan sebagai benchmark dalam studi prediktif harga karena cukup lengkap dan representatif terhadap kondisi pasar perhiasan.

Dataset memiliki total 53.940 entri dan 10 kolom, dengan masing-masing baris merepresentasikan satu unit berlian.

## Variabel-variabel pada Diamonds dataset adalah sebagai berikut:
- carat: berat berlian dalam satuan karat. Semakin berat, biasanya semakin mahal.

- cut: kualitas potongan berlian. Merupakan kategori ordinal: Fair, Good, Very Good, Premium, Ideal.

- color: tingkat warna berlian, dikategorikan dari D (terjernih) hingga J (paling kuning).

- clarity: tingkat kejernihan berlian, dikategorikan dari I1 (terburuk) hingga IF (terbaik).

- depth: total kedalaman berlian sebagai persentase dari rata-rata diameter.

- table: lebar bagian atas berlian sebagai persentase dari rata-rata diameter.

- price: harga dalam dolar AS. Ini adalah target variabel (variabel yang diprediksi).

- x: panjang berlian dalam milimeter.

- y: lebar berlian dalam milimeter.

- z: tinggi berlian dalam milimeter.

## Unvariate Analisys
Univariate Analysis adalah menganalisis setiap fitur secara terpisah.
## Kategorical
Fitur kategorikal dalam dataset berlian meliputi: cut, color, dan clarity. Analisis dilakukan dengan menghitung frekuensi dan membuat visualisasi (bar chart) untuk melihat proporsi masing-masing kategori.

![Screenshot 2025-05-09 at 13:45:24](https://github.com/user-attachments/assets/a2b94bfb-ee3d-41dd-b01b-55bb0a680023)

## Numerik

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

