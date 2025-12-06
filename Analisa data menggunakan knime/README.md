# LAPORAN ANALISA DATA MENGGUNAKAN KNIME

## Pendahuluan
Proyek ini dilakukan dengan membuat workflow di KNIME. Memiliki tujuan untuk mencari insight dan interpretasi dari sebuah dataset yaitu reading interest di Indonesia pada tahun 2020-2023, di mulai dari data preparation, kemudian data di proses, setelah itu di klasifikasikan, lalu data tersebut divisualisasikan sehingga mencapai tujuan yang diinginkan
Dataset berisi informasi tentang reading interest di Indonesia, variabel yang ada yaitu:
- Provinsi di Indonesia
- Tahun
- Frekuensi membaca tiap minggu
- Jumlah bacaan per kuartal
- Durasi membaca harian(dalam menit)
- Frekuensi akses internet per minggu
- Durasi internet harian(dalam menit)
- Tingkat kegemaran membaca
- Kategori tingkat kegemaran membaca(sedang dan tinggi)
Nama dataset: TGM 2020-2023_eng.csv, dataset diinputkan melalui  node *csv reader* di KNIME
---
## Data Preparation
Proses ini dilakukan untuk menyiapkan data agar siap di analisis dan di visualisasikan,
node yang digunakan:
- **CSV Reader**
digunakan untuk membaca dataset
- **Missing Value**
mengatasi nilai yang kosong pada dataset
---
## Data Process
Mengubah data yang bersih agar menjadi data yang bermanfaat dan siap untuk di modeling,
node yang digunakan:
- **Groupby**
meringkas data berdasarkan kelompok tertentu
- **Table Partitioner**
membagi data menjadi dua bagian
---
## Visualisasi Data
Tahapan ini untuk mencari insight dan interpretasi dari dataset,
node yang digunakan:
- **Statistics**
menampilkan ringkasan statistik seperti min, max, mean, median, dan standar deviasi
- **Line Plot**
melihat tren perubahan data sepanjang waktu
- **Bar Chart**
membandingkan jumlah/frekuensi antar kelompok
- **Pie Chart**
melihat proporsi dari keseluruhan
- **Scatter Plot**
melihat hubungan(korelasi) antar variabel
---
## Klasifikasi
Tujuannya mengelompokkan data ke dalam kategori yang sudah ditentukan sebelumnya,
menggunakan node:
- **Decision Tree Learner**
menganalisis data latihan untuk mencari sebab akibatnya
- **Decision Tree Predictor**
mengambil model(aturan) dari decision tree learner, menghasilkan kolom prediction
- **Decision Tree to Image**
memperlihatkan model dalam bentuk gambar
- **Scorer**
membandingkan kolom asli dengan kolom prediksi, lalu menghitung berapa data yang benar dan meleset

# Insight dan Interpretasi
Setelah melakukan tahapan analisis data, visualisasi data menghasilkan sebuah wawasan dan pandangan terhadap dataset yang sudah digunakan di antaranya:
1. Kita menjadi tahu tingkat kegemaran membaca di indonesia dari tahun ke tahun(2020-2023), selalu naik beberapa persen(line plot)
2. Orang yang sering mengakses internet ternyata tidak terganggu dan masih bisa membaca setiap minggu(scatter plot)
3. Tingkat kegemaran membaca tiap provinsi berbeda-beda dan tidak terlalu berbeda jauh(bar chart)
4. Mendapatkan 7 provinsi dengan tingkat kegemaran membaca yang tinggi(pie chart)
5. Kebanyakan provinsi memiliki tingkat kegemaran membaca dengan kategori sedang dibanding dengan kategori tinggi(pie chart)
6. Penggunaan internet yang tinggi tidak mematikan minat pembaca(scatter plot)
7. Orang yang membaca dengan durasi lama memiliki tingkat kegemaran membaca yang tinggi juga(scatter plot)
8. Orang yang memiliki durasi lama di internet juga bisa membaca dengan durasi yang lama(scatter plot)
9. Dari model decision tree, dapat diketahui bahwa pertengahan tahun 2023 ke bawah mayoritas memiliki tingkat kegemaran membaca yang tinggi sedangkan pertengahan tahun 2023 ke atas memiliki kategori tingkat kegemaran membaca yang sedang bahkan tidak ada provinsi yang masuk kategori tinggi(decision tree)
