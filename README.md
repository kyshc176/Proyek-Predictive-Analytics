# Laporan Proyek Machine Learning - Tika Putri Marsanti
# Bank Marketing Effectiveness Prediction

## Domain Proyek
Industri perbankan modern sangat bergantung pada strategi pemasaran yang tepat untuk meningkatkan akuisisi nasabah dan penjualan produk keuangan. Salah satu pendekatan yang umum digunakan adalah kampanye pemasaran langsung (direct marketing), seperti pengiriman email, panggilan telepon, atau surat fisik kepada calon nasabah. Namun, kampanye ini sering kali memiliki tingkat respons yang rendah, sehingga diperlukan pendekatan analitik yang mampu mengidentifikasi target potensial dengan akurasi tinggi.

Machine Learning (ML) memungkinkan analisis data historis kampanye pemasaran bank untuk memprediksi efektivitas suatu kampanye berdasarkan profil pelanggan. Dengan mengolah data seperti umur, pekerjaan, status pernikahan, pendidikan, status pinjaman, dan histori interaksi, model ML dapat mengidentifikasi pola-pola tertentu yang terkait dengan keberhasilan kampanye.

Studi-studi sebelumnya telah menunjukkan bahwa algoritma seperti Decision Tree, Random Forest, dan Logistic Regression cukup efektif dalam memprediksi keberhasilan kampanye pemasaran. Model klasifikasi ini dapat membantu bank dalam menghemat biaya, meningkatkan tingkat konversi, dan merancang strategi pemasaran yang lebih tertarget.

Proyek ini bertujuan untuk membangun model klasifikasi berbasis Machine Learning untuk memprediksi apakah seorang pelanggan akan merespons positif terhadap kampanye pemasaran berdasarkan data historis, serta mengevaluasi model berdasarkan metrik klasifikasi yang relevan.

## Referensi
- [Machine Learning Algorithms](https://www.researchgate.net/publication/363621267_A_Survey_of_Ensemble_Learning_Concepts_Algorithms_Applications_and_Prospects)
- [Predictive Analysis on Bank Marketing Campaign](https://www.academia.edu/80786830/Predictive_Analysis_on_Bank_Marketing_Campaign_using_Machine_Learning_Algorithms)
- [Bank Direct Marketing Campaign Success Prediction](https://www.researchgate.net/publication/385121297_Bank_Direct_Marketing_Campaign_Success_Prediction)

## Business Understanding
Dalam sektor perbankan, kampanye pemasaran langsung sering kali menghasilkan biaya besar dengan tingkat keberhasilan yang rendah. Untuk meningkatkan efektivitasnya, bank memerlukan sistem prediksi yang mampu mengidentifikasi pelanggan yang paling mungkin merespons kampanye. Dengan pendekatan berbasis data historis, kita dapat memanfaatkan machine learning untuk memprediksi respons nasabah, sehingga proses pemasaran menjadi lebih efisien, tertarget, dan hemat biaya.

Bagian laporan ini mencakup:

## Problem Statements
1. Bagaimana memprediksi apakah seorang nasabah akan merespons positif terhadap kampanye pemasaran bank?
2. Fitur-fitur nasabah mana yang paling berpengaruh terhadap keberhasilan kampanye?
3. Algoritma Machine Learning mana yang paling efektif dalam memprediksi keberhasilan kampanye pemasaran?

## Goals
- Membangun model klasifikasi untuk memprediksi respons nasabah terhadap kampanye pemasaran.
- Mengidentifikasi fitur yang paling berkontribusi terhadap keberhasilan kampanye menggunakan metode interpretabilitas model.
- Mengevaluasi dan memilih model terbaik berdasarkan metrik klasifikasi.

## Solution Statements
Untuk menjawab problem statements dan mencapai goals di atas, pendekatan solusi dilakukan melalui tahapan berikut:

1.Menerapkan beberapa algoritma klasifikasi untuk membandingkan performa:
- Support Vector Classifier (SVC): model yang efektif untuk klasifikasi dengan margin maksimal, terutama pada data dengan dimensi tinggi atau distribusi yang kompleks.
- Random Forest Classifier: model ensemble berbasis banyak decision tree yang mampu menangani overfitting dan memberikan hasil prediksi yang stabil.
- K-Nearest Neighbors (KNN) Classifier: algoritma non-parametrik berbasis kemiripan antar data yang cocok untuk klasifikasi berbasis jarak.

2. Hyperparameter Tuning dan Validasi Silang (Cross-Validation):
Melakukan tuning hyperparameter menggunakan Grid Search atau Randomized Search untuk meningkatkan performa model, khususnya pada model SVC dan Random Forest.
Validasi silang dilakukan untuk memastikan bahwa model tidak overfitting terhadap data latih dan mampu melakukan generalisasi pada data baru.

3. Evaluasi menggunakan metrik regresi, yaitu:

- Accuracy: mengukur seberapa banyak prediksi yang benar.
- Precision, Recall, F1-Score: digunakan untuk mengevaluasi performa dalam kondisi distribusi data yang tidak seimbang.
- ROC-AUC Score: digunakan untuk menilai kemampuan model dalam membedakan antara kelas positif dan negatif.

3. Analisis fitur penting:
Untuk model seperti Random Forest, dilakukan analisis feature importance untuk mengetahui fitur mana yang paling berpengaruh.

## Data Understanding
Dataset yang digunakan adalah Bank Marketing Dataset dari UCI Machine Learning Repository. Dataset ini sering digunakan sebagai benchmark dalam penelitian prediksi respons kampanye pemasaran.

Dataset ini terdiri dari 45.211 entri dan 17 kolom, masing-masing baris merepresentasikan satu interaksi nasabah dalam kampanye pemasaran.

## Variabel pada Bank Marketing Dataset:
- age: umur nasabah
- job: pekerjaan
- marital: status pernikahan
- education: tingkat pendidikan
- default: apakah nasabah memiliki kredit macet
- balance: saldo tahunan rata-rata
- housing: apakah memiliki pinjaman rumah
- loan: apakah memiliki pinjaman pribadi
- contact: jenis kontak komunikasi (cellular/telephone)
- day/month: hari dan bulan kontak terakhir
- duration: durasi kontak terakhir dalam detik
- campaign: jumlah kontak selama kampanye ini
- pdays: jumlah hari sejak terakhir kali dihubungi
- previous: jumlah kontak sebelumnya
- poutcome: hasil dari kampanye pemasaran sebelumnya
- y: target label (yes/no) – apakah nasabah menerima tawaran produk ban

## Unvariate dan Bivariate Analisys
Univariate dan bivariate Analysis adalah menganalisis setiap fitur secara terpisah.
## Kategorical
Fitur kategorikal dalam dataset berlian meliputi:
<img width="137" alt="Screenshot 2025-05-22 at 13 07 31" src="https://github.com/user-attachments/assets/baad7ff1-9fab-46ea-b275-4c57f4732b82" />

<img width="1035" alt="Screenshot 2025-05-22 at 13 08 01" src="https://github.com/user-attachments/assets/01a5418d-c043-4bb1-bce1-a41edf58fa30" />
<img width="1037" alt="Screenshot 2025-05-22 at 13 08 09" src="https://github.com/user-attachments/assets/81ae4e6d-99e8-4715-b3f2-73a3a0a604ee" />
<img width="1033" alt="Screenshot 2025-05-22 at 13 12 48" src="https://github.com/user-attachments/assets/2729a510-db62-4d36-b88a-54ff8ab836b2" />
<img width="1026" alt="Screenshot 2025-05-22 at 13 12 57" src="https://github.com/user-attachments/assets/170fd5ef-d6ac-4dee-9a8a-2e7f9550b579" />

# Analisis
- Nasabah yang tidak memiliki pinjaman pribadi, pinjaman perumahan, atau kredit macet memiliki rasio yang lebih tinggi untuk berlangganan deposito berjangka dibandingkan dengan nasabah yang memiliki pinjaman atau kredit macet.
- Pada kolom pendidikan, persentase nasabah yang memiliki deposito berjangka lebih tinggi pada nasabah dengan kategori pendidikan menengah dan tinggi. Hal ini menunjukkan bahwa bank harus lebih fokus pada nasabah dengan kategori tersebut.
- Pada kolom pernikahan, tidak ada pola yang jelas dalam rasio langganan. Namun, bank harus lebih fokus pada nasabah yang sudah menikah dan lajang yang masih berstatus pelajar. Hal ini karena kami mengamati pada grafik sebelumnya bahwa pelajar memiliki rasio langganan yang lebih tinggi pada kolom pekerjaan.
- Pada kolom poutcome, kita dapat melihat dengan jelas bahwa nasabah yang berlangganan deposito berjangka pada kampanye pemasaran sebelumnya memiliki kemungkinan lebih besar untuk berlangganan kembali. Hal ini mengindikasikan peluang keberhasilan yang tinggi dalam menargetkan nasabah ini.

## Numerik
Fitur numerik meliputi: 

<img width="1028" alt="Screenshot 2025-05-22 at 13 32 05" src="https://github.com/user-attachments/assets/ba213a8c-4c1b-4d07-889b-49f67e2fdc77" />
<img width="1030" alt="Screenshot 2025-05-22 at 13 32 23" src="https://github.com/user-attachments/assets/ef190903-6a5f-440e-83d8-e4e8af0c548d" />

# Analisi
- Kolom numerik 'usia', 'saldo', dan 'durasi' miring ke kanan, menunjukkan bahwa mungkin ada beberapa outlier yang ada di data. mereka jauh dari kisaran nilai normal dan dapat secara signifikan mempengaruhi analisis

- Sesuai histogram, ada beberapa nasabah yang berusia di atas 65 tahun dan telah dihubungi untuk deposito berjangka. Hal ini mungkin bukan strategi yang masuk akal karena nasabah ini mungkin tidak memiliki jangka waktu investasi yang cukup panjang untuk mendapatkan keuntungan dari deposito berjangka. kita harus menganalisis rasio nasabah usia tua yang berlangganan dan yang tidak berlangganan.

<img width="1040" alt="Screenshot 2025-05-22 at 13 33 14" src="https://github.com/user-attachments/assets/d3bc181d-9ed2-402a-9326-489a8d3a223c" />

# Analisi
- `Usia:` Dari plot biola, kita dapat mengamati bahwa nasabah dalam **kelompok usia 20 hingga 30** memiliki peluang lebih tinggi untuk berlangganan deposito berjangka. Namun, setelah usia **60+**, rasio nasabah yang berlangganan juga tinggi. Penting untuk dicatat bahwa jumlah nasabah yang dihubungi pada kelompok usia **60+** lebih sedikit, yang dapat menjadi faktor dalam tren yang diamati.
- `Saldo :` Distribusi saldo menunjukkan bahwa nasabah dengan **saldo yang lebih kecil cenderung tidak berlangganan deposito berjangka.
- `Durasi :` Kita dapat melihat bahwa ketika durasi kontak terakhir yang dilakukan dengan nasabah lebih tinggi, ada kemungkinan besar nasabah tersebut berlangganan deposito berjangka.
- `Kampanye :` Dari plot biola, kita dapat mengamati bahwa nasabah yang dihubungi **5 kali atau kurang** selama kampanye pemasaran saat ini memiliki kemungkinan lebih besar untuk berlangganan deposito berjangka.
Pengamatan ini menunjukkan bahwa usia, saldo, durasi, dan kampanye merupakan faktor penting dalam menentukan apakah nasabah akan berlangganan deposito berjangka.

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
| Model               | MSE       | R²   |
|---------------------|-----------|------|
| Linear Regression   | 1.29e+06  | 0.92 |
| Decision Tree       | 7.16e+05  | 0.95 |
| Random Forest       | 4.09e+05  | 0.97 |
| K-Nearest Neighbors | 6.84e+05  | 0.96 |

<img width="752" alt="Screenshot 2025-05-11 at 13 38 26" src="https://github.com/user-attachments/assets/a461aa3d-3f17-4576-b5d4-b3991dc6053c" />
<img width="730" alt="Screenshot 2025-05-11 at 13 38 02" src="https://github.com/user-attachments/assets/004b0af2-8306-4616-9015-ce50333097f1" />

Berdasarkan hasil evaluasi menggunakan metrik  MSE (Mean Squared Error) dan R² Score, dapat disimpulkan bahwa Random Forest Regressor adalah model terbaik untuk memprediksi harga berlian dalam proyek ini. Berikut adalah beberapa poin kesimpulan penting:

Random Forest Regressor memiliki performa terbaik dengan nilai:

- MSE terendah (4.09e+05), yang mengindikasikan bahwa kesalahan prediksi pada model ini lebih kecil dan penalti terhadap kesalahan besar lebih rendah.

- R² Score tertinggi (0.97), yang menunjukkan bahwa model ini dapat menjelaskan 97% dari variabilitas data harga berlian, jauh lebih tinggi dibandingkan model lain.

**---Ini adalah bagian akhir laporan---**
