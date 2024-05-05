## 2.1. _Understanding How it Run_

![Understanding how it run](https://i.imgur.com/uFIA7Ia.png)

Untuk menjalankan program _broadcast chat_ ini, pertama kita perlu jalankan _server_ menggunakan perintah `cargo run --bin server` dalam satu terminal. Kemudian, buka beberapa terminal lain dan jalankan _client_ menggunakan perintah `cargo run --bin client` di setiap terminal. Setelah semua _client_ terhubung, ketika kita mengetik pesan di salah satu _client_ dan menekan _enter_, pesan tersebut akan dikirim ke _server_. _Server_ kemudian akan menyebarkan pesan tersebut kepada semua _client_ yang terhubung dan setiap _client_ akan menampilkan pesan tersebut di terminalnya.

## 2.2. _Modifying the websocket port_

Untuk mengubah port menjadi 8080, kita perlu memodifikasi bagian di mana _server_ melakukan _binding_ kepada port. Selain itu, kita juga perlu memastikan bahwa _client_ terhubung ke port yang benar. Pada file `client.rs`, kita perlu memastikan bahwa _client_ terhubung ke URI yang menggunakan port 8080 dengan perintah `Uri::from_static("ws://127.0.0.1:8080")`. _Protocol_ yang digunakan masih sama, yaitu WebSocket, yang didefinisikan menggunakan modul `tokio_websockets`. Jika kita jalankan kembali, dapat dilihat bahwa program masih dapat berjalan dengan baik.

![Modifying the websocket port](https://i.imgur.com/nt8psIP.png)

## 2.3. _Small changes, add IP and Port_

Pada `server.rs`, saya menambahkan informasi alamat pengirim ke setiap pesan yang dikirim ke _client_.

![](https://i.imgur.com/4LOHOqX.png)

Sementara itu, pada `client.rs`, saya menambahkan teks "Fahmi's computer -". Selain itu, karena perubahan dari _server_, _client_ juga akan menampilkan alamat IP dan port asli pengirim saat mencetak pesan dari _server_

![](https://i.imgur.com/ppC2xzv.png)

Berikut adalah hasilnya setelah dijalankan.

![](https://i.imgur.com/uoh7sSl.png)
