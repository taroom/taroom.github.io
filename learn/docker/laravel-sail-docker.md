# Laravel Sail Tanpa Perlu Install Laragon

[Kembali](index.md)

## Langkah 1: Menginstal Docker dan WSL

Pastikan Docker dan WSL terinstal di sistem Anda. Anda bisa mengunduhnya dari situs resmi [Docker](https://www.docker.com/) dan [wsl disini](https://learn.microsoft.com/en-us/windows/wsl/install)

## Langkah 2: Menggunakan Laravel Build untuk Membuat Proyek Baru

gunakan perintah ini di terminal, Anda harus menggunakan terminal wsl. jika Anda menggunakan terminal di sistem ubuntu

```bash
curl -s https://laravel.build/contoh-aplikasimu | bash
```

## Langkah 3: Menggunakan Laravel Sail untuk Membuat Proyek Baru

setelah aplikasi terbuat maka anda bisa langsung menjalankan perintah dibawah ini untuk mulai mendownload docker image yang dibutuhkan melalui sail :

```bash
cd contoh-aplikasimu
./vendor/bin/sail up
atau
./vendor/bin/sail up -d
(mode detach)
```

## Langkah 4: Selesai

Setelah semua docker image yang dibutuhkan terdownload maka kita bisa menggunakan perintah perintah Sail dibawah ini:

menjalankan semua perintah artisan

```bash
./vendor/bin/sail artisan migrate
```

menjalankan semua perintah npm

```bash
./vendor/bin/sail npm run dev
```

Menjalankan unit test:

```bash
./vendor/bin/sail artisan test
```

## BONUS menginstall daisy ui untuk tailwind

pertama harus kita aktifkan tailwindnya. cara mudahnya sih bisa pakai laravel breeze. coba install laravel breeze

```bash
./vendor/bin/sail composer require laravel/breeze --dev
```

setelah install lewat composer jangan lupa jalankan perintah ini :

```bash
./vendor/bin/sail artisan breeze:install
```

nah setelah perintah diatas kamu jalankan akan ada beberapa pertanyaan muncul

saya jawab setahu saya aja ya

Which Breeze stack would you like to install? **Blade with Alpine**
Would you like dark mode support? **Yes**
Which testing framework do you prefer? **PHPUnit**

ok setelah langkah diatas maka akan ada link di website kita (selama halaman welcome tidak dirubah) yakni link login dan register. dan kita sudah menginstall tailwind ya karena breeze butuh tailwind.

langkah selanjutnya ketikkan perintah dibawah ini

```bash
./vendor/bin/sail artisan migrate (kalau belum)
./vendor/bin/sail npm install
./vendor/bin/sail npm run dev (menjalankan vite)
```

untuk menyalakan fitur hot reload maka tempatkan script ini di welcome

```php
<title>Nearest Food</title>
  ..
  @vite('resources/css/app.css')
</head>
```

nah sekarang saatnya menginstall daisy ui caranya buka tab terminal baru di vscode

lalu ketikkan perintah dibawah ini :

```bash
./vendor/bin/sail npm i -D daisyui@latest
```

nah setelah berhasil pasangkan daisy ke tailwind.config.js

```js
import defaultTheme from "tailwindcss/defaultTheme";
import forms from "@tailwindcss/forms";

/** @type {import('tailwindcss').Config} */
export default {
  content: [
    //    **
  ],

  theme: {
    extend: {
      fontFamily: {
        sans: ["Figtree", ...defaultTheme.fontFamily.sans],
      },
    },
  },

  plugins: [forms, require("daisyui")],
};
```

selesai. Anda bisa memakai semua komponen dari daisyui
