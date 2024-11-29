
# Laporan Proyek Machine Learning - Ma'shum Abdul Jabbar

## Project Overview

Seiring dengan pesatnya perkembangan teknologi dan pengumpulan data, data kini dimanfaatkan untuk menciptakan sistem yang lebih efisien, salah satunya melalui sistem rekomendasi. Sistem rekomendasi ini berperan penting dalam memberikan pengalaman yang lebih baik kepada pengguna dengan menyarankan item yang relevan berdasarkan preferensi mereka. 

Salah satu pendekatan yang banyak digunakan dalam sistem rekomendasi adalah **Content-Based Filtering**, yang memanfaatkan informasi yang terkandung dalam item itu sendiri untuk memberikan rekomendasi yang sesuai. Pendekatan ini bekerja dengan menganalisis fitur-fitur spesifik dari item seperti deskripsi, genre, aktor, atau sutradara untuk memberikan saran yang lebih personal kepada pengguna.

### **Latar Belakang**

Sistem rekomendasi telah menjadi komponen penting dalam berbagai platform digital. Sebuah penelitian menyebutkan bahwa sistem ini mampu membantu organisasi yang mengelola data dari jumlah pelanggan yang besar untuk memberikan saran yang lebih efektif kepada pengguna berdasarkan preferensi mereka. Sistem rekomendasi film, misalnya, dapat dirancang menggunakan atribut seperti genre, aktor, atau sutradara, bahkan kombinasi dari beberapa atribut. Dalam penelitian ini, sistem rekomendasi dibangun menggunakan pendekatan **content-based filtering** dengan korelasi genre sebagai fokus utamanya. Dataset yang digunakan adalah **MovieLens dataset** yang diolah dengan alat analisis data seperti R (Reddy et al., 2019).

Sistem rekomendasi serupa juga telah diimplementasikan untuk film Indonesia, dengan menggunakan elemen seperti genre, sutradara, aktor utama, dan deskripsi. Hasil pengujian menunjukkan efektivitas metode ini dalam memberikan rekomendasi yang sesuai dengan preferensi pengguna, serta mendorong eksplorasi terhadap film yang belum dikenal luas. Sistem seperti ini berkontribusi pada pengalaman menonton yang lebih memuaskan bagi pengguna (Zakharia et al., 2024).

### **Pentingnya Proyek**

Proyek ini penting untuk diselesaikan karena:
- **Meningkatkan pengalaman pengguna**: Dengan memberikan rekomendasi yang relevan, pengguna dapat dengan mudah menemukan film yang sesuai dengan preferensi mereka.
- **Mendukung industri perfilman**: Sistem ini dapat membantu memperkenalkan film yang kurang dikenal kepada audiens yang lebih luas, mendorong eksplorasi film.
- **Optimalisasi data**: Sistem rekomendasi memanfaatkan data yang ada untuk menciptakan nilai tambah bagi pengguna dan industri.

### **Referensi**
- Reddy, S., Nalluri, S., Kunisetti, S., Ashok, S., Venkatesh, B. (2019). *Content-Based Movie Recommendation System Using Genre Correlation.* In: Satapathy, S., Bhateja, V., Das, S. (eds) Smart Intelligent Computing and Applications. *Smart Innovation, Systems and Technologies, vol 105.* Springer, Singapore. [https://doi.org/10.1007/978-981-13-1927-3_42](https://doi.org/10.1007/978-981-13-1927-3_42)

- Zakharia, A., Dia Ulhaq, A., Budi Suryono, A., Cahyo Nugroho, N., Ferdinand Hafith, D., & De Andrade Gusmao, N. (2024). *Sistem Rekomendasi Film Indonesia Menggunakan Metode Content-Based Filtering.* *LOGIC: Jurnal Ilmu Komputer Dan Pendidikan, 2*(4), 671–678. [https://www.journal.mediapublikasi.id/index.php/logic/article/view/4299](https://www.journal.mediapublikasi.id/index.php/logic/article/view/4299)

---

## Business Understanding

### **Problem Statements**

1. **Bagaimana memberikan rekomendasi film yang relevan berdasarkan metadata film?**  
   Metadata seperti deskripsi, aktor, tagline, dan genre sering kali menjadi sumber informasi yang kurang dimanfaatkan untuk memberikan rekomendasi yang akurat.

2. **Bagaimana mencapai keseimbangan antara precision dan recall pada sistem rekomendasi?**  
   Rekomendasi yang terlalu fokus pada precision dapat mengurangi cakupan film yang direkomendasikan, sedangkan recall tinggi tanpa precision cukup akan menurunkan kualitas rekomendasi.

3. **Bagaimana meningkatkan pengalaman pengguna dengan memberikan rekomendasi film yang sesuai?**  
   Sistem rekomendasi yang baik dapat dapat memberikan rekomendasi yang relevan sehingga meningkatkan keterlibatan dan kepuasan pengguna.

---

### **Goals**

1. **Menerapkan sistem rekomendasi berbasis Content-Based Filtering untuk menemukan film relevan.**  
   Sistem ini bertujuan untuk menggunakan metadata seperti genre, deskripsi, aktor, dan tagline untuk memberikan rekomendasi film yang mirip dengan film yang disukai oleh pengguna.

2. **Mengoptimalkan metrik evaluasi rekomendasi (precision, recall, dan F1-Score).**  
   Sistem akan dirancang untuk mencapai precision minimal 75%, sehingga rekomendasi tetap relevan bagi pengguna.

3. **Meningkatkan pengalaman pengguna dengan rekomendasi yang relevan dan personal.**  
   Sistem ini bertujuan untuk memberikan rekomendasi yang tidak hanya relevan, tetapi juga mendorong pengguna untuk menjelajahi lebih banyak konten.

---

### **Solution Approach**

1. **Content-Based Filtering**  
   Sistem ini menggunakan metadata seperti deskripsi, genre, aktor, dan tagline untuk menganalisis kesamaan antarfilm. Algoritma ini memanfaatkan **TF-IDF Vectorizer** dan **Cosine Similarity** untuk menemukan film dengan atribut serupa.

2. **Eksperimen dengan Threshold Kesamaan**  
   Menyesuaikan ambang batas similarity memungkinkan sistem untuk mengontrol keseimbangan antara precision dan recall, memastikan rekomendasi tetap relevan tanpa kehilangan cakupan.

---

### **Keuntungan bagi Bisnis**

1. **Peningkatan Keterlibatan Pengguna:**  
   Rekomendasi yang relevan mendorong pengguna untuk menghabiskan lebih banyak waktu menjelajahi konten, sehingga meningkatkan retensi pengguna.

2. **Pengalaman Pengguna yang Lebih Baik:**  
   Dengan rekomendasi yang akurat, pengguna akan lebih puas dengan pengalaman mereka, yang secara langsung meningkatkan loyalitas terhadap platform.

3. **Monetisasi yang Lebih Baik:**  
   Platform yang memberikan pengalaman personal memiliki peluang lebih tinggi untuk menarik lebih banyak pengguna dan meningkatkan potensi pendapatan melalui langganan atau iklan.


---

## **Data Understanding**

### **Sumber Data**
Dataset yang digunakan dalam proyek ini diperoleh dari **[Kaggle: TMDB Movie Metadata](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)**. Dataset ini memuat informasi metadata terkait film, termasuk pemeran, kru, genre, dan atribut lainnya yang relevan untuk membangun sistem rekomendasi.

Dataset terdiri dari dua file utama:
1. **data_tmdb_credits**: Memuat informasi mengenai pemeran dan kru film.
2. **data_tmdb_movies**: Berisi informasi lengkap terkait atribut film, seperti judul, genre, deskripsi, tanggal rilis, dan lain-lain.

---

### **Informasi Dataset**

#### **Dataset `data_tmdb_credits`**
Output dari `data_tmdb_credits.head()` menunjukkan 5 baris pertama data ini, yang memiliki kolom-kolom berikut:
- **movie_id**: ID unik yang mengidentifikasi setiap film dalam dataset.
- **title**: Judul film.
- **cast**: Informasi mengenai pemeran, dalam format JSON yang mencakup ID pemeran, nama, dan karakter yang diperankan.
- **crew**: Informasi mengenai kru film, termasuk peran mereka dalam produksi (sutradara, penulis, dll.), dalam format JSON.

#### **Dataset `data_tmdb_movies`**
Hasil `data_tmdb_movies.info()` menunjukkan bahwa dataset ini memiliki **4803 entri** dengan **20 kolom**. Berikut adalah penjelasan setiap kolom:
- **budget**: Anggaran produksi film dalam format integer.
- **genres**: Kategori atau jenis film dalam format string.
- **homepage**: URL halaman resmi film (beberapa nilai null).
- **id**: ID unik untuk setiap film dalam format integer.
- **keywords**: Kata kunci yang relevan dengan film dalam format string.
- **original_language**: Bahasa asli film (contoh: "en" untuk bahasa Inggris).
- **original_title**: Judul asli film.
- **overview**: Deskripsi singkat tentang film (beberapa nilai null).
- **popularity**: Tingkat popularitas film dalam format float.
- **production_companies**: Perusahaan produksi yang terlibat dalam film.
- **production_countries**: Negara tempat produksi film dilakukan.
- **release_date**: Tanggal rilis film (beberapa nilai null).
- **revenue**: Pendapatan yang dihasilkan film dalam format integer.
- **runtime**: Durasi film dalam menit (beberapa nilai null).
- **spoken_languages**: Bahasa yang digunakan dalam film.
- **status**: Status film (contoh: "Released").
- **tagline**: Tagline promosi film (beberapa nilai null).
- **title**: Judul film.
- **vote_average**: Rata-rata rating dari penonton.
- **vote_count**: Jumlah ulasan yang diterima film.

---

### **Insight Awal dari Data**

1. **Jumlah Data**:
   - Dataset `data_tmdb_credits` memiliki informasi pemeran dan kru untuk setiap film.
   - Dataset `data_tmdb_movies` terdiri dari **4803 film** dengan berbagai atribut.

2. **Kondisi Data**:
   - Beberapa kolom memiliki nilai **null**, seperti `homepage`, `overview`, `tagline`, dan `release_date`. Perlu dilakukan penanganan nilai null pada proses pre-processing.
   - Atribut seperti `genres`, `tagline`, `overview` dan `cast` berbentuk string yang dapat digunakan untuk analisis berbasis teks.

3. **Kesesuaian untuk Sistem Rekomendasi**:
   - **Kolom `overview` dan `genres`** akan digunakan untuk membangun sistem rekomendasi berbasis content filtering, karena keduanya memberikan informasi langsung mengenai deskripsi dan kategori film.

---

### **Tahapan Eksplorasi Data**

Pada tahap eksplorasi data, dilakukan beberapa analisis untuk memahami pola dan informasi yang dapat mendukung pengembangan sistem rekomendasi. Berikut adalah hasil eksplorasi yang telah dilakukan:

---

**1. Menampilkan Genre Film**

Genre adalah salah satu fitur penting dalam sistem rekomendasi berbasis konten. Berikut adalah daftar genre yang terdapat dalam dataset TMDB:

![Genre Film](https://github.com/kangdconqueror/sistem-rekomendasi/blob/main/genre.png?raw=true)

Genre-genre ini akan digunakan untuk mengelompokkan film dan menemukan kesamaan antarfilm dalam sistem rekomendasi.

---

**2. Menampilkan 10 Aktor dengan Film Terbanyak**

Visualisasi berikut menunjukkan aktor dengan jumlah film terbanyak dalam dataset TMDB:

![Aktor Terbanyak dengan Film](https://github.com/kangdconqueror/sistem-rekomendasi/blob/main/aktor-terbanyak-film.png?raw=true)

Dari visualisasi di atas, terlihat bahwa **Samuel L. Jackson** merupakan aktor dengan jumlah film terbanyak pada database TMDB. Informasi ini dapat digunakan untuk analisis lebih lanjut, seperti popularitas aktor dalam berbagai genre film.

---

**3. Menampilkan 10 Film dengan Rating Tertinggi**

Berikut adalah visualisasi yang menampilkan 10 film dengan rata-rata nilai suara (**rating**) tertinggi dalam dataset TMDB:

![Top 10 Film dengan Rating Tertinggi](https://github.com/kangdconqueror/sistem-rekomendasi/blob/main/top-rating.png?raw=true)

Visualisasi ini menunjukkan film-film yang paling disukai berdasarkan rata-rata nilai suara dari pemilih. Data ini memberikan gambaran mengenai film-film berkualitas tinggi menurut penilaian pengguna. Informasi ini juga dapat digunakan untuk menilai rekomendasi berdasarkan preferensi pengguna terhadap film dengan rating tinggi, meski dalam proyek kali ini kita belum akan menggunakan rating.

---

## **Data Preparation**

Pada tahap ini, dilakukan serangkaian proses untuk mempersiapkan dataset sehingga siap digunakan untuk model Content-Based Filtering. Berikut adalah langkah-langkah yang dilakukan:

---

### **1. Mengatasi Missing Value**

Dataset awal memiliki beberapa kolom dengan nilai yang hilang (missing value). Langkah-langkah berikut diterapkan untuk menangani nilai yang hilang:

- Kolom **runtime** diisi dengan nilai median runtime.
- Kolom **homepage** diisi dengan string kosong.
- Kolom **overview** dan **tagline** diisi dengan nilai dari kolom **title_x** jika nilainya kosong.
- Kolom **release_date** diisi menggunakan metode forward fill (mengisi dengan nilai sebelumnya).

Tujuan dari langkah ini adalah untuk memastikan tidak ada nilai yang hilang sehingga proses analisis selanjutnya dapat berjalan tanpa kendala.

---

### **2. Mengatasi Duplikasi Kolom**

Dataset memiliki kolom duplikat seperti **title_x** dan **title_y**, serta **id** dan **movie_id**. Proses berikut dilakukan:

- Mengecek dan memastikan tidak ada perbedaan signifikan antara kolom duplikat.
- Menyimpan kolom yang lebih relevan, yaitu **title** dari **title_x** dan **id** dari **id**.
- Menghapus kolom duplikat yang tidak diperlukan.

Langkah ini dilakukan untuk menyederhanakan dataset dan mengurangi kompleksitas analisis.

---

### **3. Memilih Kolom yang Relevan**

Untuk analisis berbasis konten, dipilih kolom-kolom yang memiliki informasi esensial terkait film. Kolom yang dipertahankan adalah:

- **id**: ID unik untuk setiap film.
- **title**: Judul film.
- **overview**: Deskripsi atau sinopsis singkat film.
- **tagline**: Slogan atau pesan singkat dari film.
- **cast**: Daftar nama pemeran film.
- **genres**: Genre atau kategori film.

Kolom lain yang tidak relevan seperti **budget**, **revenue**, dan **vote_average** dihapus karena tidak diperlukan untuk analisis berbasis konten.

Hasil setelah pemilihan kolom menunjukkan bahwa dataset memiliki 4803 entri dengan 6 kolom tanpa nilai kosong.

---

### **4. Analisis Berdasarkan Keyword**

Untuk memahami kemampuan dataset dalam mendukung pencarian berbasis kata kunci, dilakukan filter pada film yang mengandung keyword tertentu dalam kolom **title**, **overview**, atau **tagline**. Berikut adalah hasilnya:

#### **a. Keyword: "The Dark Knight"**

Jumlah film yang mengandung kata "The Dark Knight" adalah **6**, yaitu:

- The Dark Knight Rises
- The Dark Knight
- Batman Forever
- Seventh Son
- Batman
- Batman: The Dark Knight Returns, Part 2

#### **b. Keyword: "Batman"**

Jumlah film yang mengandung kata "Batman" adalah **10**, termasuk:

- Batman v Superman: Dawn of Justice
- Batman Begins
- Batman & Robin
- Batman Forever
- Batman Returns

---

### **5. Kasus Khusus: "Seventh Son"**

Pada pencarian dengan keyword "The Dark Knight", ditemukan bahwa film *Seventh Son* muncul dalam hasil filter meskipun judulnya tidak mengandung kata tersebut. Setelah dianalisis, diketahui bahwa kata "The Dark Knight" terdapat pada kolom **tagline** dengan isi:

> *"When darkness falls, the son will rise. When the son falls, the dark knight will rise."*

Hal ini menunjukkan bahwa sistem rekomendasi berbasis konten harus memperhatikan sumber informasi (seperti tagline) untuk menghindari hasil rekomendasi yang tidak relevan.

---

### **Kesimpulan**

- Dataset telah dibersihkan dari nilai yang hilang dan kolom duplikat, serta difokuskan pada kolom yang relevan untuk analisis berbasis konten.
- Pencarian berbasis kata kunci memberikan wawasan mengenai relevansi data, namun memerlukan kontrol yang lebih baik terhadap konteks informasi seperti tagline.
- Dataset siap digunakan untuk langkah berikutnya, yaitu pembangunan model Content-Based Filtering yang memanfaatkan kolom **overview**, **genres**, **cast**, dan **tagline** untuk analisis kemiripan antar film.


## **Modeling and Result**

Pada tahap ini, dilakukan pembangunan sistem rekomendasi berbasis **Content-Based Filtering** untuk menyelesaikan permasalahan rekomendasi film. Berikut adalah langkah-langkah dan metode yang digunakan:

### **TF-IDF**

**Representasi Data Teks**

Representasi data teks dilakukan menggunakan metode **TF-IDF (Term Frequency-Inverse Document Frequency)**. Teknik ini bertujuan untuk:
- Mengonversi data teks menjadi representasi numerik yang dapat dihitung oleh model.
- Memberikan bobot yang lebih tinggi untuk kata-kata yang memiliki frekuensi tinggi dalam dokumen tertentu, namun jarang muncul di dokumen lain.


![Formula TF-IDF](https://github.com/kangdconqueror/sistem-rekomendasi/blob/main/tf-idf.png?raw=true)

- **TF**: Frekuensi kemunculan kata dalam dokumen tertentu.
- **IDF**: Logaritma terbalik dari frekuensi dokumen yang mengandung kata tersebut.


### **Formula Cosine Similarity**

**Perhitungan Kesamaan**

Perhitungan kesamaan antar film dilakukan menggunakan **Cosine Similarity**. Metode ini digunakan untuk mengukur tingkat kemiripan antara vektor representasi teks berdasarkan sudut antara vektor.

![Formula TF-IDF](https://github.com/kangdconqueror/sistem-rekomendasi/blob/main/consine.png?raw=true)

Cosine Similarity mengukur kesamaan antara dua vektor berdasarkan sudut kosinus antara mereka dalam ruang vektor. 


### **Proses Rekomendasi**

Langkah-langkah utama dalam sistem rekomendasi:

1. **Ekstraksi Fitur**: Data teks (seperti deskripsi film atau genre) diubah menjadi vektor TF-IDF.
2. **Penghitungan Kemiripan**: Menggunakan Cosine Similarity untuk membandingkan film yang dipilih pengguna dengan semua film lain dalam dataset.
3. **Penyortiran Hasil**: Mengurutkan daftar film berdasarkan skor kesamaan tertinggi.
4. **Pemfilteran**: Menghapus film yang telah ditonton pengguna dari daftar rekomendasi.

---

### Hasil Film Recommendations Based on Cosine Similarity

| **Judul Film**                          | **Skor Similarity** | **Pemeran**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | **Genres**                      |
|-----------------------------------------|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------|
| The Dark Knight Rises                   | 0.235753             | Christian Bale, Michael Caine, Gary Oldman, Anne Hathaway, Tom Hardy, Marion Cotillard, Joseph Gordon-Levitt, Morgan Freeman, Cillian Murphy, Juno Temple, Liam Neeson, Matthew Modine, Alon Aboutboul, Ben Mendelsohn, Nestor Carbonell, Josh Pence, Tom Conti, Joey King, Warren Brown, Daniel Sunjata, Sam Kennard, Aliash Tepina, Nick Julian, Miranda Nolan, Claire Julien, Aidan Gillen, Burn Gorman, Brett Cullen, Reggie Lee, Joseph Lyle Taylor, Chris Ellis, Duane Henry, James Harvey Ward, Gonzalo Menendez, Cameron Jack, Lex Daniel, Tyler Dean Flores, Thomas Lennon, Trevor White, Rob Brown, Fredric Lehne, and many more. | Action, Crime, Drama, Thriller |
| Batman Begins                          | 0.164443             | Christian Bale, Michael Caine, Liam Neeson, Katie Holmes, Gary Oldman, Cillian Murphy, Tom Wilkinson, Morgan Freeman, Rutger Hauer, Ken Watanabe, Mark Boone Junior, Linus Roache, Larry Holden, Gerard Murphy, Colin McFarlane, Jack Gleeson, T.J. Ramini, Kieran Hurley, Catherine Porter, Gus Lewis, Rade Serbedzija, Sara Stewart, Richard Brake, Emma Lockhart, Christine Adams, John Nolan, Karen David, and many more.                                                                                                                                                                                                                     | Action, Crime, Drama           |
| Batman Forever                         | 0.148847             | Val Kilmer, Tommy Lee Jones, Jim Carrey, Nicole Kidman, Chris O'Donnell, Michael Gough, Pat Hingle, Drew Barrymore, Debi Mazar, Elizabeth Sanders, Rene Auberjonois, Joe Grifasi, Philip Moon, Jessica Tuck, Dennis Paladino, Don Wilson, Bob Zmuda.                                                                                                                                                                                                                                                                                                                                                                        | Action, Crime, Fantasy         |
| Batman Returns                         | 0.135284             | Michael Keaton, Danny DeVito, Michelle Pfeiffer, Christopher Walken, Michael Gough, Pat Hingle, Vincent Schiavelli, Michael Murphy, Cristi Conaway, Paul Reubens, Diane Salinger.                                                                                                                                                                                                                                                                                                                                                                                                                                         | Action, Fantasy                |
| Law Abiding Citizen                    | 0.134281             | Jamie Foxx, Gerard Butler, Colm Meaney, Bruce McGill, Leslie Bibb, Michael Irby, Gregory Itzin, Regina Hall, Emerald-Angel Young, Christian Stolte, Annie Corley, Richard Portnow, Viola Davis, Michael Kelly, Josh Stewart, Roger Bart, Dan Bittner, Brooke Stacy Mills, Patrick McDade, Richard Barlow.                                                                                                                                                                                                                                                                                                                    | Drama, Crime, Thriller         |
| Harsh Times                            | 0.126822             | Christian Bale, Freddy Rodríguez, Eva Longoria, Chaka Forman, Tammy Trull, J.K. Simmons, Michael Monks, Samantha Esteban, Tania Verafield, Noel Gugliemi, Adriana Millan, Geovanny Corvera, Cesar Garcia, Terry Crews, Emilio Rivera, Paul Renteria.                                                                                                                                                                                                                                                                                                                                                                     | Crime, Drama, Thriller, Action |
| Batman: The Dark Knight Returns, Part 2| 0.123448             | Peter Weller, Ariel Winter, David Selby, Michael Emerson, Mark Valley, Grey Griffin, Frank Welker, Dee Bradley Baker, Michael McKean, James Patrick Stuart, Maria Canals-Barrera, Gwendoline Yeo, Danny Jacobs, Townsend Coleman, Michael Jackson, Bruce Timm, Tress MacNeille, Paget Brewster, Gary Anthony Williams, Conan O'Brien, Robin Atkin Downes, Yuri Lowenthal, Greg Eagles.                                                                                                                                                                                                                               | Action, Animation              |
| Kiss of Death                          | 0.123307             | David Caruso, Samuel L. Jackson, Nicolas Cage, Helen Hunt, Kathryn Erbe, Stanley Tucci, Michael Rapaport, Ving Rhames, Philip Baker Hall, Anthony Heald.                                                                                                                                                                                                                                                                                                                                                                                                                                                                   | Action, Crime, Drama, Thriller |
| Hitman                                 | 0.119232             | Timothy Olyphant, Dougray Scott, Olga Kurylenko, Robert Knepper, Ulrich Thomsen, Henry Ian Cusick, Michael Offei, Christian Erickson, Eriq Ebouaney, Joe Sheridan, James Faulkner.                                                                                                                                                                                                                                                                                                                                                                                                                                          | Action, Crime, Drama, Thriller |
| Dead Man Down                          | 0.118277             | Colin Farrell, Noomi Rapace, Terrence Howard, Dominic Cooper, Isabelle Huppert, Luis Da Silva Jr., Stuart Bennett, Franky G, Declan Mulvey, John Cenatiempo, Roy James Wilson, Myles Humphus, Stephen Hill, Aaron Vexler, James Biberi, F. Murray Abraham, Andrew Stewart-Jones, Krystal Tini, William Zielinski, Jessica Jean Wilson, Christopher Cline, Kimberly S. Fairbanks, Michael McKiddy, Beata Dalton, Accalia Quintana, Jay Santiago, Maria Laboy, Saul Stein, Roy Milton Davis, Armand Assante, Jennifer Mudge, Ante Novakovic, Kresh Novakovic, Raw Leiba, Jennifer Butler, and many more.                                    | Thriller, Action, Crime, Drama |



## **Evaluation**

Pada tahap ini, kita akan mengevaluasi performa sistem rekomendasi berbasis **Content-Based Filtering** yang telah dibangun menggunakan model **TF-IDF** dan **Cosine Similarity**. Evaluasi dilakukan untuk mengukur seberapa efektif sistem dalam memberikan rekomendasi yang relevan berdasarkan kata kunci yang dimasukkan oleh pengguna.

### **Metrik Evaluasi yang Digunakan**

Untuk mengevaluasi hasil dari sistem rekomendasi, beberapa metrik yang umum digunakan dalam sistem berbasis konten adalah sebagai berikut:

#### 1. **Precision@k**:
Metrik ini mengukur seberapa banyak item yang relevan (film yang relevan) ada di dalam k rekomendasi teratas yang diberikan oleh sistem.
- **Formula**:  
  ![Precision](https://github.com/kangdconqueror/sistem-rekomendasi/blob/main/Precision.png?raw=true)
  
- **Penjelasan**: Precision@k menunjukkan seberapa banyak rekomendasi yang diberikan oleh sistem benar-benar relevan dengan kata kunci yang diberikan.

#### 2.  **Recall@k**:
Metrik ini mengukur sejauh mana sistem dapat menemukan seluruh item relevan di antara hasil rekomendasi.
- **Formula**:  
  ![Recall](https://github.com/kangdconqueror/sistem-rekomendasi/blob/main/Recall.png?raw=true)

- **Penjelasan**: Recall@k membantu mengukur seberapa efektif sistem dalam menemukan semua film yang relevan untuk kata kunci yang dimasukkan.

#### 3. **F1-Score**:
F1-Score adalah gabungan dari precision dan recall, memberikan gambaran yang lebih menyeluruh mengenai kemampuan sistem.
- **Formula**:  
  ![F1 Score](https://github.com/kangdconqueror/sistem-rekomendasi/blob/main/F1Score.png?raw=true)

- **Penjelasan**: F1-Score memberikan nilai tunggal untuk menilai keseimbangan antara precision dan recall, yang sangat berguna untuk memastikan bahwa sistem tidak hanya memberikan rekomendasi yang relevan, tetapi juga menemukan semua item relevan.

### **Analisis Hasil Evaluasi**

Pada tahap ini, kita akan menggunakan hasil dari sistem rekomendasi untuk menghitung precision dan recall berdasarkan hasil yang diberikan untuk kata kunci tertentu. Berdasarkan hasil yang diperoleh, kita akan mengevaluasi seberapa baik model memberikan rekomendasi yang relevan.

Berikut adalah kode untuk mengevaluasi sistem rekomendasi menggunakan metrik di atas:

**Langkah Evaluasi**
1. Asumsikan kita memiliki data ground truth berupa daftar film relevan untuk pengguna (misalnya dari preferensi sebelumnya).
2. Bandingkan rekomendasi sistem dengan daftar film relevan tersebut.

Berikut adalah hasil evaluasi sistem rekomendasi berdasarkan kata kunci **"The Dark Knight"**:

- **Precision@10**: 50%
- **Recall@10**: 100%
- **F1-Score**: 66%

### **Kesimpulan**

Berdasarkan evaluasi yang dilakukan, sistem rekomendasi telah memberikan performa yang cukup baik untuk kata kunci **"The Dark Knight"**, dengan hasil sebagai berikut:  

1. **Precision (50%)**:
   - Dari semua rekomendasi yang diberikan oleh sistem, 50% di antaranya relevan.
   - Menunjukkan bahwa sistem memiliki tingkat kecermatan yang sedang dalam memilih film relevan.

2. **Recall (100%)**:
   - Dari seluruh film relevan yang tersedia dalam dataset, sistem berhasil menemukan semuanya.
   - Hasil ini menunjukkan bahwa sistem dapat menangkap semua film relevan.

3. **F1-Score (66%)**:
   - Kombinasi antara precision dan recall menghasilkan F1-Score sebesar 66%.
   - Hasil ini menunjukkan bahwa sistem memiliki keseimbangan yang cukup baik antara relevansi dan cakupan rekomendasi.

### **Pengaruh Threshold (Ambang Batas Kesamaan)**

- **Menaikkan Threshold**:
  - Precision akan meningkat karena hanya rekomendasi dengan skor similarity tinggi yang dianggap relevan.
  - Namun, recall cenderung menurun karena beberapa film relevan dengan skor similarity rendah akan terlewat.

- **Menurunkan Threshold**:
  - Recall akan meningkat karena lebih banyak film relevan terdeteksi, termasuk yang memiliki skor similarity rendah.
  - Namun, precision cenderung menurun karena rekomendasi yang kurang relevan juga akan dimasukkan.

### **Rekomendasi Perbaikan**

1. **Feature Engineering**:
   - Tambahkan atribut tambahan seperti **genre**, **tahun rilis**, **popularitas**, atau **rating** untuk memperkaya basis rekomendasi.
   - Fitur tambahan ini dapat memberikan konteks yang lebih baik dalam menilai relevansi.

2. **Eksperimen Threshold**:
   - Lakukan pengujian dengan berbagai nilai threshold untuk menemukan ambang batas yang memberikan keseimbangan optimal antara precision dan recall.
   - Untuk target precision minimal 75%, threshold dapat diatur lebih tinggi, misalnya di atas 0.3.

3. **Penggunaan Model Hybrid**:
   - Kombinasikan pendekatan **Content-Based Filtering** dengan **Collaborative Filtering** untuk menciptakan sistem rekomendasi yang lebih akurat dan personal.
   - Model hybrid dapat memanfaatkan data interaksi pengguna untuk melengkapi sistem berbasis konten.

4. **Optimasi Dataset**:
   - Tingkatkan cakupan dan kualitas dataset dengan menambahkan lebih banyak film, terutama yang populer, untuk memperbaiki representasi data.

Dengan perbaikan ini, diharapkan sistem dapat mencapai **precision minimal 75%** tanpa mengorbankan recall secara signifikan.
