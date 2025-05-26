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
Dataset yang digunakan adalah Bank Marketing Dataset dari [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/222/bank+marketing). Dataset ini sering digunakan sebagai benchmark dalam penelitian prediksi respons kampanye pemasaran.

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
- y: target label (yes/no) – apakah nasabah menerima tawaran produk bank.

# Data Wrangling
1. 5 Data teratas
<img width="1060" alt="Screenshot 2025-05-23 at 13 13 58" src="https://github.com/user-attachments/assets/39fd526f-1048-4ff5-b60a-705707b7af7e" />


2. Tipe data
<img width="295" alt="Screenshot 2025-05-23 at 13 14 13" src="https://github.com/user-attachments/assets/e10bd35f-71f1-4848-bf71-5f93ac58f299" />


3. Describe all numerical column
<img width="752" alt="Screenshot 2025-05-23 at 13 15 24" src="https://github.com/user-attachments/assets/40bb5dbc-311b-48cb-89c4-702ede57e267" />


# Analisis
- Kolom **pdays** berisi nilai **-1**, yang mengindikasikan bahwa nasabah tertentu tidak dihubungi sebelumnya sebagai bagian dari kampanye pemasaran bank.
- Dataset ini mencakup **sejumlah besar nasabah baru**, yang dibuktikan dengan prevalensi nilai 0 pada kolom sebelumnya, yang menunjukkan bahwa banyak nasabah yang belum pernah dihubungi sebelum kampanye ini.
- Kolom saldo berisi beberapa nilai negatif, yang dapat mengindikasikan bahwa beberapa nasabah tertentu telah melakukan penarikan dana secara berlebihan pada rekening mereka atau memiliki hutang yang belum dibayar. Saldo negatif ini menunjukkan bahwa beberapa nasabah mungkin mengalami kesulitan atau tantangan keuangan.
- Tampaknya terdapat sejumlah kecil outlier pada kolom **saldo** dan **durasi**, seperti yang ditunjukkan oleh kesenjangan yang mencolok antara nilai persentil 99.9% dan nilai maksimum pada kolom-kolom ini. Hal ini menunjukkan bahwa mungkin ada beberapa nilai ekstrem yang membuat distribusi data di kolom-kolom ini miring.


## Unvariate dan Bivariate Analisys
Univariate dan bivariate Analysis adalah menganalisis setiap fitur secara terpisah.
## Kategorical
Fitur kategorikal dalam dataset Bank Marketing meliputi:

<img width="137" alt="Screenshot 2025-05-22 at 13 07 31" src="https://github.com/user-attachments/assets/baad7ff1-9fab-46ea-b275-4c57f4732b82" />

# Unvariate
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

# Analisis
- Kolom numerik 'usia', 'saldo', dan 'durasi' miring ke kanan, menunjukkan bahwa mungkin ada beberapa outlier yang ada di data. mereka jauh dari kisaran nilai normal dan dapat secara signifikan mempengaruhi analisis

- Sesuai histogram, ada beberapa nasabah yang berusia di atas 65 tahun dan telah dihubungi untuk deposito berjangka. Hal ini mungkin bukan strategi yang masuk akal karena nasabah ini mungkin tidak memiliki jangka waktu investasi yang cukup panjang untuk mendapatkan keuntungan dari deposito berjangka. kita harus menganalisis rasio nasabah usia tua yang berlangganan dan yang tidak berlangganan.

<img width="1040" alt="Screenshot 2025-05-22 at 13 33 14" src="https://github.com/user-attachments/assets/d3bc181d-9ed2-402a-9326-489a8d3a223c" />

# Analisis
- `Usia:` Dari plot biola, kita dapat mengamati bahwa nasabah dalam **kelompok usia 20 hingga 30** memiliki peluang lebih tinggi untuk berlangganan deposito berjangka. Namun, setelah usia **60+**, rasio nasabah yang berlangganan juga tinggi. Penting untuk dicatat bahwa jumlah nasabah yang dihubungi pada kelompok usia **60+** lebih sedikit, yang dapat menjadi faktor dalam tren yang diamati.
- `Saldo :` Distribusi saldo menunjukkan bahwa nasabah dengan **saldo yang lebih kecil cenderung tidak berlangganan deposito berjangka.
- `Durasi :` Kita dapat melihat bahwa ketika durasi kontak terakhir yang dilakukan dengan nasabah lebih tinggi, ada kemungkinan besar nasabah tersebut berlangganan deposito berjangka.
- `Kampanye :` Dari plot biola, kita dapat mengamati bahwa nasabah yang dihubungi **5 kali atau kurang** selama kampanye pemasaran saat ini memiliki kemungkinan lebih besar untuk berlangganan deposito berjangka.
Pengamatan ini menunjukkan bahwa usia, saldo, durasi, dan kampanye merupakan faktor penting dalam menentukan apakah nasabah akan berlangganan deposito berjangka.

## Multivariate Analisys
Multivariate Analysis menunjukkan hubungan antara dua atau lebih fitur dalam data.

# job vs credit deafult
<img width="1036" alt="Screenshot 2025-05-23 at 08 23 34" src="https://github.com/user-attachments/assets/b7163d9f-f85d-495d-b014-26f9f13aa345" />
# Analisis
- Berdasarkan analisis sebelumnya, dapat dilihat bahwa nasabah pelajar dan pensiunan memiliki kemungkinan yang lebih tinggi untuk memilih deposito berjangka. Hal ini dapat disebabkan oleh fakta bahwa mereka memiliki jumlah kredit macet yang lebih rendah, serta berpotensi memiliki lebih banyak waktu dan sumber daya yang tersedia untuk mempertimbangkan investasi jangka panjang.
- Selain itu, penting bagi bank untuk fokus pada nasabah dengan kategori pekerjaan tertentu, seperti pekerja kantoran, admin, manajemen, dan jasa. Kategori-kategori ini telah menunjukkan porsi yang signifikan dari nasabah yang berlangganan deposito berjangka.
- Di sisi lain, mungkin bukan strategi yang baik untuk menghubungi nasabah dalam kategori seperti pengusaha, pengangguran, dan wiraswasta karena mereka telah menunjukkan kemungkinan yang lebih rendah untuk berlangganan deposito berjangka. Namun, penting untuk dicatat bahwa mungkin ada faktor lain seperti saldo bank dan status pinjaman yang juga dapat mempengaruhi keputusan nasabah untuk berlangganan.
  
# Day of the month vs term deposit
<img width="1037" alt="Screenshot 2025-05-23 at 08 24 00" src="https://github.com/user-attachments/assets/0f5a7b7b-2a94-4393-be9f-9bf33164be07" />
# Analisis
- Jumlah nasabah yang lebih besar dihubungi pada pertengahan bulan. Namun demikian, rasio deposito berjangka tetap relatif konsisten sepanjang hari dalam satu bulan, kecuali pada hari terakhir (hari ke-30), yang memiliki peluang sedikit lebih tinggi untuk nasabah yang berlangganan deposito berjangka. Oleh karena itu, akan bermanfaat bagi bank untuk lebih fokus pada hari terakhir dalam satu bulan untuk menghubungi nasabah. Hal ini dapat disebabkan oleh berbagai alasan, seperti nasabah lebih bersedia untuk berinvestasi pada akhir bulan ketika mereka memiliki pemahaman yang lebih baik tentang anggaran bulanan mereka, atau bank memiliki penawaran atau insentif yang lebih baik pada akhir bulan untuk mendorong nasabah untuk berinvestasi pada deposito berjangka.

# Korelasi Balnce vs Duration
<img width="1031" alt="Screenshot 2025-05-23 at 08 24 13" src="https://github.com/user-attachments/assets/c649cf54-8863-4097-b9c0-cd42d6837d8a" />
# Analisis
- Dari scatter plot, kita dapat melihat bahwa nasabah dengan saldo bank rendah atau nol lebih sering dihubungi oleh bank. Strategi ini mungkin bukan strategi yang paling efektif karena nasabah dengan saldo rendah memiliki rasio deposito berjangka yang lebih tinggi. Oleh karena itu, bank harus fokus pada nasabah dengan saldo menengah dan tinggi ketika menghubungi mereka untuk meningkatkan kemungkinan hasil yang positif.

## Data Preparation
1. Future Enginering
Feature Engineering adalah proses menciptakan, memilih, dan memodifikasi fitur dalam dataset untuk meningkatkan performa model machine learning.
- # Check Outliers
<img width="1304" alt="Screenshot 2025-05-26 at 19 58 50" src="https://github.com/user-attachments/assets/07a11a1b-406f-41a2-8169-6660f7b2649f" />
# Analisis
- Dalam skenario ini, tidak disarankan untuk menghapus pencilan dari dataset karena mengandung informasi yang berharga. Sebagai contoh, pada kolom saldo bank, beberapa nasabah memiliki saldo yang tinggi sementara beberapa lainnya memiliki saldo yang tidak positif. Jika kita menghapus pencilan ini, model kita tidak akan memiliki informasi yang cukup untuk membuat prediksi yang akurat, dan ada risiko overfitting.

- Demikian pula, untuk kolom usia, terdapat pencilan dalam dataset, tetapi kita perlu melatih model kita untuk membuat prediksi berdasarkan semua faktor yang tersedia. Jika kita menghapus pencilan, kita mungkin akan kehilangan informasi penting yang dapat mempengaruhi akurasi model kita. Oleh karena itu, penting untuk menjaga outlier dalam dataset dan menggunakan teknik yang tepat untuk menanganinya selama pelatihan model. di sini tidak ada masalah karena kami menggunakan algoritma yang kuat.

- # Pembuatan column baru untuk kategori job serta explorasi dengan deposit
  cat_1 = ['retired','student'], cat_2 = ['blue-collar','management','technician','admin.','services'], cat_3 = ['unemployed','housemaid','unknown'], cat_4 = ['self-employed','entrepreneur']
<img width="1164" alt="Screenshot 2025-05-26 at 20 01 16" src="https://github.com/user-attachments/assets/1456ef36-d5ec-47a8-8b56-6575e35072bb" />
<img width="1308" alt="Screenshot 2025-05-26 at 20 02 04" src="https://github.com/user-attachments/assets/4d574790-218f-442a-8aa1-fe769b465f53" />
# Analisis
- kami mengamati bahwa kategori 1 dan 2 memiliki rasio langganan deposito berjangka yang tinggi. Namun, kami melihat bahwa bank lebih banyak menghubungi nasabah kategori 2 dibandingkan dengan kategori 1. Hal ini menunjukkan bahwa bank harus lebih fokus pada nasabah kategori 2, tetapi pada saat yang sama, bank juga tidak boleh mengabaikan nasabah kategori 1, karena meskipun jumlah nasabahnya lebih sedikit, namun rasio nasabah yang berlangganan masih tinggi. Bank harus mencoba untuk mencapai keseimbangan antara kedua kategori ini dan mengalokasikan sumber daya mereka secara tepat untuk memaksimalkan tingkat berlangganan mereka.

- # Pembuatan column baru untuk kategori age serta explorasi dengan deposit dan scaterr plot dengan durasi
< 30	'struggling'; 30–49	'stable'; 50–59	'about to retire'; 60–74	'old age'; ≥ 75	'counting a last breathe'.
<img width="1255" alt="Screenshot 2025-05-26 at 20 05 37" src="https://github.com/user-attachments/assets/f00786d5-764a-4f7c-991e-0dc47926eb9f" />
<img width="1302" alt="Screenshot 2025-05-26 at 20 05 44" src="https://github.com/user-attachments/assets/b4e8deee-1961-441a-8046-c71e82616446" />
<img width="1305" alt="Screenshot 2025-05-26 at 20 07 07" src="https://github.com/user-attachments/assets/1d4a7517-1555-442c-93b5-9c37312f323c" />

# Analisis
- bank harus lebih fokus pada kategori yang sedang berjuang dan akan pensiun juga
- Kesimpulan Dari scatterplot di atas dapat disimpulkan bahwa ketika kategori usia old_age dan stabil maka durasi komunikasi lebih banyak dan ketika durasi tinggi maka kemungkinan besar klien akan berlangganan deposito berjangka. Dari scatterplot di atas kita dapat menyimpulkan bahwa ketika durasi kontak dari 300 hingga 2000 di kolom stabil, berjuang, akan pensiun dan saldo klien berada di kisaran tengah 500-35000 maka klien tersebut sebagian besar berlangganan deposito berjangka.
  
- # Ubah kolom y ke term_deposit dan menghapus kolom tidak relevan
<img width="1326" alt="Screenshot 2025-05-26 at 20 08 46" src="https://github.com/user-attachments/assets/1d6bbf90-da71-4120-825c-1bbecdd55983" />
- Kolom 'pdays' dan 'duration' telah dihapus dari dataset karena tidak relevan untuk membangun model prediktif untuk pelanggan baru. 'duration' mewakili durasi kontak terakhir dengan pelanggan di kampanye sebelumnya, dan 'pdays' mewakili jumlah hari yang telah berlalu sejak pelanggan terakhir kali dihubungi. Karena kami sedang membangun model untuk pelanggan baru, informasi ini tidak tersedia untuk mereka. Oleh karena itu, menghapus kolom ini akan mencegah bias atau overfitting yang mungkin terjadi akibat penggunaan data yang tidak relevan atau tidak tersedia.
- # Korelasi Numeric
<img width="1174" alt="Screenshot 2025-05-26 at 20 10 15" src="https://github.com/user-attachments/assets/dadf0bb5-9127-44fb-b858-d0930dced157" />
# Analisis
- tidak ada multikolinearitas yang signifikan antara variabel-variabel independen. Oleh karena itu, kita dapat menyimpulkan bahwa model tersebut robust dan variabel independen cocok untuk memprediksi variabel dependen.

2. Encoding Categorical Columns
Encoding categorical columns adalah proses mengubah data kategorikal ('job', 'marital', 'education', 'default', 'housing', 'loan', 'contact', 'month','poutcome', 'y') menjadi format numerik agar dapat diproses oleh algoritma machine learning. Sebagian besar model machine learning hanya bisa menerima data numerik, sehingga data kategorikal perlu diubah terlebih dahulu.

3. Splitting Dependent and Independent Variables
Pada tahap ini, dataset dibagi menjadi dua bagian:

X (fitur/variabel independen): Berisi seluruh kolom kecuali target, digunakan untuk memprediksi.
y (variabel dependen/target): Berisi label/kolom target yang ingin diprediksi, yaitu status berlangganan deposito berjangka.
📌 Hasil pembagian:

X shape: (44709, 35) → 44.709 baris dan 35 fitur.
y shape: (44709,) → 44.709 label.

4. SMOTE Oversampling for handling class imbalance
Distribusi kelas pada dataset awal sangat tidak seimbang, yang dapat menyebabkan model bias terhadap kelas mayoritas.

Untuk menangani hal ini, digunakan metode SMOTE (Synthetic Minority Over-sampling Technique), yaitu teknik oversampling yang membuat sampel sintetis pada kelas minoritas agar jumlahnya seimbang dengan kelas mayoritas.
📌 Hasil oversampling:
Original dataset length: 44.709
Resampled dataset length (setelah SMOTE): 79.844
Dengan SMOTE, model menjadi lebih adil dalam mempelajari pola dari kedua kelas, sehingga performa prediksi terhadap kelas minoritas meningkat.

5. Train, Test and Split
Setelah dilakukan SMOTE oversampling, dataset dibagi menjadi dua bagian dengan proporsi sekitar 80:20.:
Training set (X_train, y_train): Digunakan untuk melatih model.
Test set (X_test, y_test): Digunakan untuk mengevaluasi performa model pada data yang belum pernah dilihat sebelumnya.
📌 Hasil pembagian:
X_train: (63.875, 35)
X_test: (15.969, 35)
y_train: (63.875,)
y_test: (15.969,)

6. Standarisasi
Standarisasi adalah proses mengubah skala fitur agar memiliki mean = 0 dan standard deviation = 1. Hal ini penting untuk algoritma berbasis jarak atau probabilitas, seperti:
K-Nearest Neighbors (KNN), Naive Bayes, Logistic Regression, Support Vector Machine (SVM)

## Modeling

Untuk menyelesaikan permasalahan prediksi Bank Marketing Effectiveness, proyek ini menggunakan 3 algoritma Machine Learning: Support Vector Machine (SVM), Random Forest Regressor, dan K-Nearest Neighbors Regressor (KNN). Tujuan utamanya adalah memilih model terbaik berdasarkan performa prediksi terhadap efektivitas marketing, dengan mempertimbangkan akurasi serta kompleksitas model.

1. Support Vector Machine (SVM)
SVM mencari hyperplane terbaik yang memisahkan kelas dengan margin terbesar di ruang fitur. Dengan kernel trick, SVM dapat menangani data non-linear dan kompleks.
- Library: sklearn.svm.SVC
- **Kelebihan:**
- Efektif pada data dengan dimensi tinggi dan kompleksitas non-linear.
- Tahan terhadap overfitting dengan pengaturan parameter yang tepat.
- **Kekurangan:**
- Lambat pada dataset besar karena komputasi kernel yang mahal.
- Perlu data yang sudah distandarisasi agar performa optimal.
- Sulit diinterpretasi.

2. Random Forest Classifier (RF)
Random Forest adalah ensemble learning berbasis banyak Decision Tree, menggunakan voting mayoritas untuk klasifikasi. Algoritma ini kuat menangani fitur kompleks, interaksi non-linear, dan data dengan skala berbeda.
- Library: sklearn.ensemble.RandomForestClassifier
- **Kelebihan:**
- Akurat dan stabil, mengurangi risiko overfitting dibanding Decision Tree tunggal.
- Tidak membutuhkan standarisasi fitur.
- Mampu menangani data yang besar dan fitur yang beragam.
- **Kekurangan:**
- Model kurang mudah diinterpretasi (black-box).
- Memerlukan waktu pelatihan lebih lama daripada model sederhana.

3. K-Nearest Neighbors (KNN)
KNN mengklasifikasikan data berdasarkan mayoritas kelas dari k tetangga terdekat di ruang fitur. Jarak antar data menentukan siapa tetangga terdekat.
- Library: sklearn.neighbors.KNeighborsClassifier
- **Kelebihan:**
- Konsep sederhana dan intuitif.
- Tidak perlu pelatihan model secara eksplisit (lazy learner).
- **Kekurangan:**
- Lambat pada dataset besar karena harus menghitung jarak ke semua titik.
- Sensitif terhadap fitur yang tidak dinormalisasi (perlu scaling).
- Kurang efektif jika data sangat berdimensi tinggi.

## Evaluation
Pada bagian ini, dilakukan evaluasi untuk menilai kinerja masing-masing model klasifikasi yang telah dibangun dalam memprediksi apakah nasabah akan berlangganan deposito berjangka atau tidak. Proyek ini menggunakan beberapa metrik evaluasi utama yang sesuai dengan masalah klasifikasi biner, yaitu Accuracy, Precision, Recall, dan F1-Score.
- Metrik Evaluasi yang Digunakan
**- Accuracy**
Mengukur proporsi prediksi yang benar dari seluruh data. Nilai Accuracy = 1 berarti semua prediksi benar. Namun, metrik ini bisa menyesatkan jika kelas tidak seimbang.
**- Precision**
Mengukur proporsi prediksi positif yang benar-benar positif (true positive dibanding total prediksi positif). Precision tinggi menunjukkan sedikit false positive. Penting ketika konsekuensi salah prediksi positif cukup besar.
**- Recall (Sensitivity)**
Mengukur proporsi data positif yang berhasil dideteksi oleh model. Recall tinggi berarti sedikit false negative. Penting ketika ingin meminimalisir melewatkan kasus positif.
**- F1-Score**
Merupakan harmonisasi dari precision dan recall, memberikan nilai tunggal untuk menyeimbangkan keduanya. Cocok dipakai jika ingin keseimbangan antara precision dan recall.

2. Hasil Evaluasi Model

# Hasil Evaluasi
| Model                 | Accuracy  | Precision | Recall | F1-Score |
|-----------------------|-----------|-----------|--------|----------|
| Support Vector Machine|   0.94    |   0.94    |  0.94  |   0.94   |
| Random Forest         |   0.94    |   0.94    |  0.94  |   0.94   |
| K-Nearest Neighbors   |   0.93    |   0.93    |  0.93  |   0.93   |

<img width="685" alt="Screenshot 2025-05-23 at 14 10 46" src="https://github.com/user-attachments/assets/22819545-ceb9-4a99-b967-d11027fd5ea6" />

- Tiga algoritma yang berbeda digunakan untuk memecahkan masalah ini. Berbagai hasil telah dibandingkan pada akhir setiap model train. Sebuah plot digunakan untuk membandingkan kurva ROC dan skor auc. Skor recall digunakan sebagai salah satu matriks performa.

## why recall? ## 
- Ini adalah masalah pemasaran yang melibatkan sumber daya yang signifikan, sehingga sangat penting untuk mengoptimalkan hasil dan menghemat sumber daya. Variabel targetnya adalah **Deposito Berjangka**, yang mengindikasikan apakah calon nasabah mengatakan **ya atau tidak** untuk berlangganan deposito berjangka setelah panggilan telepon. Untuk menghemat waktu dan tenaga, tujuannya adalah untuk fokus pada klien yang memiliki probabilitas lebih tinggi untuk berlangganan deposito berjangka. Tujuannya adalah untuk memprediksi sebanyak mungkin **positif yang benar (Untuk Kelas Ya (1)) ** dari kumpulan data, **membuat skor penarikan menjadi metrik kinerja yang penting**.

- Jadi, di sini kita lebih tertarik untuk memprediksi dengan benar nasabah yang mengatakan ya pada deposito berjangka. proporsi positif aktual (Ya) yang diklasifikasikan dengan benar oleh model. Dalam kasus kami, nilai recall yang tinggi untuk Ya berarti bahwa kami mengidentifikasi dengan benar nasabah yang lebih mungkin untuk berlangganan deposito berjangka. jadi, **kita perlu lebih fokus pada nilai recall Ya (1)** dan kemudian ketepatan, F1-Score, dan juga nilai AUC.

## Kesimpulan ##

- Setelah mengevaluasi kinerja berbagai algoritma machine learning pada dataset yang diberikan, ditemukan bahwa Random Forest Classifier mengungguli algoritma lain seperti KNN dan SVM. Hyperparameter dari Random Forest Classifier disetel menggunakan GridSearchCV untuk menemukan kombinasi parameter terbaik untuk kinerja yang optimal.

- Skor validasi silang untuk Random Forest Classifier ditemukan sebesar 0,94, yang menunjukkan bahwa model menggeneralisasi dengan baik untuk data yang tidak terlihat. Skor akurasi untuk data uji adalah 0,94, yang merupakan indikasi yang baik dari kemampuan model untuk berkinerja baik pada data baru yang tidak terlihat. Selain itu, nilai akurasi untuk data latih adalah 0,97, yang mengindikasikan bahwa model tidak terlalu cocok dengan data latih.

- Selain itu, Random Forest Classifier mencapai skor recall 0,91 dan skor F1 0,94, yang sedikit lebih baik daripada skor yang sesuai untuk KNN dan SVM. Oleh karena itu, berdasarkan metrik evaluasi dan hasil kinerja, dapat disimpulkan bahwa **Random Forest Classifier** adalah algoritma yang cocok untuk masalah ini.

- Dengan menggunakan hasil ini, bank dapat secara khusus menargetkan klien dan mendapatkan kesuksesan yang lebih tinggi dalam usaha mereka. Menghemat banyak waktu dengan tidak berfokus pada nasabah yang memiliki probabilitas lebih rendah adalah keuntungan lain dari proyek ini.
**---Ini adalah bagian akhir laporan---**
