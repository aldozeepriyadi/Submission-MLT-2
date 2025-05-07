# Laporan Proyek Machine Learning - Sistem Rekomendasi Game Steam - Aldo Fernando Supriyadi
![dataset-cover](https://github.com/user-attachments/assets/6e2ee81c-bd38-483f-884b-d28aff8ddcc9)

## Domain Proyek

Layanan distribusi game seperti **Steam** telah menjadi salah satu platform terkemuka dalam industri game digital. Dengan lebih dari **120 juta pengguna aktif bulanan**, Steam menawarkan lebih dari **50.000 game** yang dapat dibeli dan diunduh oleh penggunanya dari berbagai genre, termasuk aksi, petualangan, RPG, simulasi, dan banyak lagi. Steam juga menyediakan berbagai fitur seperti **multiplayer online**, **community hub**, dan **game modding**, yang membuatnya menjadi platform yang sangat menarik bagi para gamer di seluruh dunia.

Dalam konteks bisnis, sistem rekomendasi game yang efektif memegang peranan penting dalam menarik dan mempertahankan pengguna. Steam, sebagai platform distribusi game terbesar, menggunakan algoritma rekomendasi canggih untuk menyarankan game yang relevan kepada penggunanya, berdasarkan berbagai faktor seperti genre, rating, preferensi individu, serta ulasan dari pengguna lain. Memberikan rekomendasi yang akurat dan relevan sangat penting untuk meningkatkan pengalaman pengguna, memperpanjang waktu yang dihabiskan pengguna di platform, serta meningkatkan loyalitas pengguna. Oleh karena itu, sistem rekomendasi menjadi bagian penting dalam meningkatkan kepuasan pengguna dan mempengaruhi tingkat retensi serta engagement yang lebih tinggi [1].

Sistem rekomendasi game juga memberi kesempatan bagi pengguna untuk menemukan game baru yang mungkin tidak mereka temui tanpa adanya dukungan algoritma berbasis kecerdasan buatan. Dalam dunia game digital, ini sangat penting karena membantu pengguna memperluas pilihan game mereka dan juga memungkinkan pengembang game untuk lebih mudah ditemukan oleh audiens baru. Selain itu, sistem rekomendasi yang efektif berpengaruh langsung terhadap pendapatan dan strategi bisnis Steam, baik melalui penjualan langsung game atau model freemium yang melibatkan fitur tambahan berbayar [2].

Steam juga dapat memanfaatkan sistem rekomendasi untuk mengembangkan model bisnis berbasis data yang lebih baik. Dengan lebih banyak data pengguna yang dianalisis secara real-time, Steam dapat memperkaya pengalaman pengguna dan memberikan dampak positif pada **strategi pemasaran** serta **peningkatan engagement** pengguna. Hal ini pada akhirnya dapat membantu Steam dalam meningkatkan **customer lifetime value (CLTV)**, yang merupakan salah satu indikator utama dalam kesuksesan platform distribusi game digital.

## Business Understanding

Pengembangan model rekomendasi game yang akurat memiliki potensi besar dalam memberikan manfaat nyata bagi berbagai pemangku kepentingan di industri hiburan dan distribusi game digital. Penerapan sistem rekomendasi berbasis **Collaborative Filtering** yang efektif dapat membantu platform distribusi game seperti **Steam** dalam meningkatkan pengalaman pengguna, serta memaksimalkan retensi dan kepuasan pelanggan.

Manfaat utama dari model ini adalah **peningkatan pengalaman pengguna** melalui rekomendasi game yang lebih relevan dan dipersonalisasi, yang dapat meningkatkan waktu yang dihabiskan oleh pengguna di platform. Dengan memberikan saran game yang sesuai dengan preferensi individu, platform dapat memperbaiki **loyalitas pelanggan** dan **engagement** pengguna.

Bagi pengembang game, sistem rekomendasi ini dapat membantu dalam **penemuan game baru** oleh pengguna yang mungkin tidak akan menemukannya tanpa adanya dukungan algoritma berbasis kecerdasan buatan. Selain itu, platform juga dapat memaksimalkan pendapatan melalui model **freemium** atau **berlangganan berbayar** dengan meningkatkan keterlibatan dan minat pengguna terhadap lebih banyak game.

Dengan sistem rekomendasi yang lebih baik, Steam dapat memanfaatkan data pengguna untuk **strategi pemasaran yang lebih efektif** dan meningkatkan **customer lifetime value (CLTV)**, yang menjadi indikator utama keberhasilan dalam industri distribusi game digital.

### Problem Statements

Berdasarkan tujuan yang telah dipaparkan, berikut adalah masalah utama yang ingin diselesaikan dalam proyek ini:

1. **Bagaimana membangun model rekomendasi game yang akurat** yang dapat memprediksi game yang relevan dan sesuai dengan preferensi setiap pengguna, dengan memanfaatkan data historis seperti rating game, genre, dan interaksi sebelumnya antara pengguna dan game.
  
2. **Bagaimana mengukur kinerja model rekomendasi** dengan menggunakan metrik evaluasi yang tepat, seperti **Mean Squared Error (MSE)**, **Mean Absolute Error (MAE)**, dan **Hit Rate**, untuk memastikan model dapat memberikan rekomendasi yang efektif dan relevan bagi pengguna.
  
3. **Bagaimana mengintegrasikan model ini dalam sistem rekomendasi Steam** untuk memaksimalkan pendapatan melalui peningkatan keterlibatan pengguna, serta membantu pengembang game untuk lebih mudah ditemukan oleh audiens yang relevan.

### Goals

Tujuan dari proyek ini adalah untuk:
1. **Membangun model rekomendasi berbasis machine learning** yang dapat memproses data historis interaksi pengguna dengan game, termasuk rating, genre, dan metadata game untuk memprediksi game yang relevan bagi pengguna.
  
2. **Mengevaluasi performa model** menggunakan metrik yang relevan seperti **Mean Squared Error (MSE)**, **Mean Absolute Error (MAE)**, dan **Hit Rate** untuk memastikan akurasi dan efektivitasnya dalam memberikan rekomendasi yang sesuai dengan preferensi pengguna.

3. **Menyediakan solusi berbasis data** yang dapat digunakan untuk meningkatkan pengalaman pengguna di platform seperti **Steam**, memperpanjang waktu yang dihabiskan oleh pengguna, dan membantu pengembang game untuk menjangkau audiens yang lebih luas.

### Solution Statements

Beberapa langkah yang akan diambil untuk mencapai tujuan proyek ini adalah:

1. **Eksplorasi Data (EDA):** Melakukan analisis awal pada dataset untuk memahami distribusi variabel, seperti rating pengguna, genre game, dan interaksi antar pengguna dengan game. Hal ini juga termasuk analisis hubungan antara fitur-fitur seperti genre, harga, dan rating dengan game yang direkomendasikan.

2. **Pembersihan dan Preprocessing Data:** Menangani **missing values**, **duplikasi data**, dan **normalisasi fitur** seperti ID pengguna dan ID game agar model dapat berfungsi dengan baik. Fitur-fitur penting yang digunakan untuk rekomendasi termasuk **rating pengguna**, **genre game**, dan **metadata game** (seperti harga, tag, dll.). Encoding dilakukan pada kolom **user_id** dan **app_id** untuk memudahkan proses model.

3. **Pengembangan Model:** Menggunakan algoritma machine learning berbasis **Collaborative Filtering** seperti **Matrix Factorization**, **K-Nearest Neighbors (KNN)**, atau **Neural Networks** untuk membangun model prediksi rekomendasi game. Pendekatan ini akan fokus pada interaksi antara pengguna dan game untuk menghasilkan rekomendasi yang relevan.

4. **Evaluasi Model:** Menggunakan metrik evaluasi seperti **Mean Squared Error (MSE)**, **Mean Absolute Error (MAE)**, dan **Hit Rate** untuk mengevaluasi akurasi model dalam memberikan rekomendasi game yang sesuai. Metrik ini akan digunakan untuk membandingkan performa antara berbagai model dan memilih model terbaik yang menghasilkan rekomendasi yang lebih baik.

## Data Understanding

### Deskripsi Variabel

#### **Informasi Datasets**

| Jenis   | Keterangan |
| ------- | ---------- |
| **Judul** | _Game Recommendations and User Reviews_ |
| **Sumber data** | [Steam Game Recommendations Dataset](https://www.kaggle.com/datasets/antonkozyriev/game-recommendations-on-steam/data) |
| **Pembuat** | [Anton Kozyriev](https://www.kaggle.com/antonkozyriev) |
| **Lisensi** | Public |
| **Visibilitas** | Publik |
| **Tags** | _Gaming, Steam, Recommendations, User Reviews, Data Science, Machine Learning_ |

Dataset ini berisi **50,872** entri dengan **13 kolom** yang berisi berbagai informasi terkait dengan game yang ada di platform Steam, termasuk informasi tentang rating game, user reviews, harga, serta rekomendasi dari pengguna lain.

**Data ini dikumpulkan dari platform Steam dan tersedia di Kaggle untuk analisis lebih lanjut.**

#### **Kondisi Dataset**
- Dataset terdiri dari **50,872 baris** dan **13 kolom** dengan informasi tentang game, rating, harga, dan review dari pengguna.
- Pada dataset ini tidak ada data yang duplikasi dan tidak mengalami missing value.
- **Tidak ada missing value** di seluruh kolom dataset.


#### **Deskripsi Kolom:**

##### **games_metadata_df**
- **app_id**: ID unik untuk setiap game di platform Steam.
- **description**: Deskripsi singkat tentang game, mencakup fitur, gameplay, dan konten yang tersedia.
- **tags**: Kategori atau tag yang menggambarkan genre atau elemen permainan dari game, seperti "Action", "Adventure", atau "Multiplayer".

##### **game_df**
- **app_id**: ID unik untuk setiap game di platform Steam, menghubungkan game dengan informasi lainnya.
- **title**: Nama dari game yang terdaftar di Steam.
- **date_release**: Tanggal rilis game di Steam.
- **win**: Menunjukkan apakah game tersedia untuk sistem operasi Windows.
- **mac**: Menunjukkan apakah game tersedia untuk sistem operasi macOS.
- **linux**: Menunjukkan apakah game tersedia untuk sistem operasi Linux.
- **rating**: Rating yang diberikan oleh pengguna untuk game, sering kali berupa teks yang menunjukkan kualitas game (misalnya, "Very Positive", "Positive").
- **positive_ratio**: Rasio persentase review positif terhadap total review yang diterima oleh game.
- **user_reviews**: Jumlah total review yang diberikan oleh pengguna untuk game.
- **price_final**: Harga final game yang tersedia untuk dibeli, setelah diskon atau penawaran khusus.
- **price_original**: Harga asli game sebelum diskon atau penawaran khusus.
- **discount**: Persentase diskon yang diterapkan pada harga game.
- **steam_deck**: Menunjukkan apakah game kompatibel dengan perangkat Steam Deck.

##### **user_df**
- **user_id**: ID unik yang mengidentifikasi setiap pengguna Steam.
- **products**: ID produk yang dibeli atau diinteraksikan oleh pengguna.
- **reviews**: Jumlah review yang diberikan oleh pengguna di platform Steam.

##### **recommend_df**
- **app_id**: ID unik game yang direkomendasikan kepada pengguna.
- **helpful**: Jumlah pengguna yang menandai review sebagai "membantu" untuk game tertentu.
- **funny**: Jumlah pengguna yang menandai review sebagai "lucuk" untuk game tertentu.
- **date**: Tanggal dan waktu saat review dilakukan atau ketika rekomendasi diberikan.
- **is_recommended**: Menunjukkan apakah pengguna merekomendasikan game (True/False).
- **hours**: Jumlah jam yang dihabiskan oleh pengguna untuk bermain game yang direkomendasikan.
- **user_id**: ID pengguna yang memberikan review atau rekomendasi.
- **review_id**: ID unik yang mengidentifikasi setiap review pada game tertentu.



### Pengecekan Missing Value, Data Duplikat dan Tipe Data

Pada tahap ini, dilakukan pengecekan untuk memastikan bahwa tidak ada nilai yang hilang (`missing value`) atau data yang berulang (`duplicated data`). Pengecekan tipe data juga dilakukan untuk memastikan bahwa semua kolom memiliki tipe data yang sesuai dengan jenis informasi yang terkandung dalam setiap kolom.

#### **Pengecekan Missing Values dan Duplikasi Data**

Pengecekan dilakukan untuk melihat apakah ada nilai yang hilang dalam dataset. Berdasarkan hasil pengecekan, dapat disimpulkan bahwa **semua kolom dalam dataset memiliki nilai yang lengkap**, yang berarti tidak ditemukan missing values pada dataset ini.

Selain itu, dilakukan pengecekan untuk data duplikat. Hasil pengecekan menunjukkan bahwa tidak ada data yang terduplikasi pada dataset. 

#### **Pengecekan Tipe Data**

Saat memeriksa tipe data dataset, ditemukan bahwa semua kolom memiliki tipe data yang sesuai. Berikut adalah tipe data untuk setiap dataset:

1. **`game_df`**
   - **Jumlah Baris**: 50,872
   - **Tipe Data**:
     - `app_id`: integer
     - `title`: object (string)
     - `rating`: object (string)
     - `positive_ratio`: integer
     - `user_reviews`: integer
     - `price_final`: float
     - `price_original`: float
     - `discount`: float
     - `steam_deck`: boolean

2. **`users_df`**
   - **Jumlah Baris**: 14,306,064
   - **Tipe Data**:
     - `user_id`: integer
     - `products`: integer
     - `reviews`: integer

3. **`recommend_df`**
   - **Jumlah Baris**: 41,154,794
   - **Tipe Data**:
     - `app_id`: integer
     - `helpful`: integer
     - `funny`: integer
     - `date`: object (string)
     - `is_recommended`: boolean
     - `hours`: float
     - `user_id`: integer
     - `review_id`: integer

4. **`games_metadata_df`**
   - **Jumlah Baris**: 50,872
   - **Tipe Data**:
     - `app_id`: integer
     - `description`: object (string)
     - `tags`: object (list of strings)

Dari hasil pengecekan ini, diketahui bahwa beberapa kolom bertipe `object` pada dataset `game_df` seperti `rating`, perlu dikonversi menjadi tipe data yang tepat (misalnya `float` atau `integer`) untuk analisis lebih lanjut.

---
### EDA - Univariate Analysis

Untuk analisis univariate pada kolom numerik, digunakan dua jenis visualisasi yaitu **Histogram** dan **Violin Plot** untuk mengeksplorasi distribusi data dan menemukan pola yang ada pada setiap fitur.

- **Histogram** digunakan untuk melihat distribusi frekuensi dari kolom numerik, apakah terdistribusi normal, skewed, atau distribusi lainnya.

<img width="auto" alt="Gambar1" src="https://github.com/user-attachments/assets/21b80875-77dd-4a1b-87a6-cde59edc43fa" />

**Insight yang didapatkan dari Gambar 1:**
- **Rating positif** pada dataset ini lebih terdistribusi pada rentang **70-90**, yang menunjukkan sebagian besar game mendapatkan ulasan yang cukup baik dari pengguna. Rentang **90-100** juga cukup besar, menandakan sejumlah game yang sangat diterima oleh pemain.
- Rentang **30-50** dan **10-30** relatif lebih sedikit, menunjukkan bahwa ada sedikit game dengan rating yang sangat rendah.

- **Violin Plot** digunakan untuk menggambarkan distribusi dan variabilitas data numerik. Di bawah ini adalah visualisasi **Jumlah Game per Genre** yang menggambarkan variabilitas genre-game yang ada dalam dataset.

<img width="auto" alt="Gambar2" src="https://github.com/user-attachments/assets/442bf4ce-4da7-4bb0-a6cd-276d3a26d918" />


**Insight yang didapatkan dari Gambar 2:**
- **Indie** adalah genre yang paling banyak ditemukan di Steam, dengan lebih dari **25.000 game**, menunjukkan bahwa genre ini mendominasi platform tersebut.
- Genre **Singleplayer** dan **Action** mencatatkan angka lebih dari **20.000 game**, yang mencerminkan popularitas genre yang berfokus pada pengalaman pemain tunggal dan aksi.
- Genre **RPG**, **Simulation**, dan **2D** juga memiliki jumlah game yang signifikan, meskipun lebih sedikit dibandingkan dengan genre lainnya seperti **Indie** dan **Singleplayer**.

Distribusi ini menunjukkan bahwa Steam memiliki variasi besar dalam genre yang ditawarkan kepada penggunanya, dengan genre **Indie** dan **Singleplayer** yang sangat dominan, sementara genre **RPG** dan **2D** juga cukup populer meskipun tidak sebanyak genre lainnya.



## Data Preparation

Dalam tahap persiapan data ini, kita melakukan beberapa pembersihan pada dataset **games_metadata_df** yang berisi informasi tentang metadata permainan. Berikut adalah langkah-langkah yang dilakukan:

### **Mengganti Nilai Kosong di Kolom 'Description'**  
   Nilai kosong atau NaN pada kolom `description` diganti dengan string `'No Description'`.

###  **Mengganti Array Kosong di Kolom 'Tags'**  
   Array kosong pada kolom `tags` diganti dengan `None` atau list kosong.

### **Menghapus Baris dengan NaN di Kolom 'Tags' dan 'Description'**  
   Setelah mengganti nilai kosong, baris yang masih mengandung NaN pada kolom `tags` dan `description` dihapus.

### Proses Pemilihan Fitur:

1. **Pemilihan Kolom yang Relevan:**
   - Dari `game_df`, kolom yang dipilih adalah:
     - `app_id`: ID dari setiap game
     - `title`: Judul game
     - `positive_ratio`: Rasio penilaian positif
   - Dari `games_metadata_df`, hanya kolom:
     - `app_id`: ID game yang sesuai
     - `tags`: Kategori atau tag terkait game tersebut

2. **Penggabungan Data:**
   Setelah memilih kolom-kolom tersebut, langkah selanjutnya adalah menggabungkan kedua DataFrame berdasarkan kolom `app_id`. Ini dilakukan untuk mendapatkan satu DataFrame yang memiliki informasi tentang ID game, judul, rasio penilaian, dan tag sekaligus.

   Penggabungan ini menggunakan metode `inner join`, yang memastikan hanya game yang memiliki data di kedua DataFrame yang akan digabungkan. Hasilnya adalah DataFrame yang lebih fokus pada informasi penting saja.

3. **Hasil Penggabungan:**
   Setelah proses penggabungan selesai, DataFrame `df_games_rating` akan berisi:
   - `app_id`: ID game yang unik
   - `title`: Nama game
   - `positive_ratio`: Rasio penilaian positif
   - `tags`: Kategori atau tag yang relevan dengan game tersebut.


#### Contoh Hasil:
Misalnya, setelah penggabungan, DataFrame yang dihasilkan akan terlihat seperti ini:

| app_id | title                      | positive_ratio | tags                             |
|--------|----------------------------|----------------|----------------------------------|
| 13500  | Prince of Persia: The Sands of Time | 100           | [Action, Adventure, Parkour]     |
| 22364  | Game Title Example 2        | 50          | [Action]                         |
| 113020 | Monaco: What's Yours Is Mine | 30          | [Co-op, Stealth, Indie, Heist]  |
### Content-Based Filtering - Data Preparation

1. Pemilihan Fitur Utama

Pada tahap persiapan data untuk **Content-Based Filtering**, fitur-fitur utama yang dipilih adalah:

- **`app_id`**: ID unik untuk setiap game.
- **`title`**: Nama dari game.
- **`positive_ratio`**: Rasio ulasan positif yang diterima oleh setiap game.
- **`tags`**: Tag yang menggambarkan genre atau kategori dari game, seperti "Action", "Adventure", dll.

2. Penggabungan Data

Data dari dua sumber yang berbeda digabungkan berdasarkan **`app_id`** untuk mendapatkan informasi lengkap tentang setiap game. Gabungan ini menghasilkan sebuah dataframe yang memuat data seperti **rasio ulasan positif** dan **tag** untuk masing-masing game.

3. Transformasi Data

Untuk mempersiapkan data bagi model **Content-Based Filtering**, berikut adalah langkah-langkah yang dilakukan:

- Inisiasi objek TF-IDF Vectorizer dari sklearn
Pertama, objek `TfidfVectorizer` digunakan untuk mentransformasikan kolom **`tags`** yang berisi genre game menjadi matriks TF-IDF. Proses ini akan mengubah teks genre menjadi representasi numerik yang dapat digunakan dalam model pembelajaran mesin.

```python
from sklearn.feature_extraction.text import TfidfVectorizer

# Inisiasi objek TF-IDF Vectorizer
vectorizer = TfidfVectorizer()

# Transformasi teks genre menjadi matriks TF-IDF
tf_idf_matrix = vectorizer.fit_transform(df_games_rating_cbf['tags'])
```
- Menampilkan fitur/genre unik yang dihasilkan oleh TF-IDF setelah proses token

Setelah proses transformasi, kita dapat melihat fitur unik (genre) yang dihasilkan oleh TF-IDF. Ini akan memberikan informasi tentang genre yang ada dalam dataset, yang digunakan dalam rekomendasi berbasis konten.

```python
# Menampilkan fitur/genre unik yang dihasilkan oleh TF-IDF
vectorizer.get_feature_names_out()
```

### Colaborative Filtering - Data Preparation

1. Pengabungan Data

Data dari tiga sumber yang berbeda digabungkan berdasarkan **`app_id`** dan untuk berdasarkan  **`user_id`**  untuk mendapatkan informasi lengkap tentang setiap game. Gabungan ini menghasilkan sebuah dataframe yang memuat data user dari masing masing game dan rating dari user dari masing-masing game.

2. Pemilihan Fitur Utama pada colaborative filtering

Pada tahap persiapan data untuk **Colaborative Filtering**, fitur-fitur utama yang dipilih adalah:

- **`app_id`**: ID unik untuk setiap game.
- **`title`**: Nama dari game.
- **`positive_ratio`**: Rasio ulasan positif yang diterima oleh setiap game.


Pada tahap ini, label encoding digunakan untuk mengubah kolom **`user_id`** dan **`app_id`** menjadi format numerik agar dapat digunakan dalam algoritma **Collaborative Filtering**.

```python
from sklearn.preprocessing import LabelEncoder

# Inisiasi objek LabelEncoder untuk user dan game
user_encoder = LabelEncoder()
game_encoder = LabelEncoder()

# Encoding kolom 'user_id' menjadi nilai numerik
df_games_rating_cf['user'] = user_encoder.fit_transform(df_games_rating_cf['user_id'])

# Encoding kolom 'app_id' menjadi nilai numerik
df_games_rating_cf['app'] = game_encoder.fit_transform(df_games_rating_cf['app_id'])
```
Setelah dilakukan proses encoding, data menjadi seperti berikut:

| app_id   | user_id | positive_ratio | user | app  |
|----------|---------|----------------|------|------|
| 10914530 | 339160  | 0              | 88   | 4178 |
| 19793737 | 1454400 | 0              | 97   | 28308|
| 5892961  | 202750  | 0              | 70   | 1174 |
| 6237794  | 402840  | 0              | 83   | 6210 |
| 10941265 | 423880  | 0              | 89   | 6787 |

**Jumlah dari user** --> 7462237  
**Jumlah dari games** --> 37032  
**Rating minimum** --> 0  
**Rating maksimum** --> 100

4. Normalisasi Data

Pada tahap ini, rating dinormalisasi ke dalam rentang 0-1 dengan menggunakan rumus berikut:

```python
# Normalisasi rating ke rentang 0-1
min_rating = df_games_rating_cf['positive_ratio'].min()
max_rating = df_games_rating_cf['positive_ratio'].max()

df_games_rating_cf['positive_ratio_norm'] = (df_games_rating_cf['positive_ratio'] - min_rating) / (max_rating - min_rating)
```
#### 5. Pemisahan Data untuk Pelatihan, Validasi, dan Pengujian
Data dibagi menjadi 80% untuk pelatihan, dan 20% untuk validasi serta pengujian. Selanjutnya, 20% dari data validasi dibagi lagi menjadi 10% untuk validasi dan 10% untuk pengujian.

```python
from sklearn.model_selection import train_test_split

# Memisahkan data menjadi 80% untuk training dan 20% untuk validasi dan testing
train_data, temp_data = train_test_split(df_games_rating_cf, test_size=0.2, random_state=42)

# Memisahkan 20% temp_data menjadi 10% validasi dan 10% testing
validation_data, test_data = train_test_split(temp_data, test_size=0.5, random_state=42)

# Menampilkan jumlah data untuk memastikan pembagian yang benar
print(f"Jumlah data untuk pelatihan: {len(train_data)}")
print(f"Jumlah data untuk validasi: {len(validation_data)}")
print(f"Jumlah data untuk pengujian: {len(test_data)}")
```
Hasilnya terdapat:
Jumlah data untuk pelatihan: 16251661
Jumlah data untuk validasi: 2031458
Jumlah data untuk pengujian: 2031458




## Modeling
### Content-Based Filtering (CBF)
Tahapan ini membahas mengenai model sistem rekomendasi yang digunakan untuk menyelesaikan permasalahan yang ada. Dalam hal ini, kita akan membahas tentang model **Content-Based Filtering (CBF)**, di mana rekomendasi game diberikan berdasarkan kesamaan konten atau fitur (misalnya, genre atau tags) antara game yang sudah ada dan yang sedang dicari.

#### Cosine Similarity

Pada pendekatan **Content-Based Filtering (CBF)**, kita menggunakan **Cosine Similarity** untuk mengukur kemiripan antara game yang sudah ada dengan game yang sedang dicari. Berikut adalah langkah-langkah yang dilakukan dalam implementasi ini:

1. **Menghitung Cosine Similarity**:
Setelah mendapatkan matriks **TF-IDF**, kami menggunakan **Cosine Similarity** untuk mengukur seberapa mirip setiap game dengan game lainnya berdasarkan tag yang ada. Hasilnya adalah matriks kemiripan antar game.

```python
cosine_sim = cosine_similarity(tf_idf_matrix, tf_idf_matrix)
```
Output dari operasi ini adalah matriks cosine similarity yang menunjukkan seberapa mirip game satu dengan lainnya. Setiap nilai dalam matriks ini berkisar antara 0 dan 1, dengan nilai 1 berarti dua game tersebut identik dan 0 berarti tidak ada kemiripan.
2. **Menghitung DataFrame Cosine Similarity**

Setelah menghitung **Cosine Similarity**, hasilnya disimpan dalam sebuah DataFrame untuk memudahkan pencarian rekomendasi berdasarkan nama game.

```python
cosine_df = pd.DataFrame(cosine_sim, columns=df_games_rating_cbf['title'], index=df_games_rating_cbf['title'])
```
Dengan langkah ini, kita dapat dengan mudah melakukan pencarian dan melihat kemiripan antara game satu dengan lainnya menggunakan DataFrame cosine similarity.

### Collaborative Filtering (CF)
Tahapan ini membahas mengenai model sistem rekomendasi yang digunakan untuk menyelesaikan permasalahan yang ada. Dalam hal ini, kita akan membahas tentang model **Collaborative Filtering (CF)** menggunakan **Neural Networks**. Model ini menggunakan data interaksi pengguna dengan game untuk menghasilkan rekomendasi yang lebih akurat.

#### Neural Network Collaborative Filtering

Model **Collaborative Filtering** yang digunakan di sini memanfaatkan embedding layer untuk **user** dan **game**, serta **dot product** untuk menghitung interaksi antara keduanya. Seluruh model dibangun menggunakan **TensorFlow/Keras**.

Berikut adalah langkah-langkah yang dilakukan dalam implementasi ini:

1. **Definisi Ukuran Vektor Embedding**
Ukuran vektor embedding yang digunakan untuk mewakili pengguna dan game diatur sebesar **50**, yang berarti setiap pengguna dan game diwakili oleh vektor berdimensi 50.

```python
embedding_size = 50
```
2. **Input untuk User dan Game**

Pada model ini, kita memiliki dua input, yaitu untuk **user** dan **game**. Setiap input akan diproses melalui layer embedding untuk mengubah ID pengguna dan ID game menjadi representasi vektor.

```python
user_input = Input(shape=(1,), name='user_input')
app_input = Input(shape=(1,), name='app_input')
```
Dengan input ini,dapat memetakan user dan game ke dalam representasi vektor yang digunakan oleh model untuk menghitung interaksi antara keduanya

3. **Embedding untuk User dan Game**

- **User Embedding**: Representasi vektor untuk pengguna.
- **Game Embedding**: Representasi vektor untuk game.

Setiap embedding diinisialisasi menggunakan **He Normal initializer** dan diberi regularisasi **L2**.

```python
user_embedding = Embedding(
    input_dim=df_games_rating_cf['user'].nunique(),
    output_dim=embedding_size,
    embeddings_initializer='he_normal',
    embeddings_regularizer=l2(1e-6)
)(user_input)

app_embedding = Embedding(
    input_dim=df_games_rating_cf['app'].nunique(),
    output_dim=embedding_size,
    embeddings_initializer='he_normal',
    embeddings_regularizer=l2(1e-6)
)(app_input)
```
Dengan menggunakan embedding ini, kita dapat merepresentasikan user dan game dalam bentuk vektor berdimensi yang lebih rendah, yang memungkinkan model untuk belajar interaksi antara keduanya.

4. **Bias untuk User dan Game**

Selain embedding, kita juga menambahkan **bias** untuk masing-masing pengguna dan game. Bias ini bertujuan untuk menangkap preferensi dasar pengguna dan game.

```python
user_bias = Embedding(
    input_dim=df_games_rating_cf['user'].nunique(),
    output_dim=1
)(user_input)

app_bias = Embedding(
    input_dim=df_games_rating_cf['app'].nunique(),
    output_dim=1
)(app_input)
```
Bias ini membantu model untuk memperhitungkan faktor-faktor umum atau dasar yang mempengaruhi preferensi pengguna terhadap game, seperti kecenderungan umum pengguna untuk memberikan rating tinggi atau rendah pada game tertentu.

5. **Dot Product antara User dan Game Embedding**

Interaksi antara **user** dan **game** dihitung dengan **dot product** antara embedding pengguna dan embedding game. Hasil dari dot product ini menunjukkan seberapa besar kecocokan antara pengguna dan game.

```python
dot_product = Dot(axes=2)([user_embedding, app_embedding])
```
Dengan menggunakan dot product,  dapat mengukur interaksi antara pengguna dan game berdasarkan representasi vektor embedding mereka. Hasilnya memberikan informasi tentang seberapa besar kecocokan antara pengguna dengan game yang diberikan.

6. **Penambahan Bias pada Hasil Dot Product**

Bias yang sebelumnya dihitung ditambahkan pada hasil dot product untuk memperbaiki prediksi.

```python
add_bias = Add()([dot_product, user_bias, app_bias])
```
Dengan menambahkan bias ini pada hasil dot product, model dapat memperhitungkan faktor-faktor tambahan yang mempengaruhi prediksi, seperti preferensi dasar pengguna dan karakteristik dasar game.

7. **Flatten Output**

Hasil dari dot product dan penambahan bias kemudian diratakan (flatten) untuk memudahkan pemrosesan lebih lanjut.

```python
x = Flatten()(add_bias)
```
Dengan menggunakan Flatten, dapat mengubah output dari matriks berdimensi tinggi menjadi vektor satu dimensi, sehingga dapat diproses lebih lanjut oleh layer berikutnya dalam model.

 8. **Output dengan Aktivasi Sigmoid**

Output model diproses menggunakan fungsi aktivasi **sigmoid**, karena target yang kita prediksi sudah dinormalisasi dalam rentang 0-1.

```python
output = tf.keras.activations.sigmoid(x)
```
Fungsi aktivasi sigmoid memastikan bahwa output model berada dalam rentang 0 hingga 1, yang cocok dengan target yang telah dinormalisasi sebelumnya.

9. **Membangun dan Menyusun Model**

Setelah semua layer ditentukan, model dibangun menggunakan **user_input** dan **app_input** sebagai input, serta **output** sebagai hasil prediksi. Model kemudian disusun dengan menggunakan **Mean Squared Error** sebagai loss function, serta **Adam optimizer**.

```python
model = Model(inputs=[user_input, app_input], outputs=output)

model.compile(
    loss=tf.keras.losses.MeanSquaredError(),
    optimizer=tf.keras.optimizers.Adam(),
    metrics=['mean_absolute_error', "root_mean_squared_error"]
)
```
Pada tahap ini, model siap untuk dilatih dengan loss function yang cocok untuk regresi dan optimizer Adam yang efisien untuk pembaruan bobot selama pelatihan.

10. **Pelatihan Model**

Model kemudian dilatih menggunakan data pelatihan yang sudah dipersiapkan. Dalam hal ini, data yang digunakan adalah ID pengguna dan ID game, dengan target **positive_ratio_norm** yang merupakan rating yang telah dinormalisasi.

```python
history = model.fit(
    x=[train_data['user'], train_data['app']],
    y=train_data['positive_ratio_norm'],
    batch_size=524288,
    epochs=5,
    verbose=1,
    validation_data=([validation_data['user'], validation_data['app']], validation_data['positive_ratio_norm'])
)
```
Pada tahap ini, model dilatih selama 5 epoch dengan ukuran batch yang besar. Pelatihan ini dilakukan dengan menggunakan validation data untuk memantau kinerja model di luar data pelatihan.
Output dari pelatihan akan memberikan loss dan metrik seperti mean_absolute_error dan root_mean_squared_error, yang digunakan untuk mengevaluasi seberapa baik model memprediksi rating pengguna.
### **Hasil Top-N Recommendations Content-Based Filtering (CBF) & Collaborative Filtering (CF)**

#### **1. Content-Based Filtering (CBF) Recommendations**
Pada pendekatan **Content-Based Filtering (CBF)**, rekomendasi diberikan berdasarkan kemiripan konten (seperti genre atau tags) antara game yang sudah ada dan yang sedang dicari. Di bawah ini adalah **10 game teratas** yang direkomendasikan menggunakan pendekatan ini, berdasarkan **Cosine Similarity**:

| Rank | Game Title                      | Tags                                                   | Cosine Similarity Score |
|------|----------------------------------|--------------------------------------------------------|-------------------------|
| 1    | Prince of Persia®: The Sands of Time | Action, Adventure, Parkour, Platformer, Third Person  | 0.95                    |
| 2    | Prince of Persia®: The Two Thrones | Action, Adventure, Platformer, Parkour, Third Person  | 0.93                    |
| 3    | Prince of Persia®: The Forgotten Sands™ | Action, Adventure, Platformer, Parkour, Third Person  | 0.92                    |
| 4    | Darksiders II Deathinitive Edition | Action, Hack and Slash, Adventure, RPG, Open World    | 0.91                    |
| 5    | Legacy of Kain: Soul Reaver 2    | Adventure, Action, Vampire, Story Rich, Classic        | 0.89                    |
| 6    | AeternoBlade II: Director's Rewind | Action, RPG, Indie, Time Manipulation, Puzzle          | 0.87                    |
| 7    | Legacy of Kain: Soul Reaver      | Adventure, Action, Vampire, Classic, Story Rich        | 0.86                    |
| 8    | AeternoBlade                      | Action, Indie, RPG, Time Manipulation, Metroidvania   | 0.85                    |
| 9    | Enclave                          | RPG, Action, Fantasy, Third Person, Hack and Slash     | 0.83                    |
| 10   | Rhythm Doctor                    | Rhythm, Music, Indie, Pixel Graphics, Great Soundtrack | 0.82                    |
- **Content-Based Filtering (CBF)** memberikan rekomendasi berdasarkan kemiripan konten antara game yang sudah ada dan game yang dicari, menggunakan **Cosine Similarity**.

#### **2. Collaborative Filtering (CF) Recommendations**
Pada pendekatan **Collaborative Filtering (CF)**, rekomendasi diberikan berdasarkan interaksi pengguna dengan game, menggunakan model **Neural Networks**. Di bawah ini adalah **10 game teratas** yang direkomendasikan menggunakan pendekatan ini, berdasarkan **prediksi rating** yang dihasilkan oleh model Collaborative Filtering:

| Rank | Game Title       | Tags                                              | Predicted Rating |
|------|------------------|---------------------------------------------------|------------------|
| 1    | Horizon Chase Turbo | Racing, Casual, Indie, Arcade, Sports, Retro    | 95               |
| 2    | Killing Floor    | FPS, Zombies, Co-op, Survival, Horror, Action    | 96               |
| 3    | ISLANDERS        | Relaxing, City Builder, Strategy, Building       | 95               |
| 4    | Yakuza 0         | Story Rich, Action, Beat 'em up, Great Soundtrack | 95               |
| 5    | GolfTopia        | Strategy, Sandbox, Simulation, Golf, Mini Golf   | 96               |
| 6    | AudioSurf        | Music, Rhythm, Indie, Casual, Music-Based        | 95               |
| 7    | Horizon's Gate   | Tactical RPG, Open World, Exploration, Sailing    | 96               |
| 8    | Aloof            | Casual, Building, Puzzle, Match 3, Cute, Fantasy | 100              |
| 9    | Wildermyth       | Party-Based RPG, Choices Matter, Story Rich      | 95               |
| 10   | Rhythm Doctor    | Rhythm, Music, Indie, Pixel Graphics, Great Soundtrack | 98            |



- **Collaborative Filtering (CF)** memberikan rekomendasi berdasarkan interaksi pengguna sebelumnya dengan game lain, menggunakan model **Neural Networks** dan **dot product** untuk menghitung interaksi antara pengguna dan game.




## Evaluation
### **Evaluasi Model CBF: Content-Based Filtering (CBF)**

Pada bagian ini, kita mengevaluasi kinerja model **Content-Based Filtering (CBF)** yang digunakan untuk memberikan rekomendasi game berdasarkan kesamaan konten (misalnya, genre atau tags).

#### **1. Metrik Evaluasi**

Evaluasi model **CBF** dilakukan dengan menggunakan metrik berbasis relevansi rekomendasi, seperti **Precision@K** dan **Recall@K**, yang mengukur relevansi rekomendasi yang diberikan kepada pengguna.

##### **Precision@K**
**Precision@K** mengukur seberapa banyak game yang relevan ada dalam **top-K** rekomendasi yang diberikan kepada pengguna. Metrik ini sangat berguna untuk menilai seberapa baik sistem rekomendasi dalam memberikan item yang sesuai dengan preferensi pengguna.

##### **Recall@K**
**Recall@K** mengukur seberapa banyak game relevan yang ada di seluruh dataset berhasil direkomendasikan di antara **top-K** rekomendasi. Metrik ini menunjukkan seberapa banyak item relevan yang dapat ditemukan dalam rekomendasi.

#### **2. Evaluasi dengan Precision@K dan Recall@K**

Setelah melakukan prediksi rekomendasi menggunakan **Content-Based Filtering**, kita dapat mengevaluasi seberapa relevan rekomendasi tersebut dengan menggunakan **Precision@K** dan **Recall@K**. Berikut adalah contoh evaluasi menggunakan **top 10 rekomendasi**:

```python
# Mengambil rekomendasi untuk game 'Prince of Persia: Warrior Within™'
rekomendasi = game_recommendations('Prince of Persia: Warrior Within™')

# Output contoh hasil evaluasi
print(f"Precision@10: {precision:.4f}")
print(f"Recall@10: {recall:.4f}")
```
Precision@10 menunjukkan bahwa **1.0000** dari top-10 rekomendasi adalah relevan (semua item relevan ada dalam top-K).
Recall@10 menunjukkan bahwa hanya **0.0004** dari semua item relevan ditemukan dalam top-10 rekomendasi.
### **Relevansi Evaluasi CBF dengan Business Understanding**

Berdasarkan **Business Understanding** yang disampaikan, tujuan utama dari sistem rekomendasi ini adalah untuk **meningkatkan pengalaman pengguna**, **peningkatan loyalitas pengguna**, dan **meningkatkan pendapatan** melalui game yang relevan dan disesuaikan dengan preferensi pengguna.

1. **Rekomendasi yang Lebih Relevan**:
    - Model **Content-Based Filtering (CBF)** dapat memberikan rekomendasi game yang lebih relevan berdasarkan kesamaan genre, tag, atau fitur lainnya. Ini sesuai dengan tujuan untuk memberikan **pengalaman pengguna yang lebih personal** dan **meningkatkan kepuasan pengguna**. Sistem ini memungkinkan pengguna untuk menerima saran game yang sesuai dengan preferensi dan minat mereka.
    
2. **Penemuan Game Baru**:
    - Dengan menggunakan model **CBF**, pengguna dapat **menemukan game baru** yang sesuai dengan minat mereka, yang sangat penting untuk meningkatkan **engagement** pengguna di platform seperti **Steam**. Ini memungkinkan pengguna untuk mengeksplorasi game yang mungkin tidak mereka temui secara langsung, tetapi masih relevan dengan apa yang telah mereka nikmati sebelumnya.

3. **Meningkatkan Waktu yang Dihabiskan di Platform**:
    - Dengan memberikan game yang relevan berdasarkan kesamaan konten, pengguna lebih mungkin untuk **menghabiskan lebih banyak waktu** di platform. Ketika pengguna menemukan game baru yang menarik berdasarkan rekomendasi, mereka akan lebih terlibat dan tertarik untuk mencoba lebih banyak game yang sesuai dengan preferensi mereka. Hal ini secara langsung dapat **meningkatkan retensi pengguna** dan **memperpanjang waktu interaksi dengan platform**.

4. **Meningkatkan Loyalitas Pengguna dan Pendapatan**:
    - **CBF** dapat memperbaiki **loyalitas pelanggan** dan meningkatkan **customer lifetime value (CLTV)** dengan memberikan rekomendasi yang sesuai dengan keinginan pengguna. Dengan demikian, platform dapat menciptakan pengalaman yang lebih memuaskan bagi pengguna, mendorong mereka untuk kembali dan menjelajahi lebih banyak game, serta meningkatkan peluang untuk monetisasi melalui model **freemium** atau **berlangganan berbayar**.


### Evaluasi Model Collaborative Filtering (CF)

Pada bagian ini, kita akan mengevaluasi kinerja model **Collaborative Filtering (CF)** yang dibangun menggunakan **embedding** untuk pengguna dan game serta **dot product** untuk menghitung interaksi antar keduanya. Evaluasi dilakukan menggunakan metrik **MSE**, **MAE**, dan **RMSE** untuk memastikan bahwa model memberikan rekomendasi yang akurat dan relevan berdasarkan data yang ada.


**1. Mean Squared Error (MSE)**

**Formula:**

$$
MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
$$

**Penjelasan**: 
MSE mengukur rata-rata kuadrat perbedaan antara nilai yang diprediksi oleh model dan nilai asli. Semakin kecil nilai MSE, semakin baik model dalam memprediksi rating yang relevan dan sesuai dengan preferensi pengguna.

---

**2. Mean Absolute Error (MAE)**

**Formula:**

$$
MAE = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|
$$

**Penjelasan**: 
MAE mengukur rata-rata perbedaan absolut antara nilai yang diprediksi oleh model dan nilai asli. Nilai MAE yang lebih kecil menunjukkan bahwa model lebih baik dalam memberikan prediksi yang sesuai.

---

**3. Root Mean Squared Error (RMSE)**

**Formula:**

$$
RMSE = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2}
$$



**Penjelasan**: 
RMSE memberikan gambaran tentang seberapa besar perbedaan rata-rata antara rating yang diprediksi dan rating yang sebenarnya, dengan memperhitungkan besar kecilnya kesalahan. RMSE lebih sensitif terhadap perbedaan besar, sehingga memberikan penalti lebih besar untuk prediksi yang jauh dari nilai asli.

#### Hasil Evaluasi Model

Berdasarkan hasil pelatihan selama **5 epoch**, berikut adalah metrik yang dihitung untuk model:

**Epoch 1:**
- **MSE**: 0.1182
- **MAE**: 0.3248
- **RMSE**: 0.3432

**Epoch 2:**
- **MSE**: 0.0680
- **MAE**: 0.2360
- **RMSE**: 0.2603

**Epoch 3:**
- **MSE**: 0.0451
- **MAE**: 0.1813
- **RMSE**: 0.2120

**Epoch 4:**
- **MSE**: 0.0330
- **MAE**: 0.1473
- **RMSE**: 0.1813

**Epoch 5:**
- **MSE**: 0.0255
- **MAE**: 0.1239
- **RMSE**: 0.1596

#### Penjelasan Hasil

Seiring berjalannya waktu dan bertambahnya epoch, nilai **MSE**, **MAE**, dan **RMSE** mengalami penurunan yang signifikan. Ini menunjukkan bahwa model semakin mampu memprediksi rating yang diberikan oleh pengguna dengan lebih akurat. Hal ini mencerminkan bahwa model semakin efektif dalam memberikan rekomendasi yang relevan, yang diharapkan dapat meningkatkan **pengalaman pengguna** dan **loyalitas pengguna** di platform.


### Relevansi Evaluasi CF dengan Business Understanding

Berdasarkan **Business Understanding** yang telah dijelaskan sebelumnya, tujuan utama dari sistem rekomendasi ini adalah untuk **meningkatkan pengalaman pengguna**, **meningkatkan keterlibatan pengguna**, dan **memaksimalkan pendapatan** platform dengan memberikan rekomendasi yang lebih personal.

1. **Rekomendasi yang Lebih Akurat**: 
   - Dengan penurunan nilai **MSE**, **MAE**, dan **RMSE**, model **Collaborative Filtering** semakin baik dalam memberikan prediksi yang sesuai dengan preferensi pengguna. Hal ini menunjukkan bahwa model dapat memberikan **rekomendasi yang lebih akurat**, yang sesuai dengan tujuan untuk meningkatkan **pengalaman pengguna**.

2. **Meningkatkan Retensi dan Loyalitas Pengguna**:
   - Semakin akurat prediksi yang diberikan oleh model, semakin besar kemungkinan pengguna akan menemukan game yang mereka sukai, yang membantu meningkatkan **loyalitas pengguna** dan **engagement** pengguna di platform seperti **Steam**.

3. **Menambah Pendapatan**:
   - Rekomendasi yang lebih personal dan relevan, berdasarkan interaksi historis pengguna, dapat mendorong lebih banyak pembelian atau langganan game, yang pada akhirnya dapat **meningkatkan pendapatan** platform.

Secara keseluruhan, evaluasi **Collaborative Filtering (CF)** dengan menggunakan **MSE**, **MAE**, dan **RMSE** sangat relevan dengan tujuan bisnis yang Anda sebutkan. Hasil yang diperoleh menunjukkan bahwa model ini efektif dalam memberikan rekomendasi yang sesuai dengan preferensi pengguna, yang berkontribusi pada **peningkatan pengalaman pengguna**, **loyalitas**, dan **pendapatan**.


# Referensi
1. J. Zhang, Y. Chen, and M. Zha, "A collaborative filtering approach to personalized game recommendation in social networks," *International Journal of Computer Applications*, vol. 24, no. 10, pp. 12–19, 2011. DOI: 10.5120/3350-4645

2. S. B. Koren, "Collaborative filtering for the entertainment industry: The movieLens case," *IEEE Transactions on Systems, Man, and Cybernetics: Systems*, vol. 46, no. 1, pp. 68–80, 2016. DOI: 10.1109/TSMC.2015.2432871

3.  **Steam Community Recommendations**, [Steam Community](https://steamcommunity.com/app/games/recommendations)

4. T. M. Mitchell, "Machine Learning," *McGraw-Hill Education*, 1997. ISBN: 978-0070428072

5. K. R. K. R. Chai, "A Survey of Personalized Recommendation Systems in E-Commerce," *Journal of Electronic Commerce Research*, vol. 16, no. 2, pp. 136–146, 2015. DOI: 10.1177/2158244015568249
