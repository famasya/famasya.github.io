---
layout: post
title: Bagaimana Blockchain bekerja
---

## Bitcoin sudah jadi hot topic belakangan. Tapi di balik itu, ide yang revolusioner itu namanya _blockchain_, mekanisme dari bitcoin.

Bitcoin adalah _cryptocurrency_, yaitu uang yang diproduksi berdasarkan persamaan matematika alih-alih dikeluarkan oleh pemerintah. Latar belakangnya? Sepertinya di dunia internet ini sebisa mungkin warganet ingin menghindari interupsi pemerintah. 

Dan orang-orang lebih percaya matematika daripada manusia.

Pseudonym-nya _Satoshi Nakamoto_, seorang (atau sekelompok orang) yang menulis sebuah whitepaper: Bitcoin, A Peer-to-Peer Electronic Cash System. Whitepaper inilah yang melatarbelakangi lahirnya bitcoin. Namun hingga kini pun Satoshi masih misteri karena belum ada orang yang secara _legitimate_ diakui sebagai Satoshi yang asli.

Bitcoin menggunakan mekanisme unik layaknya buku besar (_ledger_) yang terdistribusi. Rangkaian traksaksi elektronik dicatat di ribuan komputer, alih-alih memercayakannya ke **satu** pihak ketiga (pemerintah) sebagai perantaranya. Rangkaian transaksi itu tercatat dalam publik, sehingga tidak diperlukan bank sebagai pihak ketiga. Orang-orang menyebutnya _blockchain_ meski tidak ada kata itu secara eksplisit di paper-nya.

Bingung? Tidak apa-apa. Saya dulu juga begitu.

## Transaksi konvensional
***
Sebelum menginjak blockchain, lebih enak jika kita mengetahui bagaimana cara kerja transaksi konvensional bekerja terlebih dahulu.

Ketika kita ingin melakukan suatu transaksi, sebenarnya kita selalu melibatkan pihak ketiga dalam transaksi tersebut yang sering diwakili oleh bank.

Saya ingin membeli barang di Toko A menggunakan rekening saya sebesar 1 juta rupiah. Uang saya di bank tinggal 1.500.000. Ketika saya melakukan pembayaran, otomatis uang saya akan berkurang sebesar 1 juta rupiah. Kini saldo di rekening saya tinggal 500.000 rupiah. Sedangkan rekening A bertambah 1 juta rupiah.

Pengurangan ini dilakukan oleh bank sebagai **pihak ketiga yang dipercaya semua orang**. Sehingga, setelah transaksi itu, saya tidak dapat menghabiskan uang lebih dari 500.000 rupiah.

Dalam blockchain, pihak ketiga itu dihilangkan. Jadi siapa yang meverifikasi rekening saya telah berkurang sebesar 1 juta rupiah? Tidak ada uang fisik yang dilibatkan. Bisa saja saya tidak mengurangi rekening saya kan?

![double spending](/public/double-spending.png)

Masalah di atas disebut _double spending_ problem.

## Mengenal blockchain
***
Blockchain bekerja dengan ide yang sederhana: ketika satu pembelian dilakukan, maka user akan melakukan signing transaksi tersebut menggunakan private key miliknya. Transaksi yang telah di-sign akan disebarluaskan ke seluruh komputer (_nodes_) dalam network.

![mekanisme blockchain](https://blockgeeks.com/wp-content/uploads/2016/09/infographics0517-01-1.png)

Sumber gambar: [Blockgeeks](https://blockgeeks.com/guides/what-is-blockchain-technology/).

Beberapa transaksi dalam rentang waktu tertentu akan dikumpulkan menjadi satu yang disebut *block of transaction*. Satu block ini akan diverifikasi oleh nodes.

Setelah block selesai divalidasi oleh sistem, maka block tersebut akan disebarluaskan lagi ke nodes untuk ditambahkan ke suatu rangkaian bersamaan block-block yang lain. 

Block yang valid ditandai dengan seluruh transaksi-transaksi yang terjadi dalam block tersebut valid dan tidak *overspend* dan *double spending*. Overspend bisa terjadi ketika saya menghabiskan transaksi lebih banyak dari uang yang saya miliki.

Suatu block yang valid akan ditambahkan ke block sebelumnya dengan referensi historis membentuk suatu rangkaian (chain). Disinilah nama *blockchain* berasal.

![rangkaian blocks](/public/chain-of-blocks.png)

### Lah, gitu aja? Lalu dimana keamanannya?

Jika seseorang membeli sesuatu menggunakan blockchain dengan sejumlah *currency*, maka *overspend* maupun *double spending* dalam transaksi berbeda akan ditolak sistem. Jadi harus dipastikan hanya ada satu block yang valid, dan ditambahkan dalam blockchain.

![rejected transaction](/public/double-spend-rejected.png)

Dan karena blockchain berada dalam peer-to-peer system, maka setiap transaksi akan tercatat dalam publik. Terdapat proses mining untuk melakukan validasinya. FYI, mining disini berbeda maknanya dengan proses menggali emas.

Dalam proses mining akan dilakukan *hashing* terhadap block. Kita tahu bahwa proses hashing disini akan berbeda jika block sebelumnya berbeda.

Jadi ketika ada seseorang ingin "menimpa" suatu transaksi dengan yang palsu, maka ia harus mengubah seluruh blockchain dalam seluruh nodes sekaligus. Karena jika ia hanya mengganti satu block dalam sebuah blockchain, nodes akan menolaknya karena hasil hash yang berbeda. 

Artinya (sampai saat ini), ini tidak mungkin dilakukan. 

Mekanisme blockchain juga akan mengeliminasi "cabang terpendek" jika ada dua chain dengan referensi yang sama untuk menjamin validitas.

Jadi pertama: seluruh transaksi di blockchain dipastikan valid, kedua: proses penimpaan (tampering) sulit dilakukan. Disinilah keamanan yang ditawarkan blockchain dibanding transaksi tersentralisasi biasa.

### Lalu bagaimana sebenarnya cara blockchain melakukan validasi suatu block?

Pertanyaan bagus. Bisa saja ada banyak block-block palsu yang diproduksi dan ditambahkan ke chain dengan cepat. Lagi-lagi kuncinya ada di proses *mining*.

Cara dari blockchain untuk memastikan **hanya** ada satu block yang valid adalah dengan membuat sebuah block sangat sulit untuk diproduksi.

Proses validasi suatu block memerlukan suatu proses kriptografis disebut Proof of Work (PoW). Proof of work adalah suatu proses untuk menyelesaikan fungsi matematika rumit dan *computationally intensive*, yang akan diberi suatu reward berupa *bitcoin*. Jadi akan ada semacam "balapan" antar miners untuk mevalidasi block terlebih dahulu. 

![block validation](/public/block-validation.png)

Nah, selain menyelesaikan fungsi kriptografis, miners juga dituntut untuk mevalidasi bahwa tidak ada transaksi yang berkonflik di dalam block tersebut. Jadi bisa dikatakan para miners melakukan *gambling* dalam mevalidasi block. Bisa saja ia mendapat upah berupa bitcoin, atau orang lain menyelesaikannya lebih dahulu.

Setelah divalidasi, maka bisa dikatakan block tersebut valid.

Tapi tunggu dulu, bisa jadi kan, saya melakukan *mining* terhadap transaksi saya terlebih dahulu dengan hardware super modern, lalu menambahkan block tersebut ke chain sebelum yang lainnya?

## Tantangan blockchain
***
Disinilah tantangan-tantangan blockchain berasal. Setidaknya ada 3 tantangan yang harus dihadapi:

1. Race attack
2. Finney attack
3. 51% attack


Race attack terjadi ketika ada suatu user *melakukan transaksi ke dirinya sendiri tepat ketika ia melakukan transaksi lainnya*. Dengan kata lain, kedua transaksi ini di-broadcast ke network secara bersamaan dan diharapkan transaksi yang divalidasi adalah transaksi yang menuju dirinya sendiri.

![race attack](/public/race-attack.png)

Biasanya hal ini terjadi sebelum transaksi divalidasi oleh sistem (0/unconfirmed), sedangkan merchant sudah kadung percaya bahwa payment telah dilakukan. Solusinya adalah dengan menanti pembayaran dilakukan divalidasi oleh miners.

Sedangkan finney attack terjadi ketika ada suatu user yang melakukan mining suatu block terlebih dahulu, tapi block yang telah divalidasi untuk di-broadcast ke network. Sehingga sebelum me-broadcast validated block, user bisa menggunakan transaksi yang sama untuk membeli barang lain.

Hal ini dibutuhkan hardware resource yang tinggi dan timing yang sangat tepat. Tapi bisa dicegah dengan menunggu validasi lebih lama: misal 6 block yang valid. Karena semakin hanya satu block valid, akan rentan serangan ini. Semakin panjang block, akan kelihatan mana yang valid.

Dan yang terakhir adalah 51% attack (majority) yang secara teoritis akan memenangi "balapan" dalam validasi block.

Bayangkan ada seorang dengan resource mining sangat besar: lebih dari setengah resource mining di dunia. Maka dengan ini, dia bisa membuat transaksi-transaksi palsu dan dengan cepat mevalidasinya.

![51% attack](/public/51-percent.png)

Semua transaksi lain akan dianggap tidak valid karena ia telah melakukan validasi dan me-broadcast terlebih dahulu. Karena mekanisme blockchain yang hanya akan mengakui satu chain terpanjang, maka dengan 51% komputasi, seseorang akan dengan mudah "menimpa" chain yang ada sekarang.

## Penutup

Itulah sekilas tentang blockchain yang saya pelajari belakangan. Didasari dari penasaran dengan yang-lagi-ngetren, saya belajar blockchain.

Sebenarnya banyak juga hal lain yang bisa dipelajari: ethereum, smart contract, Proof-of-Stake, Vector76 attack, dll. Banyak sekali penelitian yang dilakukan di bidang ini. Bahkan, ketika sore tadi saya iseng-iseng browsing Hacker News, Bitcoin [ternyata bisa di hijack melalui BGP protocol](https://btc-hijack.ethz.ch/).

Selain itu banyak potensi lain dari blockchain dan tidak terbatas di bitcoin saja seperti di bidang kesehatan, properti, hingga [voting](https://medium.com/@BlockByBlock/how-we-can-improve-the-election-process-using-blockchain-technology-5b313be330f4). Bahkan Bank Indonesia juga [sedang memelajarinya](https://tirto.id/blockchain-teknologi-yang-awalnya-membuat-takut-bank-cxJu).

Dan karena saya juga belajar, saya menerima sekali segala koreksi atas tulisan ini.

Cheers!

***
Ref:  
[1] https://bitcoin.org/bitcoin.pdf  
[2] https://blockgeeks.com/guides/what-is-blockchain-technology/  
[3] https://bitcoin.stackexchange.com/questions/148/what-exactly-is-mining  
[4] https://en.bitcoin.it/wiki/Irreversible_Transactions