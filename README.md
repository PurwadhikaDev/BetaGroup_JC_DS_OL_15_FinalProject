# Background

Antara tahun 2015 hingga 2017, industri perhotelan di Portugal mengalami pertumbuhan yang signifikan, didukung oleh peningkatan jumlah wisatawan internasional dan pengembangan infrastruktur pariwisata. Selama periode ini, Portugal menjadi salah satu tujuan wisata utama di Eropa, dengan kontribusi sektor pariwisata terhadap GDP mencapai sekitar 20% pada 2017. Strategi diversifikasi pasar yang dilakukan pemerintah berhasil mengurangi ketergantungan historis pada pasar Inggris, menarik lebih banyak wisatawan dari negara seperti Spanyol, Prancis, Jerman, dan pasar-pasar baru seperti Kanada dan Brasil [link text](https://horwathhtl.com/publication/market-report-portugal-market-overview/). Data yang berasal dari Kaggle [link text](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand/data) dan Science Direct [link text](https://www.sciencedirect.com/science/article/pii/S2352340918315191) ini memberikan wawasan mengenai pola pemesanan, durasi tinggal, dan perilaku pembatalan, yang penting bagi pengelolaan operasional hotel.

Karena hotel memiliki inventaris tetap dan menjual “produk” yang mudah rusak, sebagai cara untuk menyediakan kamar yang tepat bagi tamu yang tepat, pada waktu yang tepat, hotel menerima pemesanan di muka. Pemesanan merupakan kontrak antara pelanggan dan hotel (Talluri & Van Ryzin, 2004). Kontrak ini memberikan pelanggan hak untuk menggunakan layanan di masa mendatang dengan harga yang telah ditetapkan, biasanya dengan opsi untuk membatalkan kontrak sebelum layanan diberikan. Meskipun pemesanan di muka dianggap sebagai prediktor utama kinerja prakiraan hotel (Smith, Parsa, Bujisic, & van der Rest, 2015), opsi untuk membatalkan layanan ini menempatkan risiko pada pihak hotel, karena hotel harus menjamin kamar bagi pelanggan yang memenuhi pemesanan mereka, tetapi pada saat yang sama, harus menanggung biaya peluang dari kapasitas kosong ketika pelanggan membatalkan pemesanan atau tidak muncul (Talluri & Van Ryzin, 2004). Pembatalan terjadi apabila pelanggan mengakhiri kontrak sebelum kedatangannya, sedangkan ketidakhadiran terjadi apabila pelanggan tidak memberi tahu pihak hotel dan gagal check-in. [link text](https://www.researchgate.net/publication/320625331_Predicting_hotel_booking_cancellations_to_decrease_uncertainty_and_increase_revenue)


# Problem Statement
Pembatalan pemesanan hotel telah menjadi tantangan besar dalam industri perhotelan, memengaruhi akurasi prakiraan permintaan, efisiensi operasional, dan pendapatan. Ketidakmampuan untuk mengantisipasi pembatalan berisiko menyebabkan kamar kosong yang tidak terpakai atau, sebaliknya, overbooking, yang dapat merusak reputasi hotel dan memengaruhi pengalaman tamu secara negatif.

  Dalam menghadapi masalah ini, penerapan teknologi machine learning menjadi solusi potensial yang sangat relevan. Dengan kemampuannya untuk menganalisis pola data yang kompleks, machine learning dapat membantu hotel membangun model prediktif yang lebih akurat dibandingkan pendekatan konvensional. Teknologi ini memungkinkan pengolahan data besar secara efisien untuk mengidentifikasi pola tersembunyi dan atribut utama yang memengaruhi pembatalan.

   Untuk itu, penelitian ini mengajukan beberapa pertanyaan utama:
   1. Faktor Utama:
    - Apa saja variabel atau atribut yang paling memengaruhi kemungkinan pembatalan pemesanan?
   2.  Akurasi Model:
    - Sejauh mana model machine learning dapat memprediksi pembatalan pemesanan dengan tingkat akurasi yang tinggi?
    - Bagaimana performa model diukur berdasarkan metrik utama seperti recall dan precision?
   3. Keunggulan Machine Learning:
    - Bagaimana penerapan machine learning meningkatkan kemampuan analisis dibandingkan metode konvensional dalam industri hotel?

# Goals

Tujuan utama dari proyek ini adalah untuk mengembangkan model Machine Learning yang mampu memprediksi kemungkinan pembatalan pemesanan di hotel dibandingkan dengan metode konvensional (rule based non Machine Learning) yang memperoleh nilai f-1 score sebesar 0.48. Dengan model ini, manajemen hotel dapat lebih proaktif dalam mengantisipasi jumlah pembatalan yang mungkin terjadi, sehingga membantu dalam perencanaan dan pengambilan keputusan operasional yang lebih baik. Dengan prediksi yang akurat, hotel dapat menerapkan strategi mitigasi seperti menetapkan kebijakan deposit yang sesuai, merancang promosi khusus, atau menyesuaikan inventaris kamar.

  Model ini diharapkan dapat mengidentifikasi variabel atau atribut yang paling memengaruhi keputusan pembatalan pemesanan. Hal ini memungkinkan manajemen untuk memahami faktor-faktor yang memicu pembatalan dan mengambil langkah-langkah pencegahan yang lebih tepat, sehingga dapat meningkatkan tingkat okupansi dan mengoptimalkan pengalaman pelanggan secara keseluruhan.

# Analytical Approach

Analisis dimulai dengan eksplorasi data untuk memahami distribusi variabel dan korelasi antara variabel prediktor dengan pembatalan. Berikut tahapan pendekatan analitis yang dapat diambil:

  1.  Data Understanding: informasi data, statistic deskriptif, jumlah missing value, dan distribusi data secara keseluruhan
  2.  Data Cleaning: menangani missing values, duplicated values, anomalies, data leakage, dan outliers.
  3.  Exploratory Data Analysis (EDA): Analisis visualisasi untuk memahami pola dan korelasi antar variabel (Q&A based).
  4.  Data Preparation, Model Development untuk Machine Learning, Hyperparameter Tuning, Feature Importance, Estimasi Keuntungan, dan Limitasi.
  5.  Kesimpulan dan Rekomendasi.


# Limitasi

Berdasarkan semua informasi limitasi untuk False Positve, False Negative, True Positive, dan True Negative. Dapat kita simpulkan bahwa:

1. False Positive (FP)

  Kesalahan False Positive terjadi ketika model memprediksi pembatalan (canceled), tetapi sebenarnya tidak ada pembatalan.

  - Karakteristik utama:

    - Data cenderung berasal dari City Hotel dengan tamu domestik, memesan melalui agen perjalanan online (Online TA) tanpa deposit (No Deposit), dan tidak memiliki permintaan khusus.
    - Tamu baru dengan riwayat reservasi yang bersih (tidak pernah membatalkan atau mengubah reservasi sebelumnya).
    - Waktu kedatangan: pertengahan bulan Agustus, musim panas (Summer), hari Senin, dengan reservasi dilakukan pada bulan Februari.
    - Fitur lainnya seperti: Lead time pendek (99-100 hari), ADR moderat (120.5), dan durasi menginap singkat (1 hari di akhir pekan, 2-3 hari di hari kerja).

  - Implikasi limitasi:

    - Model memiliki kecenderungan untuk salah mengidentifikasi tamu domestik yang memesan melalui agen perjalanan sebagai tamu yang kemungkinan akan membatalkan, meskipun faktanya mereka tidak membatalkan.

    - Hal ini menunjukkan bahwa model mungkin terlalu sensitif terhadap market segment Online TA dan City Hotel, sehingga menghasilkan lebih banyak FP.

2. False Negative (FN)

  Kesalahan False Negative terjadi ketika model tidak memprediksi pembatalan (tidak canceled), tetapi pembatalan sebenarnya terjadi.

  - Karakteristik utama:

    - Sama seperti False Positive, sebagian besar data berasal dari City Hotel, dengan tamu baru yang memesan melalui agen perjalanan online tanpa deposit.
    - Waktu kedatangan: pertengahan bulan Agustus, musim panas (Summer), hari Senin, dengan reservasi dilakukan pada bulan Januari.
    - Fitur lainnya seperti: Lead time moderat (73 hari), ADR moderat (117.6), dan durasi menginap singkat (1 hari di akhir pekan, 2-3 hari di hari kerja).

  - Implikasi limitasi:

    - Model cenderung kurang sensitif terhadap karakteristik tamu dengan pola pemesanan pendek/moderat dan musim tertentu (Summer), sehingga mengakibatkan tidak memprediksi pembatalan meskipun ada kecenderungan untuk membatalkan.
    - Hal ini menunjukkan model perlu dioptimalkan untuk lebih baik mengenali pola dari tamu yang benar-benar membatalkan.

3. True Positive (TP)

    Klasifikasi True Positive terjadi ketika model memprediksi pembatalan (canceled) dan pembatalan benar-benar terjadi.

    - Karakteristik utama:

      - Tamu yang benar-benar membatalkan biasanya memiliki Lead time yang panjang (118-119 hari) dan berasal dari City Hotel.
      - Reservasi dilakukan melalui agen perjalanan online tanpa deposit, dan tamu baru dengan riwayat reservasi bersih.
      - Waktu kedatangan: pertengahan bulan Agustus, musim panas (Summer), hari Selasa, dengan reservasi dilakukan pada bulan Januari.
      - Fitur lainnya seperti: ADR moderat (120.94), durasi menginap singkat (1 hari di akhir pekan, 3 hari di hari kerja), tanpa permintaan khusus.

    - Implikasi limitasi:

      - Model sudah cukup baik dalam memprediksi pembatalan dengan karakteristik ini, tetapi cenderung mengandalkan pola seperti lead time panjang dan musim tertentu (Summer).
      - Model mungkin kurang fleksibel untuk mengidentifikasi pembatalan di luar pola ini.

4. True Negative (TN)

    Klasifikasi True Negative terjadi ketika model memprediksi tidak ada pembatalan (not canceled), dan memang tidak ada pembatalan.

    - Karakteristik utama:

      - Sama seperti kategori lain, sebagian besar data berasal dari City Hotel dengan tamu domestik/internasional yang memesan melalui agen perjalanan online tanpa deposit.
      - Waktu kedatangan: pertengahan bulan Agustus, musim panas (Summer), hari Selasa, dengan reservasi dilakukan pada bulan Januari.
      - Fitur lainnya seperti: Lead time pendek (65 hari), ADR lebih rendah (102.12), durasi menginap singkat (1 hari di akhir pekan, 2 hari di hari kerja), tanpa permintaan khusus.

    - Implikasi limitasi:

      - Model cukup akurat dalam mengenali tamu yang tidak akan membatalkan reservasi, terutama untuk tamu dengan lead time pendek, riwayat reservasi bersih, dan tanpa permintaan khusus.
      - Namun, seperti pada kategori lainnya, model mungkin terlalu bergantung pada pola tertentu.


# Kesimpulan

## 5.1 Kesimpulan Model:

**Faktor Utama**:

1.  **Variabel atau atribut yang paling memengaruhi pembatalan pemesanan**:
  Berdasarkan analisis, variabel yang paling memengaruhi kemungkinan pembatalan pemesanan adalah:

  - Market Segment (Online TA): Pelanggan yang memesan melalui Online Travel Agents (OTA) memiliki kecenderungan lebih tinggi untuk membatalkan reservasi.
  - Required Car Parking Spaces: Pelanggan yang membutuhkan tempat parkir menunjukkan pola tertentu dalam pembatalan reservasi.
  - Deposit Type (Non-Refundable): Ketentuan deposit yang tidak dapat dikembalikan memengaruhi keputusan pelanggan dalam membatalkan pemesanan.
  - Is Overseas: Tamu internasional cenderung lebih rentan terhadap pembatalan karena ketidakpastian dalam rencana perjalanan.

**Akurasi Model**:

2.  **Tingkat akurasi model dalam memprediksi pembatalan pemesanan**: Model terbaik, XGBoost Classifier, menunjukkan akurasi sebesar 87% pada data train dan 84% pada data test. Hal ini menunjukkan bahwa model mampu menangkap pola pembatalan dengan baik pada sebagian besar data.

3.  **Performa model berdasarkan metrik utama seperti recall dan precision**:

  - Pada data test:

      Precision:

      Untuk kelas "0" (tidak membatalkan): 87%

      Untuk kelas "1" (membatalkan): 73%

      Recall:
    
      Untuk kelas "0": 91%

      Untuk kelas "1": 65%

      Dengan F1-score sebesar 0.69 untuk kelas pembatalan (kelas "1"), model memiliki keseimbangan yang cukup baik antara precision dan recall, meskipun recall untuk kelas "1" sedikit lebih rendah.

**Keunggulan Machine Learning**:

4.  **Penerapan machine learning dibandingkan metode konvensional**:

    - Rule-Based Model: Menggunakan fitur yang secara statistik memiliki korelasi tertinggi terhadap pembatalan (lead_time dan market_segment). Model ini hanya mencapai F1-score sebesar 0.48, menunjukkan keterbatasan dalam menangkap kompleksitas data.

    - Machine Learning Model: Dengan menggunakan metode SMOTE untuk penyeimbangan data dan XGBoost Classifier sebagai model terbaik, diperoleh F1-score sebesar 0.6866 setelah tuning.

    - Keunggulan Utama Machine Learning:
      
      - Kemampuan menangkap pola kompleks: Machine learning dapat menganalisis interaksi antar fitur yang tidak terlihat dengan metode konvensional.

      - Optimisasi melalui tuning: Hyperparameter tuning dan balancing data meningkatkan performa model secara signifikan.

      - Fleksibilitas data: Model mampu menangani berbagai jenis data (numerik dan kategorikal) melalui proses encoding yang optimal.

**Kesimpulan**:

Machine learning terbukti memberikan keunggulan dalam prediksi pembatalan pemesanan, dengan hasil yang lebih akurat dan metrik yang lebih baik dibandingkan metode rule-based. Model XGBoost Classifier yang digunakan mampu menangkap pola-pola penting dalam data, menjadikannya solusi yang efektif untuk analisis pembatalan pemesanan.

## 5.2.1 Rekomendasi bagi Manajemen Hotel based on Machine Learning Model:

Berdasarkan analisis implikasi dari False Positive dan False Negative pada prediksi pembatalan reservasi, berikut adalah rekomendasi strategis bagi hotel untuk mengelola risiko serta memaksimalkan keuntungan:

1. Mengurangi Risiko False Positive (Overbooking yang Tidak Tepat)
  - Kebijakan Overbooking yang Lebih Terukur
    
    - Gunakan prediksi pembatalan model sebagai guideline, tetapi kombinasikan dengan data historis tingkat pembatalan untuk menentukan tingkat overbooking optimal.
    - Terapkan overbooking hanya pada musim atau periode tertentu (misalnya, high season) dengan tingkat pembatalan yang tinggi berdasarkan data sebelumnya.

  - Meningkatkan Fleksibilitas Manajemen Kamar

    - Siapkan backup rooms untuk kasus overbooking, seperti kamar yang jarang digunakan.
    - Bangun kemitraan strategis dengan hotel lain di sekitar untuk menangani relokasi tamu secara efisien.

  - Strategi Komunikasi untuk Mitigasi Risiko Reputasi

    - Jika terjadi overbooking, tawarkan kompensasi yang menarik (upgrade kamar gratis pada kunjungan berikutnya, diskon, atau layanan tambahan) untuk menjaga kepuasan tamu.
    - Aktifkan tim layanan pelanggan khusus untuk menangani keluhan terkait overbooking dengan cepat.

2. Mengurangi Risiko False Negative (Kamar Kosong yang Tidak Terserap)
  - Kebijakan Pembatalan yang Adaptif

    - Terapkan kebijakan pembatalan progresif (tiered cancellation policy), seperti:
      - Refund penuh untuk pembatalan >7 hari sebelum check-in.
      - Refund parsial untuk pembatalan 3-7 hari sebelum check-in.
      - Tidak ada refund untuk pembatalan mendadak (<3 hari).

    - Tawarkan fleksibilitas tambahan seperti reschedule gratis agar tamu tidak sepenuhnya membatalkan reservasi.

  - Strategi Penjualan Kamar Kosong

    - Gunakan platform pemesanan last-minute untuk memasarkan kamar kosong dengan harga diskon.
    - Berikan penawaran khusus untuk segmen tamu lokal (staycation deals).

  - Pendekatan Dinamis untuk Pemesanan Grup atau Korporat

    - Fokuskan promosi ke tamu grup atau korporat yang lebih stabil dan memiliki probabilitas pembatalan lebih rendah.


3.  Mitigasi Risiko Finansial dan Reputasi
  - Asuransi Pembatalan Reservasi
    
      - Kerja sama dengan penyedia asuransi untuk menawarkan opsi asuransi pembatalan kepada tamu saat melakukan reservasi.
      - Biaya asuransi dapat membantu menutupi kerugian finansial akibat pembatalan mendadak.

  - Manajemen Ulasan dan Reputasi

      - Pantau dan tanggapi ulasan di platform secara aktif untuk memitigasi dampak negatif pembatalan atau overbooking.
      - Berikan transparansi penuh terkait kebijakan pembatalan agar tamu memahami dan merasa adil.

Kesimpulan

Rekomendasi ini bertujuan untuk mencapai keseimbangan antara efisiensi operasional, pengalaman tamu, dan profitabilitas. Dengan mengoptimalkan prediksi model, kebijakan yang fleksibel, dan komunikasi yang baik, hotel dapat meminimalkan dampak negatif dari false positive dan false negative secara signifikan.

## 5.2.2 Rekomendasi bagi Manajemen Hotel based on EDA:

Berdasarkan analisis dataset hotel booking demand, terdapat beberapa rekomendasi strategis yang dapat diimplementasikan oleh hotel di Portugal untuk mengurangi pembatalan reservasi dan memaksimalkan pendapatan berdasarkan hasil dari Explanatory Data Analysis:

**Berdasarkan Karkterisitk Waktu**
- Beberapa hal yang dapat pihak hotel lakukan untuk dapat meminimalisir pembatalan kamar hotel yang telah dilakukan dengan berfokus kepada promosi musiman atau dengan katalain hotel dapat memberikan penawaran diskon ataupun harga menarik sesuai dengan musim ketika customer hadir untuk check-in ataupun bisa memberikan discount untuk musim dimana customer tersebut menginap. Selain itu pihak hotel dapat memberikan beberapa kebijakan dalam melakukan pembatalan seperti customer yang melakukan pembatalan pada h-10 kehadiran tidak akan mendapatkan pengembalian dana, ataupun pihak hotel juga dapat melakukan pengenaan biaya pembatalan yang dilakukan oleh customer atau pinalty agar customer tidak melakukan pembatalan dengan mendadak, sehingga apabila terpaksanya ada pembatalan yang dilakukan, pihak hotel tidak mengalami kerugian yang besar ataupun bisa melakukan strategi untuk memasarkan kembali hotel yang di batalkan tersebut dengan harga spesial agar mendapatkan customer baru.

**Berdasarkan Karakteristik Tamu**
- Untuk customer keluarga yang memiliki anak-anak atau bayi, pihak hotel dapat menawarkan fasilitas yang mendukung mereka agar tidak mudah bosan seperti adanya playgrond khusus untuk anak ataupun bayi. Ataupun untuk customer yang membawa orang tua, pihak hotel dapat menyiapkan tremp atau akses lewat khusus utnuk orang tua yang menggunakan kursi roda. Pihak hotel juga dapat memberikan program loyalitas kepada customer, sehingga customer yang sering menginap di hotel dapat merasakan keistimewaan ketika sering menginap di hotel tersebut, ataupun customer yang loyal dapat memberikan testimoninya ke orang sekitar tentang pelayanan yang sangat luarbiasa yang diberikan oleh hotel, sehingga customer yang mendengarkan cerita tersebut berminat untuk mencoba menginap pada hotel tersebut.

**Berdasarkan Karakteristik Pemesanan**
- Hotel dapat memberikan diskon untuk para customer yang melakukan pemesanan langsung pada situs hotel dan memberikan kewajiban deposito ataupun kebijakan untuk tidak bisa melakukan pengembalian dana apabila memesan menggunakan agen. Selanjutnya untuk pelanggan tipe Contract, hotel dapat meberikan penawaran khusus dan opsi komitmen lebih awal, sementara untuk pelanggan Transient, berikan pengalaman yang lebih personal agar mereka merasa lebih dihargai atau diperhatikan. Dan untuk mengantisipasi adanya peningkatan pengunjung, pihak hotel dapat memastikan bahwa lahan parkir yang dimiliki cukup untuk menampung kendaraan yang dibawa oleh customer. Kemudian untuk  hotel berjenis resort hotel dapat menawarkan paket bundling all-inclusive untuk meningkatkan pengalaman tamu.  Kemudian pihak hotel dapat melakukan promosi pada sosial media dengan menggunakan multi-language sebab banyaknya customer yang berasal dari luar negeri.

**Berdasarkan Analisa Keuangan**
- Pendapatan hotel dari reservasi yang tidak dibatalkan mencapai €22,930,425.50, sementara potensi pendapatan dari reservasi yang dibatalkan adalah €11,456,861.02. Jika tidak ada reservasi yang dibatalkan sama sekali, maka total pendapatan hotel yang dapat diperoleh adalah €34,387,286.52. Dengan demikian, pembatalan reservasi menyumbang kerugian potensial sebesar 33.32% dari total pendapatan yang mungkin diraih jika tidak ada pembatalan. Untuk meminimalkan kerugian ini, hotel dapat menerapkan strategi kebijakan non-refundable atau mengenakan penalti pada pembatalan yang dilakukan dalam periode tertentu sebelum tanggal check-in. Selain itu, dengan meningkatkan promosi untuk menarik tamu last-minute, hotel dapat memanfaatkan kembali kamar yang kosong akibat pembatalan. Strategi ini tidak hanya mengurangi dampak finansial dari pembatalan, tetapi juga membantu menjaga tingkat okupansi kamar, yang pada akhirnya berkontribusi pada stabilitas pendapatan hotel.


Sebagai salah satu destinasi wisata utama, hotel di Portugal dapat memanfaatkan strategi berbasis data untuk meningkatkan daya saing. Dengan memberikan layanan responsif, promosi relevan, dan fasilitas yang baik, hotel dapat menciptakan pengalaman tamu yang optimal, mengurangi tingkat pembatalan, dan memaksimalkan pendapatan. Strategi ini juga membantu menjaga reputasi dan menarik lebih banyak tamu di masa mendatang.






