# Laravel Guide

(petunjuk penginstallan dan penggunaan dasar laravel)

## cara install menggunakan laravel + composer

nantinya kita bisa menggunakan perintah dibawah ini untuk membuat projek baru dengan cepat :

```
laravel new aplikasimu
```

### menginstall laravel

sebelum bisa menggunakan perintah diatas yang harus dikerjakan pertama kali adalah menginstall laravel ke composer dengan cara

```
composer global require laravel/installer
```

lalu agar lebih melekat kedalam terminal (bisa dipanggil dari direktori/path manapun) kita tambahkan PATH ke ~/.bashrc

```
export PATH="$PATH:$HOME/.composer/vendor/bin"
```

# Beberapa hal dasar yang perlu dipersiapkan

## Database kosong

kita bisa menggunakan phpmyadmin untuk membuat sebuah database kosong. yang selanjutnya akan di isi oleh perintah migrasi di laravel

## lakukan instalasi proyek baru laravel dengan menggunakan

ketikkan perintah ini di terminal atau command prompt (windows)

```
laravel new coba
```

atau kamu juga bisa menggunakan perintah dari composer

```
composer create-project laravel/laravel coba
cd coba
php artisan serve
```

baris pertama akan membuat sebuah aplikasi dengan nama folder dan nama projek coba, baris kedua masuk kedalam folder utama aplikasi dimana disana ada file "artisan" file tanpa extensi yang dapat digunakan untuk berbagai hal, untuk kali ini kita gunakan fitur serve dimana artisan dari laravel akan membangkitkan server built-in php yang bisa kita langsung akses melalui browser dengan alamat yang biasanya http://localhost:8000 atau http://127.0.0.1:8000, 8000 adalah port default yang dapat kita ganti dengan menggunakan paramater --port

```
php artisan serve --port 8001
```

## edit konfigurasi .env

sesuaikan dengan konfigurasi koneksi database yang telah kita buat,

## pentingnya scaffolding terlebih dahulu

harus install scaffolding mau pakai laravel ui, breeze, atau jetstream sebelum aplikasi dibuat dikarenakan route, controller akan di timpa. kejadian (2023-11-19 13:49:32)

[kesini untuk laravel ui](guide-install-laravel-ui.md)<br>
[kesini untuk laravel breeze](laravel-8-breeze-auth.md)

[Selesai? Klik Disini](guide.md)
