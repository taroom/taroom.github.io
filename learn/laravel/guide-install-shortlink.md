# Laravel Shortlink

kita bisa mulai membuat aplikasi shortlink dengan mudah menggunakan [repo ini](https://github.com/ash-jc-allen/short-url) yang mana kita bisa memulainya dengan menggunakan composer

```
composer require ashallendesign/short-url
```

kemudian ketika sudah selesai install kita bisa membuat route dulu di routes/web.php

buat sebuah route baru misalkan seperti dibawah ini :

```
Route::get('/link/create', function () {
    $builder = new \AshAllenDesign\ShortURL\Classes\Builder();

    $shortURLObject = $builder->destinationUrl('https://mediatuban.com')->make();
    $shortURL = $shortURLObject->default_short_url;
    return $shortURL;
});
```

ketika kita mengunjungi {url}/link/create maka sebuat shortlink baru akan dibuat dan kita bisa langsung mengaksesnya lewat link yang telah digeneratekan, contoh link (sesuaikan port jika menggunakan php artisan serve seperti localhost -> localhost:8000)

```
http://localhost/short/k4x9e
```

[selesai](guide.md)
