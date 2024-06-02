# Controller

kita bisa membuat sebuah controller yang bersifat resource (skema CRUD) dengan menggunakan artisan

```
php artisan make:controller UserController --resource
```

kemudian di bagian route kita sisipkan kode

```
Route::resource('users', UserController::class);
```

jika kita ingin membuat tanpa skema resource kita bisa hilangkan --resourcenya

```
php artisan make:controller UserController
```

[selesai](guide.md)
