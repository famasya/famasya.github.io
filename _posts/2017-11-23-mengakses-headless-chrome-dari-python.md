Istilah headless browser cukup populer di kalangan software engineer apalagi bagian QA. Berbeda dengan _browser_ biasa, _headless browser_ tidak menggunakan antarmuka dan hanya menggunakan _core_ dari browser tersebut untuk me-render komponen web. Maka dari itu, headless browser ini relatif ringan dan populer digunakan untuk front end testing maupun automation.

Beberapa waktu lalu saya cukup sering menggunakan headless chrome sebagai _tools_ testing. Cukup banyak solusi yang ditawarkan dalam berbagai API. Yang paling populer adalah selenium dan PhantomJS. Namun semenjak isu [phantom js ditinggal maintenernya](https://news.ycombinator.com/item?id=14105489), saya mulai mencari alternative lain.

Dan ketemulah sama [Chrome Headless Browser](https://developers.google.com/web/updates/2017/04/headless-chrome).

Sejak Chrome 59, secara default, kita bisa mengakses headless browser dengan parameter ```--headless```. Ada berbagai macam mode headless yang ditawarkan mulai dari REPL, hingga _remote debugging port_ (RDP). Nah, karena tim _startup_ saya masih kecil (banget) dan saya adalah programmer yang merangkap ini-itu, akhirnya saya belajar pakai headless mode ini. 

Masalahnya timbul ketika saya diminta bikin DOM testing, dan lagi 'males' move on dari Python. Sedangkan contoh snippet yang diberi Google dalam EcmaScript[1]. Sebenarnya saya ada sih beberapa pengalaman dengan ES, tapi karena 'kemalasan', saya coba manipulasi yang ada dulu. 

Di headless chrome ada RDP, yang mana menggunakan websocket sebagai komunikasinya. Jadi, bagaimana kalau kita bisa mengirim evaluasi DOM menggunakan javascript lewat websocket ke headless chrome? Dengan ini saya tidak perlu menulis Node.js package.

{% gist f13896e7113ab82a0d60b9dbb9330a1a %}

Expression di atas akan menghasilkan

`{'result': {'type': 'string', 'value': 'http://localhost/'}}`

Yay!

Untuk menjalankannya, dibutuhkan headless chrome yang sudah berjalan di belakang layar. Saya gunakan command ```/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --headless --remote-debugging-port=9222 http://localhost:3030``` untuk membuka halaman front end secara background. Bisa juga menggunakan ```subprocess``` bila ingin menggabungkan eksekusi headless Chrome dalam script.

Logikanya cukup sederhana bukan? Dengan library `requests`, untuk mendapatkan `websocketDebuggerUrl`, kita bisa mengirim evaluasi expression javascript untuk dieksekusi di Chrome. Hasilnya akan dapat kita terima dengan `ws.recv()`.

Oh iya, karena eksekusi expression-nya secara asynchronous, maka mungkin perlu ditambahkan `time.wait()` untuk menunggu elemen web ter render dengan sempurna.

Masih banyak potensi yang disediakan oleh Chrome ini sendiri. Kita bisa mengeksekusi expression dalam mode REPL dengan menambahkan parameter `--repl`, atau melakukan screenshot dengan `--screenshot`. Referensi lengkapnya ada [di sini](https://developers.google.com/web/updates/2017/04/headless-chrome).

Ngomong-ngomong, semoga Firefox bisa menyediakan headless browser juga agar tidak Google centric.

[1] Ada perbedaan antara Javascript dan EcmaScript di [tulisan menarik ini](http://blog.codecarrot.net/whats-the-difference-between-javascript-and-ecmascript/).