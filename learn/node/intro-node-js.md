## Apa yang tidak bisa dilakukan Node JS

- melakukan fungsi fungsi DOM di nodejs
- AJAX berjalan hanya di browser
- API baru yang di define hanya untuk bekerja pada node js, bukan js yang ada dibrowser

## Daftar RoadMAP Pembelajaran Node JS

- Concurrency dan Parallel
- Validasi
- setup nodejs (setting path)
- hello world
- modules
- [Debugging](debugging.md)
- [Unit Test](unit-test.md)
- require function (commonJS) dan import (ES16)
- package / library bawaan node JS (os, filesystem, ...)

## Jenis Aplikasi Yang disarankan menggunakan node js

- semuanya kecuali CPU Intensive App

### Aplikasi CPU Intensive

- Aplikasi Enkripsi/Dekripsi
- Video Transcoder

## Beberapa Kesimpulan

- Node JS hanyalah mesin browser (v8) yang dipakai agar JS bisa menjadi bahasa pemrograman Server
- Beberapa fungsi JS yang diperuntukkan untuk pemrograman client (browser) dihilangkan, semacam ajax (XMLHttpRequest), fungsi fungsi DOM
- Untuk membantu pekerjaan, node sudah mempersiapkan library/package bawaan untuk kebutuhan khusus semacam package os (untuk yang berurusan dengan sistem operasi), http (untuk pemanggilan layaknya curl)
