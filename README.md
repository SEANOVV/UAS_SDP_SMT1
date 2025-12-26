# Tugas Analisis Statistik: Deskriptif, Korelasi, dan Regresi

## 1. Informasi Penyusun

- **Nama:** `PUTU NOVA RESTIAWAN`
- **NIM:** `2515091137`
- **Program Studi:** `SISTEM INFORMASI`
- **Mata Kuliah:** Statistika dan Probabilitas

---

## 2. Deskripsi Proyek

Pada bagian ini, jelaskan secara singkat dataset yang Anda gunakan. Apa saja variabel di dalamnya? Apa tujuan dari analisis yang Anda lakukan?

*Contoh:*
> Dataset yang digunakan adalah data `data_startup_saas.csv` yang berisi informasi tentang `Informasi yang diperoleh dari penelitian atau pengolahan data dapat memberikan gambaran yang cukup lengkap mengenai kondisi dan hasil yang diteliti. Melalui kuesioner atau dataset, peneliti dapat mengetahui profil responden, seperti karakteristik umum subjek penelitian, serta kondisi awal yang dimiliki sebelum diberikan perlakuan. Selain itu, data yang terkumpul juga dapat menunjukkan apakah variabel yang diteliti, misalnya permainan sudoku, memiliki pengaruh terhadap aspek tertentu seperti memori, konsentrasi, atau kemampuan berpikir. Dari hasil analisis, peneliti dapat melihat perbedaan sebelum dan sesudah perlakuan, menemukan hubungan antar variabel, serta menarik kesimpulan yang dapat dijadikan dasar rekomendasi untuk penelitian lanjutan maupun penerapan dalam bidang pendidikan atau pengembangan kemampuan kognitif.`. Variabel kunci dalam dataset ini meliputi `Pendapatan_Tahunan_Miliar_IDR`, `Biaya_Akusisi_Pelanggan_Juta_IDR`, dan `Nilai_Pelanggan_Juta_IDR`. Tujuan dari proyek ini adalah untuk memahami karakteristik data melalui statistik deskriptif, menguji hubungan antara `Pendapatan_Tahunan_Miliar_IDR` dan `Biaya_Akusisi_Pelanggan_Juta_IDR` melalui analisis korelasi, serta memprediksi `Nilai_Pelanggan_Juta_IDR` menggunakan `Pendapatan_Tahunan_Miliar_IDR` sebagai prediktor melalui analisis regresi.

---

## 3. Struktur Proyek

Proyek ini diorganisir ke dalam beberapa folder:
- `/data`: Berisi dataset mentah yang digunakan untuk analisis.
- `/scripts`: Berisi semua skrip R yang digunakan dalam analisis, diurutkan berdasarkan alur kerja.
- `/results`: Berisi output dari analisis, seperti plot, gambar, atau tabel ringkasan.

---

## 4. Cara Menjalankan Analisis

Untuk mereproduksi hasil analisis ini, ikuti langkah-langkah berikut:
1. Pastikan Anda memiliki R dan RStudio terinstal.
2. Buka proyek R ini di RStudio.
3. Instal paket yang diperlukan dengan menjalankan perintah berikut di konsol R:
   ```R
   # install.packages(c("tidyverse", "corrplot", "knitr"))
   ```
4. Jalankan skrip di dalam folder `/scripts` secara berurutan, mulai dari `01_data_preparation.R` hingga `05_analisis_regresi.R`.

---

## 5. Hasil dan Interpretasi

Di bagian ini, mahasiswa diharapkan untuk menyajikan dan menginterpretasikan hasil dari setiap tahap analisis.

### 5.1. Statistik Deskriptif
- **Ukuran Pemusatan (Mean, Median, Modus):**
  - *Tabel atau ringkasan...*
- Mean = 31.88
- Median = 31.3
- Modus = 1.87
  - *Interpretasi:* Jelaskan apa arti dari nilai-nilai tersebut terkait dengan data Anda.
  - Nilai mean sebesar 31,88 menunjukkan rata-rata dari seluruh data yang dikumpulkan, sehingga dapat dikatakan bahwa secara umum nilai data berada di kisaran tersebut. Median sebesar 31,3 menandakan bahwa 50% data berada di bawah nilai 31,3 dan 50% lainnya berada di atasnya, sehingga median ini menggambarkan titik tengah sebaran data. Sementara itu, modus sebesar 1,87 menunjukkan nilai yang paling sering muncul dalam data, yang mengindikasikan adanya kecenderungan pengulangan pada nilai tersebut. Perbedaan antara mean, median, dan modus menunjukkan bahwa sebaran data tidak sepenuhnya simetris, sehingga kemungkinan terdapat variasi atau pencilan (outlier) yang memengaruhi nilai rata-rata data.
- **Ukuran Sebaran (Standar Deviasi, Range, Kuartil):**
  - *Tabel atau ringkasan...*
  - Standar Devisiasi = 19.79
  - Range = 66.89
  - Kuartil = Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
              1.00   14.31   31.30   31.88   49.04   66.89 
  - *Interpretasi:* Jelaskan seberapa menyebar data Anda berdasarkan nilai-nilai ini.
  - Nilai standar deviasi sebesar 19,79 menunjukkan bahwa data memiliki tingkat penyebaran yang cukup besar dari nilai rata-ratanya, artinya nilai-nilai dalam data tidak terkonsentrasi di satu titik saja, tetapi tersebar cukup jauh. Range sebesar 66,89 menandakan selisih yang sangat lebar antara nilai minimum dan maksimum, sehingga variasi data tergolong tinggi. Berdasarkan nilai kuartil, terlihat bahwa data minimum berada pada angka 1,00 dan meningkat hingga kuartil pertama sebesar 14,31, yang menunjukkan adanya sebaran data yang cukup lebar pada bagian bawah. Median sebesar 31,30 berada relatif dekat dengan mean 31,88, mengindikasikan bahwa sebaran data secara umum cukup seimbang di bagian tengah. Kuartil ketiga sebesar 49,04 hingga nilai maksimum 66,89 menunjukkan bahwa data juga menyebar luas pada bagian atas. Secara keseluruhan, nilai-nilai ini menunjukkan bahwa data memiliki variasi yang tinggi dengan penyebaran yang cukup luas di seluruh rentang nilai.
- **Visualisasi (Histogram/Boxplot):**
  - *Sematkan gambar plot dari folder /results...*
  - ![alt text](https://github.com/SEANOVV/UAS_SDP_SMT1/blob/main/results/boxplot_Pendapatan_Tahunan_Miliar_IDR.png)
  - *Interpretasi:* Jelaskan wawasan apa yang Anda dapatkan dari bentuk distribusi data.
  - Berdasarkan boxplot Pendapatan Tahunan (dalam miliar IDR), terlihat bahwa distribusi data memiliki penyebaran yang cukup luas. Garis median berada di sekitar nilai tengah kotak, yang menunjukkan bahwa sebagian besar data terkonsentrasi di sekitar nilai tengah pendapatan. Namun, panjang kotak (jarak antara kuartil pertama dan kuartil ketiga) yang cukup besar mengindikasikan adanya variasi pendapatan yang tinggi di antara objek yang diamati. Whisker yang memanjang ke nilai minimum dan maksimum menunjukkan bahwa terdapat perbedaan pendapatan yang cukup ekstrem, dari nilai yang sangat rendah hingga sangat tinggi. Tidak terlihat titik pencilan (outlier) yang mencolok, sehingga dapat disimpulkan bahwa meskipun data bervariasi, variasi tersebut masih berada dalam rentang yang wajar. Secara keseluruhan, bentuk distribusi ini menunjukkan bahwa pendapatan tahunan tersebar lebar dengan tingkat keragaman yang cukup tinggi.

### 5.2. Uji Normalitas
- **Hasil Uji Shapiro-Wilk:**
  - *Nilai p-value...*
  - p-value = 1.497e-14
  - *Interpretasi:* Apakah data Anda terdistribusi normal berdasarkan hasil uji? Apa implikasinya?
  - Nilai p-value sebesar 1,497 × 10⁻¹⁴ menunjukkan bahwa nilai tersebut jauh lebih kecil dari tingkat signifikansi yang umum digunakan (α = 0,05). Oleh karena itu, hipotesis nol yang menyatakan bahwa data terdistribusi normal ditolak. Hal ini berarti bahwa data yang dianalisis tidak mengikuti distribusi normal. Implikasinya, peneliti perlu berhati-hati dalam memilih metode analisis selanjutnya, khususnya jika metode tersebut mensyaratkan asumsi normalitas. Dalam kondisi ini, peneliti disarankan untuk menggunakan metode statistik nonparametrik atau melakukan transformasi data agar analisis yang dilakukan tetap valid dan hasil yang diperoleh dapat dipertanggungjawabkan secara statistik.
- **Plot Q-Q:**
  - *Sematkan gambar plot dari folder /results...*
  - ![alt text](https://github.com/SEANOVV/UAS_SDP_SMT1/blob/main/results/qqplot_Pendapatan_Tahunan_Miliar_IDR.png)
  - *Interpretasi:* Apakah titik-titik data mengikuti garis lurus? Apa artinya?
  - Berdasarkan Q–Q plot yang ditampilkan, terlihat bahwa titik-titik data tidak sepenuhnya mengikuti garis lurus yang merepresentasikan distribusi normal. Pada bagian tengah, beberapa titik masih relatif mendekati garis, namun pada bagian kuantil rendah dan kuantil tinggi terlihat penyimpangan yang cukup jelas, di mana titik-titik data melengkung dan menjauh dari garis referensi. Pola ini menunjukkan bahwa distribusi data tidak bersifat normal, serta mengindikasikan adanya ketidaksimetrian atau kemencengan (skewness) pada data. Artinya, data pendapatan tahunan yang dianalisis memiliki pola distribusi yang menyimpang dari distribusi normal, terutama pada nilai ekstrem. Temuan ini sejalan dengan hasil uji normalitas sebelumnya yang menunjukkan nilai p-value sangat kecil. Dengan demikian, dapat disimpulkan bahwa asumsi normalitas tidak terpenuhi, sehingga dalam analisis lanjutan sebaiknya digunakan metode statistik yang tidak mensyaratkan distribusi normal atau dilakukan transformasi data agar hasil analisis tetap valid.

### 5.3. Analisis Korelasi
- **Nilai Koefisien Korelasi:**
  - *Nilai r...*
  - (r) = 0.996
  - *Interpretasi:* Seberapa kuat dan apa arah hubungan antara dua variabel yang Anda uji? (misalnya, korelasi positif kuat, negatif lemah, atau tidak ada korelasi).
  - Nilai koefisien korelasi (r) sebesar 0,996 menunjukkan bahwa hubungan antara kedua variabel yang diuji sangat kuat dan bersifat positif. Hal ini berarti bahwa ketika nilai salah satu variabel meningkat, nilai variabel lainnya cenderung ikut meningkat secara konsisten. Besarnya nilai r yang mendekati 1 mengindikasikan tingkat keterkaitan yang hampir sempurna, sehingga perubahan pada satu variabel sangat erat hubungannya dengan perubahan pada variabel lainnya. Dengan demikian, dapat disimpulkan bahwa kedua variabel memiliki korelasi positif yang sangat kuat, meskipun perlu diingat bahwa korelasi tidak selalu menunjukkan hubungan sebab-akibat.
- **Visualisasi (Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
  -  ![alt text](https://github.com/SEANOVV/UAS_SDP_SMT1/blob/main/results/scatterplot_Pendapatan_Tahunan_Miliar_IDR_vs_Biaya_Akuisisi_Pelanggan_Juta_IDR.png)
  - *Interpretasi:* Apakah pola pada scatter plot mendukung hasil koefisien korelasi?
  - Berdasarkan scatter plot yang ditampilkan, pola sebaran titik-titik data mendukung hasil koefisien korelasi yang sangat kuat dan positif (r = 0,996). Titik-titik data terlihat membentuk pola yang hampir linear dan mengikuti arah garis tren, yang menunjukkan bahwa peningkatan pendapatan tahunan diikuti oleh peningkatan biaya akuisisi pelanggan. Sebaran titik yang relatif rapat di sekitar garis tren mengindikasikan hubungan yang konsisten dan kuat antara kedua variabel tersebut. Dengan demikian, visualisasi scatter plot ini memperkuat hasil analisis korelasi, bahwa terdapat hubungan positif yang sangat kuat antara pendapatan tahunan dan biaya akuisisi pelanggan.

### 5.4. Analisis Regresi
- **Model Regresi:**
  - *Persamaan regresi: Y = b0 + b1*X*
  - (b0) = 1.37
  - (b1) = 1.01
  - Y = 1.37 + 1.01X
  - *Interpretasi:* Jelaskan arti dari koefisien intercept (b0) dan slope (b1) dalam konteks data Anda.
  - Nilai **intercept (b₀) sebesar 1,37** menunjukkan bahwa ketika variabel independen (X) bernilai nol, maka nilai variabel dependen (Y) diperkirakan sebesar 1,37. Dalam konteks data ini, hal tersebut dapat diartikan sebagai **nilai dasar (baseline)** dari variabel (Y) ketika pendapatan tahunan tidak mengalami peningkatan, yaitu tetap terdapat biaya akuisisi pelanggan sebesar 1,37 (dalam satuan yang digunakan). Sementara itu, nilai **slope (b₁) sebesar 1,01** menunjukkan bahwa setiap kenaikan **1 satuan pada variabel (X)** akan diikuti oleh **kenaikan sebesar 1,01 satuan pada variabel (Y)**. Artinya, terdapat hubungan positif yang sangat kuat, di mana peningkatan pendapatan tahunan akan diikuti oleh peningkatan biaya akuisisi pelanggan secara hampir sebanding. Dengan demikian, persamaan regresi (Y = 1,37 + 1,01X) menggambarkan hubungan linear yang kuat antara kedua variabel, di mana perubahan pada pendapatan tahunan berpengaruh langsung terhadap besarnya biaya akuisisi pelanggan.

- **Evaluasi Model (R-squared):**
  - *Nilai R-squared...*
  - R-squared = 0.991 atau 99.1 %
  - *Interpretasi:* Berapa persen variasi dari variabel dependen yang dapat dijelaskan oleh model regresi Anda?
  - Nilai R-squared sebesar 0,991 atau 99,1% menunjukkan bahwa sebesar 99,1% variasi pada variabel dependen dapat dijelaskan oleh model regresi yang digunakan. Artinya, hampir seluruh perubahan pada variabel dependen dipengaruhi dan dapat diterangkan oleh variabel independen dalam model tersebut. Sementara itu, sisanya sebesar 0,9% dipengaruhi oleh faktor lain di luar model atau oleh kesalahan (error). Dengan nilai R-squared yang sangat tinggi ini, dapat disimpulkan bahwa model regresi memiliki tingkat kecocokan (goodness of fit) yang sangat baik dalam menjelaskan hubungan antara kedua variabel.
- **Visualisasi (Garis Regresi pada Scatter Plot):**
  - *Sematkan gambar plot dari folder /results...*
  - ![alt text](https://github.com/SEANOVV/UAS_SDP_SMT1/blob/main/results/plot_regresi_Pendapatan_Tahunan_Miliar_IDR_vs_Biaya_Akuisisi_Pelanggan_Juta_IDR.png)
  - *Interpretasi:* Jelaskan bagaimana garis regresi merepresentasikan hubungan antara variabel.
  - Garis regresi pada grafik tersebut merepresentasikan hubungan linear antara pendapatan tahunan dan biaya akuisisi pelanggan. Garis yang menanjak dari kiri ke kanan menunjukkan bahwa hubungan kedua variabel bersifat positif, artinya setiap peningkatan pendapatan tahunan cenderung diikuti oleh peningkatan biaya akuisisi pelanggan. Kedekatan sebagian besar titik data terhadap garis regresi menunjukkan bahwa model mampu menggambarkan pola hubungan antarvariabel dengan sangat baik. Selain itu, garis regresi berfungsi sebagai estimasi nilai rata-rata variabel dependen pada setiap nilai variabel independen. Dengan nilai Adjusted R-squared yang sangat tinggi (0,991), garis tersebut menunjukkan bahwa model memiliki tingkat kecocokan yang sangat baik, sehingga perubahan pada pendapatan tahunan dapat menjelaskan hampir seluruh variasi biaya akuisisi pelanggan. Secara keseluruhan, garis regresi ini memperlihatkan bahwa hubungan antara kedua variabel bersifat kuat, konsisten, dan dapat digunakan untuk melakukan prediksi dalam rentang data yang dianalisis.

---

## 6. Kesimpulan
Berdasarkan hasil analisis statistik deskriptif, uji normalitas, analisis korelasi, dan analisis regresi yang telah dilakukan, dapat disimpulkan bahwa data yang dianalisis memiliki karakteristik yang dapat dijelaskan secara sistematis dan menyeluruh. Statistik deskriptif memberikan gambaran awal mengenai kondisi data melalui ukuran pemusatan dan penyebaran, sehingga dapat diketahui kecenderungan nilai, tingkat variasi, serta pola distribusi data yang muncul. Hasil uji normalitas selanjutnya menunjukkan apakah data memenuhi asumsi distribusi normal, yang sangat penting dalam menentukan kelayakan penggunaan metode statistik parametrik serta meningkatkan keakuratan interpretasi hasil analisis. Analisis korelasi memperlihatkan adanya hubungan antara variabel-variabel yang diteliti, baik dari segi arah hubungan (positif atau negatif) maupun tingkat kekuatannya, sehingga membantu dalam memahami keterkaitan antarvariabel secara kuantitatif. Temuan ini kemudian diperkuat melalui analisis regresi yang bertujuan untuk mengetahui sejauh mana variabel independen mampu memengaruhi atau memprediksi variabel dependen. Melalui model regresi yang dihasilkan, dapat dijelaskan makna koefisien regresi serta besarnya kontribusi variabel bebas terhadap variasi variabel terikat yang ditunjukkan oleh nilai koefisien determinasi. Secara keseluruhan, rangkaian analisis yang dilakukan tidak hanya memberikan pemahaman deskriptif mengenai data, tetapi juga menghasilkan pemahaman analitis dan prediktif yang lebih mendalam. Dengan demikian, hasil penelitian ini dapat dijadikan sebagai dasar yang kuat dalam penarikan kesimpulan, mendukung pengambilan keputusan yang lebih objektif, serta menjadi referensi awal bagi penelitian selanjutnya yang relevan dan lebih mendalam.

Rangkum temuan utama dari analisis Anda dalam beberapa kalimat. Apa wawasan paling penting yang Anda peroleh?
