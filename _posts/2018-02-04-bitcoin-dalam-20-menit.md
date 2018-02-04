---
layout: post
title: Bitcoin dalam 20 menit
---

## Tulisan ini merupakan penyederhanaan dari tulisan blockchain saya  sebelumnya.
 
Kemarin ketika saya ngobrol-ngobrol sama teman, saya “ditodong” penjelasan tentang bitcoin. Sebenarnya saya sudah membuat sebuah penjelasan bagaimana kerja bitcoin. Tetapi karena terlalu teknis, saya putuskan untuk menjelaskan ulang bagaimana cara kerjanya secara lebih sederhana. 

## Apa itu bitcoin?
***
Bitcoin adalah sebuah *cryptocurrency*, yaitu istilah untuk uang digital yang diproduksi dengan menggunakan persamaan matematika, alih-alih oleh pemerintah. Jadi tidak ada sistem yang memproduksi bitcoin secara terpusat. Semua dilakukan berdasarkan sistem terkomputasi.

## Mengapa bitcoin melambung tinggi harganya?

Ada penjelasan menarik dari Pak Budi Rahardjo, dosen ITB tentang bitcoin ini yang bisa dilihat dari [blog beliau](https://rahard.wordpress.com/2017/12/20/analogi-bitcoin/). Saya akan mengutipnya disini:

> Katakanlah sekolah Anda ingin mengadakan acara bazaar. Di acara tersebut ada penjualan makanan dan minuman. Agar penjualan makanan dan minuman terkendali maka panitia membuat aturan bahwa pembelian makanan dan minuman dilakukan dengan menggunakan kupon. Kupon dijual dalam pecahan Rp. 20.000,-. Maka mulailah orang yang hadir di bazaar tersebut membeli kupon.
>
> Untuk menghindari terjadinya fraud, penipuan, kupon palsu dan sejenisnya maka jumlah penjualan kupon dibatasi. Hanya ada 500 kupon yang tersedia.
>
> Eh, ternyata makanan dan minuman yang ada di sana enak-enak. Maka orang mulai mencari kupon. Walah. Jumlah kupon yang tersedia ternyata terbatas. Maka mulailah kupon dicari. Tiba-tiba ada orang yang menjual kuponnya. Kupon yang harganya Rp. 20.000,- dijual seharga Rp. 25.000,-. Lumayan, untung Rp. 5.000,-. Malah ada orang yang menjual kupon itu dengan harga Rp. 30.000,-.
>
> Begitu melihat kupon dapat dijual lebih mahal dari harga belinya maka orang mulai memperjualbelikan kupon. Kupon lebih dicari lagi. Harga makin naik lagi. Sekarang harga kupon menjadi Rp. 100.000,-. Wow!!
>
> Lucunya, orang-orang tidak menggunakan kupon itu untuk membeli makanan. Justru jual beli kuponnya yang menjadi fokus kegiatannya.

Jadi intinya, daripada menggunakan bitcoin sebagai transaksi, orang-orang lebih memilih menggunakannya sebagai alat *investasi*. Nah, dengan publisitas media yang besar, maka berlaku pula hukum *supply-demand* dalam ekonomi. Maka melambunglah nilai bitcoin.

## Cara kerja bitcoin
***
Ketika kita membeli sebuah barang secara non fisik —transfer misalnya— tanpa sadar kita selalu melibatkan pihak ketiga yang disebut bank. Fungsi bank disini adalah menjadi pihak yang dipercaya semua pihak untuk *mengurangi uang saya dan menambah uang pembeli ketika transaksi terjadi*.

Jadi ketika saya memiliki uang 2.000.000 dan membeli barang sejumlah 1.000.000 dari penjual A, maka yang terjadi:

- Transaksi telah dilakukan dari saya ke penjual A.
- Rekening saya berkurang 1.000.000  
- Rekening penjual bertambah 1.000.000  

Yang pencatatan keseluruhannya dilakukan oleh *bank*.

Dalam *bitcoin* yang merupakan *cryptocurrency*[1], **pihak ketiga ini dihilangkan**.  Alasannya? Banyak. Salah satunya untuk efisiensi.

Dan transaksi beralih menjadi : dari saya langsung ke seller. Tanpa bank. Hal ini disebut sistem *peer-to-peer*.

Jadi, siapa yang bertanggungjawab mengurangi rekening saya dan menambah rekening penjual? Bisa saja kan saya tidak mengurangi uang saya sebanyak 1.000.000 setelah saya membeli barang?

Hal ini disebut *double spending problem*.

Untuk mengatasinya, bitcoin menggunakan skema berikut: daripada mengandalkan bank sebagai pencatat transaksi kita, **bagaimana jika setiap catatan transaksi bitcoin, disebarluaskan oleh sebanyak mungkin orang di seluruh dunia?**

Katakanlah ada 5 pihak A, B, C, D, dan E yang bersedia menerima diserahi catatan transaksi bitcoin dari seluruh dunia.

Saya memiliki uang 3 BTC dan ingin membeli sebuah rumah seharga 1 BTC. Ketika saya melakukan transaksi, maka transaksi saya akan disebarluaskan ke A, B, C, D dan E. Sehingga, uang saya tercatat di mereka sejumlah 2 BTC.

Maka ketika saya ingin membeli rumah sebanyak 3 BTC, maka hal ini **tidak akan valid**. Mengapa? Karena ada 5 pihak yang mencatat bahwa saya telah melakukan transaksi sebanyak 1 BTC, sehingga —dengan matematika sederhana— rekening saya tinggal 2 BTC.

![distributed ledger](/public/distributed-ledger.jpg)  
Kiri: transaksi dilakukan. Kanan: transaksi disebarluaskan ke publik. Sumber gambar: [Max Groups](http://max-groups.com/blockchain-tech-maritime-supply-chain-fad/)

Pihak bernama A, B, C, D dan E itulah yang disebut *bitcoin miners*. Yaitu orang-orang yang berlomba untuk melakukan validasi transaksi bitcoin. Mereka akan mendapat sejumlah kecil bitcoin sebagai upahnya dari kedua belah pihak.

Sedangkan sistem menggunakan transaksi terdistribusi ini disebut *blockchain*.

## Implikasi-implikasi
***
Apa implikasinya? Ternyata cukup banyak. Beberapa diantaranya seperti berikut.

Yang paling penting adalah lebih terjaga keamanannya. Ketika seorang peretas berhasil meretas sistem bank sentral, maka ia bisa mengubah seluruh transaksi yang ada. Dalam *blockchain* hal ini (hampir) mustahil dilakukan. Karena untuk mengubah sebuah transaksi, ia harus meretas seluruh catatan yang telah tersebar di seluruh dunia (dalam kasus tadi di komputer A, B, C, D dan E)

Selanjutnya adalah kerahasiaan. Untuk melakukan sebuah transaksi, kita hanya butuh *bitcoin address*. Cukup itu. Dan karena dilakukan antar pengguna, maka kerahasiaannya terjamin.

Terakhir adalah *volatilitas*. Karena tidak ada pengatur regulasi, maka “kurs” bitcoin mengacu pada pasar bebas dan hukum ekonomi *supply* dan *demand*. Hal inilah yang menjadi perhatian Bank Indonesia mengapa mereka memutuskan untuk menunda legalitas bitcoin. Salah satunya untuk melindungi konsumen.

## Penutup
***
Mungkin ada pertanyaan, “Bagaimana jika terlalu banyak bitcoin diproduksi? Bukankah akan terjadi inflasi?”

Sebagai catatan, ada konsensus bahwa hanya ada 21 juta bitcoin yang dapat diproduksi. Jadi secara teoritis memang bitcoin akan terus naik harganya, seperti harga tanah. Meskipun volatil. 

Tetapi karena bitcoin bukanlah uang fisik, maka bitcoin dapat diperdagangkan hingga ke digit yang sekecil-kecilnya. Satu kilogram beras berharga 10^-9 BTC misal.

Catatan ini hanyalah panduan sederhana untuk memahami bitcoin. Sehingga bisa jadi ada salah dan ketidakakuratan informasi di dalamnya. 

Sebenarnya, saya sudah menulis hal yang jauh lebih teknis [disini](https://famasya.github.io/2017/11/24/bagaimana-blockchain-bekerja/) sih. Jadi *monggo* saja jika ingin membacanya. Jika ada pertanyaan atau diskusi, silakan sapa saya di [twitter](https://twitter.com/famasya).

*Adios! :)*