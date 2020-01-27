# Laravel Guide :: Autentikasi Otomatis
(petunjuk penginstallan dan penggunaan dasar laravel)

untuk membuat sebuah halaman login dan register pada laravel 6 kita perlu mengerjakan perintah dibawah ini :
```
composer require laravel/ui --dev -vvv

php artisan ui vue --auth

atau

php artisan ui bootstrap --auth

npm install && npm run dev

setelah itu jika belum melakukan proses db apapun silahkan untuk membuat database misalkan todo

nah setelah itu atur konfigurasi database di file .enc

setelah itu lakukan ini lewat terminal usahakan ada file artisan disitu kemudian proses dibawah ini akan membuat tabel-tabel yang diperlukan dalam proses autentifikasi

php artisan migrate
```

berikutnya anda dapat registrasi user pertama dan kemudian langsung masuk area dashboard (defaultnya seperti itu)
