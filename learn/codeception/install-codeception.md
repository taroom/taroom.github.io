# CodeCeption Instalasi

library yang perlu kamu install dan perlu kamu tambahkan ke composer.json, bagian require-dev

```
"require-dev": {
    ...
    "codeception/codeception": "^4.0",
    "codeception/module-asserts": "^1.0",
    "codeception/module-yii2": "^1.0",
    "codeception/module-filesystem": "^1.0",
    "codeception/verify": "~0.5.0 || ~1.1.0",
    "codeception/module-phpbrowser": "^1.0.0",
    "codeception/module-webdriver": "^2.0",
    ...
},
```

selain itu jika kita ingin menggunakan acceptance dan functional test kita perlu menginstal selenium. selenium digunakan untuk mengontrol browser (firefox, chrome, edge, IE dsb) untuk keperluan testing, kita bisa menggunakan selenium versi node.js dengan cara install selenium secara global, melalui npm

```
npm i -g selenium-standalone
selenium-standalone install
```

nah perintah kedua ini membutuhkan java, jadi silahkan menginstall java terlebih dahulu sebelum menjalankan perintah _install_ diatas. biar mudah kita instal lewat jdk di alamat ini (sesuaikan dengan OS Anda)

[Java SE Development Kit](https://www.oracle.com/java/technologies/downloads/)

cara install gampang tinggal next, next install saja, jika sudah selesai coba jalankan perintah _install_ diatas (yang baris kedua) perintah ini akan mendownload driver-driver browser yang diperlukan. (Pastikan koneksi Anda baik)

jika sudah selesai coba jalankan

```
selenium-standalone start
```

perintah diatas akan menjalankan server selenium, jika telah berjalan jangan ditutup ya, langsung saja kesini

[Menjalankan CodeCeption](run-codeception.md)
