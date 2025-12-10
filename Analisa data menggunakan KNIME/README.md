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
Digunakan untuk membaca dataset
<img width="1292" height="965" alt="image" src="https://github.com/user-attachments/assets/4d0f62f7-1da8-4193-a4d6-b096af48f2e5" />
mengupload dataset reading interest ke workflow di knime.
- **Missing Value**
Mengatasi nilai yang kosong pada dataset
<img width="855" height="790" alt="image" src="https://github.com/user-attachments/assets/aee5ab7c-b941-40a7-8a9c-b1029d9f8822" />
nilai yang kosong pada internet access frequency per week & daily internet duration diganti menjadi nilai tengahnya(median).
---
## Data Process
Mengubah data yang bersih agar menjadi data yang bermanfaat dan siap untuk di modeling,
node yang digunakan:
- **Groupby**
Meringkas data berdasarkan kelompok tertentu
<img width="1396" height="438" alt="image" src="https://github.com/user-attachments/assets/d50d0a00-4083-4c4d-82e6-3f4e6f7483c6" />
Di workflow yang dikerjakan, mengelompokkan data berdasarkan provinsi dengan rata-rata tingkat kegemaran membaca dan rata-rata durasi membaca harian,
<img width="1397" height="410" alt="image" src="https://github.com/user-attachments/assets/4801e211-f5e1-476a-a5e3-7039bc45a476" />
kemudian ada kelompok tahun dan kategori tingkat kegemaran membaca dengan menghitung provinsi yang ada dan rata-rata dari tingkat kegemaran membaca,
<img width="1396" height="427" alt="image" src="https://github.com/user-attachments/assets/5258904f-5c92-4000-b7a3-f52c9bd2e954" />
serta kelompok tahun berdasarkan rata-rata tingkat kegemaran membaca.

- **Table Partitioner**
Membagi data menjadi dua bagian
<img width="1393" height="434" alt="image" src="https://github.com/user-attachments/assets/5846a678-ff77-4d68-bb99-9b4ac60140f6" />
mengambil data menjadi 2 bagian 80% untuk dilatih, yang awalnya 140 kolom menjadi 112. 20% Dijadikan data test.
---
## Visualisasi Data
Tahapan ini untuk mencari insight dan interpretasi dari dataset,
node yang digunakan:
- **Statistics**
Menampilkan ringkasan statistik seperti min, max, mean, median, dan standar deviasi.
<img width="1896" height="739" alt="image" src="https://github.com/user-attachments/assets/d8e4c831-b6d6-48cb-9290-cba6c3b294c7" />
- **Line Plot**
Melihat tren perubahan data sepanjang waktu
<img width="1396" height="434" alt="image" src="https://github.com/user-attachments/assets/4a8d0d17-ee8e-4d75-93e4-c990b5148a7f" />
dari visualisasi ini dapat dilihat bahwa dari tahun 2020 sampai 2023 rata-rata tingkat kegemaran membaca naik.
- **Bar Chart**
Membandingkan jumlah/frekuensi antar kelompok
<img width="1395" height="445" alt="image" src="https://github.com/user-attachments/assets/957cf837-734e-491c-98ff-aba70351c211" />
dapat dilihat dari visualisasi ini perbandingan rata-rata tingkat kegemaran membaca tiap provinsi berbeda sedikit.
- **Pie Chart**
Melihat proporsi dari keseluruhan
<img width="1389" height="441" alt="image" src="https://github.com/user-attachments/assets/4d3d34c6-fcb0-4528-a154-c1341bc35cc8" />
dilihat dari pie chart di atas bahwa kategori tingkat kegemaran membaca ada 2 yaitu 90 sedang dan kategori kedua yaitu 50 tinggi,
<img width="1391" height="428" alt="image" src="https://github.com/user-attachments/assets/1e996493-14ed-4e07-85ab-b6b89760e753" />
dari pie chart di atas dapat disimpulkan 7 provinsi dengan rata-rata tingkat kegemaran membaca tertinggi.
- **Scatter Plot**
melihat hubungan(korelasi) antar variabel
<img width="1393" height="378" alt="image" src="https://github.com/user-attachments/assets/827bfae0-9d52-48aa-8c05-b2df4788b380" />
dari scatter plot diatas dapat disimpulkan bahwa orang yang sering mengakses internet harian tidak mempengaruhi orang tersebut untuk membaca per minggunya,
<img width="1391" height="384" alt="image" src="https://github.com/user-attachments/assets/b6f3c42d-f1c2-40d7-a40e-b38e13b04f35" />
orang yang mengakses internet harian ternyata mempunyai tingkat kegemaran membaca yang relatif tinggi juga,
<img width="1394" height="387" alt="image" src="https://github.com/user-attachments/assets/65ca3d2b-b9d1-4d11-aaa3-ce8190f47439" />
orang yang memiliki tingkat kegemaran membaca yang tinggi ternyata mempunyai durasi membaca harian yang tinggi juga,
<img width="1389" height="385" alt="image" src="https://github.com/user-attachments/assets/9aa2b682-5fd8-483e-9b9a-dbd897e29b6c" />
dapat dilihat dari scatter plot di atas bahwa orang yang memiliki durasi membaca yang tinggi ternyata juga mempunyai akses internet harian yang tinggi juga.

---
## Klasifikasi
Tujuannya mengelompokkan data ke dalam kategori yang sudah ditentukan sebelumnya,
menggunakan node:
- **Decision Tree Learner**
menganalisis data latihan untuk mencari sebab akibatnya
<img width="643" height="845" alt="image" src="https://github.com/user-attachments/assets/aa70f7cd-603e-4e39-a350-c72799e14f55" />
dari tabel partisi yang digunakan untuk membagi data, menggunakan learner untuk menciptakan model tabel bentuk tree.
- **Decision Tree Predictor**
mengambil model(aturan) dari decision tree learner, menghasilkan kolom prediction
<img width="1390" height="395" alt="image" src="https://github.com/user-attachments/assets/0e851338-2cc0-4368-a4a3-993b568a620f" />
menciptakan prediksi untuk kategori tingkat kegemaran membaca yang sedang dan tinggi, dari model tabel learner.
- **Decision Tree to Image**
memperlihatkan model dalam bentuk gambar
<img width="1001" height="777" alt="image" src="https://github.com/user-attachments/assets/59e3a307-499d-4106-ac51-f4c2f9734630" />
dapat dilihat dari model tabel tree diatas prediksi untuk pertengahan tahun 2023 kebawah memiliki 97.6% tingkat kegemaran membaca tinggi dan 2.4% sedang. Sedangkan pertengahan tahun 2023 ke atas 100% memiliki tingkat kegemaran membaca sedang.
- **Scorer**
membandingkan kolom asli dengan kolom prediksi, lalu menghitung berapa data yang benar dan meleset
<img width="1401" height="417" alt="image" src="https://github.com/user-attachments/assets/1eabf373-ecd4-4610-809e-fd34b5e52197" />
prediksi yang benar dan meleset,
<img width="1397" height="416" alt="image" src="https://github.com/user-attachments/assets/d6db93eb-4241-4d7e-a92f-177b6aa173f2" />
keakuratan scorer untuk memprediksi.
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
