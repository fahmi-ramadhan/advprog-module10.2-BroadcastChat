## 2.1. _Understanding How it Run_

![Understanding how it run](https://i.imgur.com/uFIA7Ia.png)

Untuk menjalankan program _broadcast chat_ ini, pertama kita perlu jalankan _server_ menggunakan perintah `cargo run --bin server` dalam satu terminal. Kemudian, buka beberapa terminal lain dan jalankan _client_ menggunakan perintah `cargo run --bin client` di setiap terminal. Setelah semua _client_ terhubung, ketika kita mengetik pesan di salah satu _client_ dan menekan _enter_, pesan tersebut akan dikirim ke _server_. _Server_ kemudian akan menyebarkan pesan tersebut kepada semua _client_ yang terhubung dan setiap _client_ akan menampilkan pesan tersebut di terminalnya.
