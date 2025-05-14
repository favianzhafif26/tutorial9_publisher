# Module 9

## a. How much data your publisher program will send to the message broker in one run?
Dalam satu kali eksekusi, publisher mengirimkan sebanyak 5 data ke message broker. Hal ini terlihat pada fungsi `main` di file `main.rs`, di mana fungsi `publish_event` dipanggil lima kali dengan isi data yang berbeda-beda.

## b. The url of: “`amqp://guest:guest@localhost:5672`” is the same as in the subscriber program, what does it mean?
Program subscriber dan publisher menggunakan URL yang sama karena keduanya terhubung ke server AMQP yang sama. Struktur URL tersebut memiliki arti yang sama seperti pada program subscriber: bagian pertama `guest` adalah nama pengguna untuk login ke message broker, `guest` kedua adalah kata sandi dari pengguna tersebut, dan `localhost:5672` menunjukkan alamat server serta port standar yang digunakan oleh protokol AMQP dalam hal ini RabbitMQ.

## Running RabbitMQ as message broker

![image](https://github.com/user-attachments/assets/1cae5ba9-cbeb-46c9-b0e2-f0e972c1901f)

## Sending and processing event

![image](https://github.com/user-attachments/assets/3b6fa417-dcb0-40aa-973b-630e0a94e8c4)

Ketika menjalankan cargo run pada console dengan direktori publisher, console dengan direktori subscriber akan memunculkan 5 data message bertahap-tahap sesuai dengan program.

## Monitoring chart based on publisher

![image](https://github.com/user-attachments/assets/98d4e4d2-c295-49a5-8bdd-82767d9e66e4)

Munculnya spike-spike pada chart kedua (dibawah) dikarena pengiriman request cargo run berkali-kali pada publisher yang menyebabkan spiking (naiknya frekuensi) pada message rates yang diterima oleh subscriber
