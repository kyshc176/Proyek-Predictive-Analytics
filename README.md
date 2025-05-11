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
<img width="667" alt="Screenshot 2025-05-09 at 13 45 36" src="https://github.com/user-attachments/assets/aaece686-3a40-42c9-884c-5a3e9113b608" />
<img width="666" alt="Screenshot 2025-05-09 at 13 45 42" src="https://github.com/user-attachments/assets/1314f9bf-15c5-4412-8757-b7e1bf5c9e22" />
<img width="662" alt="Screenshot 2025-05-09 at 13 45 51" src="https://github.com/user-attachments/assets/618417d4-0070-4fb8-bec9-e320dc011126" />
# Analisis
- Data cenderung terkonsentrasi pada kualitas menengah hingga tinggi untuk semua atribut.
- Hal ini menunjukkan bahwa dataset didominasi oleh berlian dengan karakteristik umum yang bernilai jual cukup tinggi (clarity sedang, warna netral, dan potongan bagus).

## Numerik
Fitur numerik meliputi: carat, depth, table, x, y, z, dan price.

<img width="595" alt="Screenshot 2025-05-09 at 13 45 29" src="https://github.com/user-attachments/assets/d2d4b381-9dcf-428c-9714-f906b9aa8480" />
<img width="882" alt="Screenshot 2025-05-09 at 13 47 59" src="https://github.com/user-attachments/assets/b648350c-b694-4192-9db8-40db70a6fb47" />
<img width="892" alt="Screenshot 2025-05-09 at 13 48 06" src="https://github.com/user-attachments/assets/61b83625-3ecd-4fff-9edf-2d7a556b567b" />

# Analisi
- Baik distribusi carat maupun harga menunjukkan pola skew ke kanan, yang umum terjadi karena berlian dengan carat besar atau harga tinggi jarang ditemukan.

- Korelasi potensial: Ada indikasi bahwa semakin besar carat, semakin tinggi harga, namun distribusi ini tetap perlu dianalisis secara statistik (misalnya korelasi atau scatter plot) untuk mengonfirmasi hubungan langsung.

## Multivariate Analisys
Multivariate Analysis menunjukkan hubungan antara dua atau lebih fitur dalam data.

# Regresi Price vs Y
<img width="606" alt="Screenshot 2025-05-09 at 13 48 13" src="https://github.com/user-attachments/assets/99de3544-4bc1-4aff-91de-94bb7a134d96" />
# Regresi Price vs z
<img width="589" alt="Screenshot 2025-05-09 at 13 48 20" src="https://github.com/user-attachments/assets/1b6d10d6-4e2f-4fcf-a197-b0b249984b80" />
# Regresi Price vs Depth
<img width="611" alt="Screenshot 2025-05-11 at 12 42 10" src="https://github.com/user-attachments/assets/957d9e11-9b8e-47d0-b8e9-f24b47eebee0" />
# Regresi Price vs Table
<img width="607" alt="Screenshot 2025-05-11 at 12 42 16" src="https://github.com/user-attachments/assets/b4915730-a47e-4a7a-8adf-50b82fa91491" />
# Korelasi
<img width="803" alt="Screenshot 2025-05-09 at 13 48 30" src="https://github.com/user-attachments/assets/89bd161e-0f16-4044-84f9-1078b1702f84" />

# Analisis
1. Fitur yang paling berpengaruh terhadap harga (price) adalah carat, dengan nilai korelasi sangat tinggi sebesar 0.92. Hal ini menunjukkan bahwa semakin besar berat berlian, semakin tinggi harganya.
2. Dimensi fisik (x, y, z) juga memiliki korelasi tinggi dengan harga, masing-masing di atas 0.85. Ini memperkuat bahwa ukuran fisik berlian merupakan faktor utama penentu harga.
3. Fitur-fitur seperti depth dan table memiliki korelasi sangat rendah atau hampir nol terhadap harga, yang menunjukkan kontribusinya terhadap prediksi harga mungkin tidak signifikan.
4. Fitur kategorikal (cut, color, dan clarity) memiliki korelasi rendah terhadap harga, namun ini bisa disebabkan oleh bentuk data aslinya yang ordinal atau kategorikal — sehingga korelasi linear mungkin tidak sepenuhnya mencerminkan pengaruh sebenarnya. Transformasi fitur (seperti encoding) bisa membantu meningkatkan peran fitur ini dalam model.
5. Terdapat multikolinearitas tinggi antar fitur dimensi fisik (carat, x, y, z) dengan korelasi di atas 0.95, yang bisa menyebabkan redundansi pada model regresi linier. Untuk menghindari ini, bisa dilakukan seleksi fitur atau teknik seperti PCA.

## Data Preparation
1. One Hot Encoding

One hot encoding adalah teknik mengubah data kategorik menjadi data numerik dimana setiap kategori menjadi kolom baru dengan nilai 0 atau 1. Fitur yang akan diubah menjadi numerik pada proyek ini adalah Area Type, City, Furnishing Status, dan Tenant Preferred.

2. Train Test Split

Train test split aja proses membagi data menjadi data latih dan data uji. Data latih akan digunakan untuk membangun model, sedangkan data uji akan digunakan untuk menguji performa model. Pada proyek ini dataset sebesar 3696 dibagi menjadi 3511 untuk data latih dan 185 untuk data uji.

3. Normalization

Algoritma machine learning akan memiliki performa lebih baik dan bekerja lebih cepat jika dimodelkan dengan data seragam yang memiliki skala relatif sama. Salah satu teknik normalisasi yang digunakan pada proyek ini adalah Standarisasi dengan sklearn.preprocessing.StandardScaler.

## Modeling
Untuk menyelesaikan permasalahan regresi prediksi harga berlian, proyek ini menggunakan empat algoritma Machine Learning: Linear Regression, Decision Tree Regressor, Random Forest Regressor, dan K-Nearest Neighbors Regressor (KNN). Tujuan utamanya adalah memilih model terbaik berdasarkan performa prediksi terhadap harga berlian, dengan mempertimbangkan akurasi serta kompleksitas model.

1. K-Nearest Neighbors (KNN)
K-Nearest Neighbors adalah algoritma yang memprediksi nilai target berdasarkan rata-rata nilai dari k tetangga terdekat di ruang fitur. Jarak antar data dihitung (misalnya dengan Euclidean distance), dan prediksi didasarkan pada k sampel terdekat dari data uji.

- Library: sklearn.neighbors.KNeighborsRegressor

- Kelebihan:

- Sederhana dan intuitif

- Tidak membutuhkan pelatihan (lazy learner)

- Kekurangan:

- Kurang efisien pada dataset besar

- Sensitif terhadap fitur yang tidak dinormalisasi

2. Random Forest Regressor
Random Forest adalah algoritma ensemble berbasis Decision Tree. Model ini membangun banyak pohon keputusan dan menghasilkan prediksi akhir berdasarkan rata-rata dari hasil tiap pohon. Metode ini mampu mengurangi overfitting dan meningkatkan generalisasi.

- Library: sklearn.ensemble.RandomForestRegressor

- Kelebihan:

- Lebih stabil dan akurat dari decision tree tunggal

- Dapat menangani data non-linear dan fitur dengan skala berbeda

- Kekurangan:

- Kurang interpretatif dibanding model sederhana

- Waktu pelatihan relatif lebih lama

3. Decision Tree Regressor
Decision Tree membagi data ke dalam simpul berdasarkan fitur yang meminimalkan error, membentuk struktur pohon keputusan.

- Library: sklearn.tree.DecisionTreeRegressor

- Kelebihan:

- Menangani data non-linear

- Tidak butuh normalisasi fitur

- Kekurangan:

- Rentan terhadap overfitting jika kedalaman pohon terlalu besar

## Evaluation
Pada bagian ini, dilakukan evaluasi untuk menilai kinerja masing-masing model yang telah dibangun. Untuk proyek prediksi harga berlian, kami menggunakan dua metrik evaluasi utama yang sesuai dengan masalah regresi, yaitu R² Score dan RMSE (Root Mean Squared Error).
Metrik Evaluasi yang Digunakan
1. R² Score (Coefficient of Determination)
R² Score mengukur seberapa baik variabilitas data target dapat dijelaskan oleh model. Nilai R² berkisar antara 0 dan 1, di mana:
- Nilai R² = 1 menunjukkan model dapat menjelaskan seluruh variabilitas data dengan sempurna.
- Nilai R² = 0 menunjukkan model tidak lebih baik dari model rata-rata (mean).
- Nilai R² < 0 menunjukkan model tidak dapat menjelaskan data lebih baik daripada model dengan tebakan acak.
<img width="353" alt="Screenshot 2025-05-11 at 13 22 19" src="https://github.com/user-attachments/assets/0b0f3cfe-745c-48d3-b090-151d5db42a19" />

2. Root Mean Squared Error (RMSE)
MSE mengukur rata-rata kuadrat perbedaan antara nilai yang diprediksi dan nilai yang sebenarnya. Metrik ini lebih sensitif terhadap perbedaan besar (outlier) dibandingkan RMSE, karena kesalahan dihitung dalam bentuk kuadrat.
<img width="375" alt="Screenshot 2025-05-11 at 13 27 33" src="https://github.com/user-attachments/assets/ae75a686-929c-4928-8a94-beeb130d2b46" />

# Hasil Evaluasi
|Model	|MSE	|R² |
|Linear Regression|	1.29e+06|	0.92|
|Decision Tree|	7.16e+05|	0.95|
|Random Forest|	4.09e+05|	0.97|
|K-Nearest Neighbors|	6.84e+05|	0.96|

<img width="752" alt="Screenshot 2025-05-11 at 13 38 26" src="https://github.com/user-attachments/assets/a461aa3d-3f17-4576-b5d4-b3991dc6053c" />
<img width="730" alt="Screenshot 2025-05-11 at 13 38 02" src="https://github.com/user-attachments/assets/004b0af2-8306-4616-9015-ce50333097f1" />

Berdasarkan hasil evaluasi menggunakan metrik  MSE (Mean Squared Error) dan R² Score, dapat disimpulkan bahwa Random Forest Regressor adalah model terbaik untuk memprediksi harga berlian dalam proyek ini. Berikut adalah beberapa poin kesimpulan penting:

Random Forest Regressor memiliki performa terbaik dengan nilai:

- MSE terendah (4.09e+05), yang mengindikasikan bahwa kesalahan prediksi pada model ini lebih kecil dan penalti terhadap kesalahan besar lebih rendah.

- R² Score tertinggi (0.97), yang menunjukkan bahwa model ini dapat menjelaskan 97% dari variabilitas data harga berlian, jauh lebih tinggi dibandingkan model lain.

**---Ini adalah bagian akhir laporan---**
