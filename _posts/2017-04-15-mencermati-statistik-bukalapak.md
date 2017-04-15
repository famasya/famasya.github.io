---
layout: post
title: Mencermati statistik bukalapak
---

Kemarin, ketika saya membaca berita teknologi, saya membaca sebuah liputan tentang [Bukareksa](https://www.bukalapak.com/bukareksa) oleh Bukalapak. Bukareksa adalah salah satu jenis investasi berbentuk reksadana yang dikelola oleh bukalapak.

Dalam berita yang dilansir oleh [Tech in Asia](https://id.techinasia.com/alasan-bukalapak-hadirkan-berbagai-fitur-baru-di-tahun-2017), ada satu kutipan yang menarik perhatian saya.

> “Pengguna kami ada yang memulai dari Rp50.000, namun ada juga yang menginvestasikan dana hingga Rp1 miliar. Secara rata-rata, pengguna kami berinvestasi sekitar Rp500.000 hingga Rp1 juta,” tutur Zaky.

Wow, 500 ribu itu jumlah yang besar untuk layanan yang baru diluncurkan. Namun saya teringat, rata-rata itu bisa menipu.

<!-- more -->

*Mean* atau nilai rata-rata memang gampang sekali dimengerti. Setiap orang dengan pengetahuan matematika dasar paham secara intuitif bahwa *mean* dapat diperoleh dengan membagi jumlah data dengan total banyaknya data.

Tapi hasilnya bisa ambigu.

### Problema nilai kelas
Bayangkan kita adalah seorang pengawas kelas yang sedang menilai kinerja guru-guru di kelas A dan B. Kelas A memberikan data, bahwa murid kelasnya memiliki rata-rata nilai sebanyak 6,3. Sedangkan kelas B, memiliki rata-rata 6.

Apakah kelas A lebih baik dari kelas B? Secara sepintas iya.

Namun mari kita lihat distribusi nilainya


<iframe width="427.76280323450146" height="264.5" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/1tZyzaXiCk5aBinxawvFbd7y4Bzjzwg0bu-rwaUZX_dA/pubchart?oid=930811441&amp;format=interactive"></iframe>

<iframe width="427.76280323450146" height="264.5" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/1tZyzaXiCk5aBinxawvFbd7y4Bzjzwg0bu-rwaUZX_dA/pubchart?oid=1807622046&amp;format=interactive"></iframe>

Dari grafik tersebut, ada sesuatu yang menarik. Meski rata-rata nilai kelas A (6,3) lebih baik dari kelas B (6), namun ternyata distribusi nilai kelas B lebih konsisten dari kelas A.

Sebagai pengawas, menurut saya kelas B lebih berhasil dari kelas A, walau rata-ratanya lebih kecil. Alasannya, murid-murid kelas B lebih konsisten dari kelas A. Hal ini dapat dijelaskan melalui **deviasi standar (standard deviation / STD)**.

### Menganalisa lebih dalam

Deviasi standar adalah salah satu cara untuk mengetahui disparitas suatu data. Rumusnya pun tidak membuat kepala pening.

Ketika kita hitung nilai standar deviasi dari kelas A menggunakan [rumus tersebut](https://www.khanacademy.org/math/probability/data-distributions-a1/summarizing-spread-distributions/a/calculating-standard-deviation-step-by-step), ia menunjukkan nilai 2,8. Sedangkan kelas B bernilai 1,2. 

Artinya distribusi nilai B lebih homogen dari kelas A, karena lebih mendekati nol (jika nol berarti sangat homogen).

Dari kasus di atas, deviasi standar dapat menunjukkan sesuatu yang kadang terlewat: bahwa *disparitas* data juga penting. Performa kelas –atau sekolah– tidak saja dinilai dari rata-rata nilainya, namun seberapa kecil perbedaan antar murid.

Hal ini pun mestinya kita cermati dalam menganalisa suatu berita. Termasuk berita dari Bukalapak di atas tadi.

Selisih antara 50 ribu dan 1 milyar di Bukareksa tadi menimbulkan pertanyaan. Bagaimana sebaran datanya? Apakah nilai rata-rata 500 ribu itu cenderung homogen atau tidak? Pertanyaan tadi bisa jadi analisa tersendiri jika kita jeli.

Menurut berita di atas, ada 25.000 nasabah dengan rata-rata investasi sebesar Rp 500.000-Rp 1.000.000. Saya asumsikan saja rata-rata investasi reksadana sebesar Rp 750.000. Maka total dana yang ada sudah sejumlah Rp 18.750.000.000. Jika ada satu investasi sebesar 1 milyar, maka itupun sudah mencakup kurang lebih 5% dari seluruh dana. Dari satu orang. 

Kita bisa bayangkan betapa tingginya nilai disparitas seluruh pengguna tersebut, karena 95% sisanya dibagi kedalam ribuan investor lain.

### Penutup

Analisa tadi hanyalah analisa sejenak tanpa validitas data lebih lanjut. Tentu dibutuhkan analisa mendalam untuk menentukan asumsi tadi benar atau salah.

Namun sekarang kita tahu, bahwa rata-rata atau *mean* tidak bisa dipukul rata untuk menganalisa segala hal. 

Dalam konteks pilkada kemarin misalnya. Saya teringat bahwa ada penyebutan [Rasio Gini](http://www.investopedia.com/terms/g/gini-index.asp) (*gini coefficient*) dalam salah satu debatnya. Rasio Gini juga merupakan salah satu mekanisme menganalisa kesenjangan antara si kaya dan si miskin. Jadi meski rata-rata pendapatan per kapita suatu kota naik, percuma jika kesenjangan sosialnya semakin besar.

Dalam hal lain, deviasi standar ini pun juga digunakan dalam menentukan distribusi normal suatu data, yang akan sangat berguna dalam analisa data dalam skala lebih besar. Namun hal tersebut tidak saya bahas disini. Mungkin akan saya bahas di lain waktu saja.

Yah, dengan tulisan ini setidaknya saya bisa membuktikan diri jika saya tidak ketiduran waktu mata kuliah statistika. :))

Tabik.

---
PS : Ada dua jenis perhitungan deviasi standar, yaitu menggunakan perhitungan sampel atau keseluruhan populasi. Dan jika ingin mengetahui penjelasan menarik tentang deviasi standar, saya sarankan membuka  situs [Math is fun](https://www.mathsisfun.com/data/standard-deviation.html).
