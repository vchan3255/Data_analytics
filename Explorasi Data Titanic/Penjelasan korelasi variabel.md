# 📊 Explorasi data titanic
## File ini dibuat untuk mengetahui korelasi antara data dengan data lainnya sehingga menghasilkan informasi yang dapat dikelola ke depannya

<br>

### 🔎 Interpretasi Korelasi Titanic:
- Alasan kuat yang membuat korelasi titanic peluang selamatnya tinggi (positif): penumpang wanita memiliki peluang selamatnya tinggi.\
  peluang penumpang yang membeli tiket kelas 1 / fare mahal memiliki peluang selamatnya tinggi.
- Alasan kuat yang membuat korelasi titanic peluang selamatnya rendah (positif): penumpang pria memiliki peluang selamatnya rendah.\
  penumpang yang membeli tiket kelas 3 / fare murah memiliki peluang selamatnya rendah.
- Alasan yang memiliki pengaruh positif dan negatif: Embarked Cherbourg -> banyak kelas 1 -> survival naik.\
  Embarked Southampton -> banyak kelas 3 -> survival turun.
- Alasan yang lemah/tidak terlalu berpengaruh (negatif): penumpang dengan usia muda -> sedikit lebih banyak selamat.\
  Terlalu banyak keluarga (SibSp/Parch tinggi) -> survival turun.
 
<br>

### Cerita di Balik Korelasi Titanic 🚢
1. Sex <-> Survival (korelasi sangat kuat)\
Heatmap menunjukkan variabel sex_num berkorelasi tinggi dengan survived.\
Ceritanya: aturan “women and children first” yang membuat lebih banyak wanita selamat dibanding pria.\

2. Class <-> Fare <-> Survival\
Korelasi: class_num dan fare hampir mirror image artinya dua variabel memiliki pengaruh korelasi yang kuat tapi berlawanan arah (negatif) (kelas rendah → fare kecil, kelas tinggi → fare besar).\
Ceritanya: penumpang kelas 1 (tiket mahal) lebih dekat dengan sekoci, peluang selamatnya menjadi jauh lebih tinggi.\
Sebaliknya, penumpang kelas 3 dengan tiket murah dan berada di dek bawah menjadi terjebak sehingga memiliki survival rendah.

3. Embarked <-> Survival (korelasi tidak langsung)\
Angka: embarked punya korelasi dengan fare dan class.\
Ceritanya: penumpang dari Cherbourg (C) banyak kelas 1 -> survival tinggi.\
Sedangkan Southampton (S) mayoritas kelas 3 -> survival rendah.

4. SibSp & Parch <-> Family Size <-> Survival\
Angka: sibsp dan parch saling berkorelasi (keluarga besar).\
Ceritanya: keluarga kecil (2–4 orang) cenderung lebih selamat karena bisa saling bantu.\
Kalau sendirian -> tidak ada yang bantu.\
Kalau keluarga besar -> sulit menyelamatkan semua, survival menurun.\

5. Age <-> Survival (korelasi lemah tapi penting)\
Angka: age tidak terlalu berkorelasi dengan survival secara linear\
Ceritanya: bayi/anak kecil lebih diutamakan diselamatkan, orang dewasa laki-laki justru banyak yang tidak selamat. Jadi hubungannya lebih non-linear.

## ✨ Jadi heatmap memberikan angka hubungan antar variabel, sementara kisah Titanic menjelaskan kenapa angka itu muncul di dunia nyata.
Keduanya saling melengkapi:\
Angka -> bukti statistik.\
Cerita -> alasan logis & manusiawi.

---
[File RAW](https://colab.research.google.com/drive/1-8XgpdgzRZ3yL4nKs0G46cTKtPL1TybI#scrollTo=6Qi4dviBFgIf)
