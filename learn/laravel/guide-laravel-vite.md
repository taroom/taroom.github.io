# Laravel Vite

kita bisa melakukan auto refresh menggunakan vite.js, dimana vite js menggantikan laravel mix untuk hal ini. penggantian ini dimulai di laravel versi 9 jadi yang udah pakai laravel v9 lanjut

disini langsung saja kita nyalakan 2 windows terminal, terminal 1 untuk laravel dan terminal 2 untuk vite.
untuk laravel kita bisa menggunakan

```
php artisan serve
```

setelah itu coba kita cek konfigurasi vite di vite.config.js, periksa bagian ini

```
laravel({
    input: [
        'resources/sass/app.scss',
        'resources/js/app.js',
    ],
    refresh: true,
}),
```

kita ganti untuk refreshnya menjadi seperti ini

```
laravel({
    input: [
        'resources/sass/app.scss',
        'resources/js/app.js',
    ],
    refresh: ['app/Http/**', 'resources/**'],
}),
```

kemudian untuk terminal 2 (vite)
kita bisa menggunakan

```
npm run dev
```

nah jika sudah berjalan maka ketika kita menyimpan pekerjaan kita yang terletak di resources/views misalnya maka akan dilakukan hot reload

[selesai](guide.md)
