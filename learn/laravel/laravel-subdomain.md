# Laravel Subdomain

jika anda menginginkan satu instance laravel mengakomodir subdomain anda seperti app.example.com atau sub.example.com, sangat mudah sekali ternyata, saya menghabiskan 2 hari untuk mempelajari ini ternyata kesalahannya sederhana sekali yaitu pengurutan scriptnya. ok begini langkahnya.

1. buka file di app\Providers\RouteServiceProvider.php
2. tambahkan script dibawah ini ganti domain dan file routenya, (ingat! tempatkan diurutan atas)

```
Route::domain('link.contoh.com')
->group(base_path('routes/link-subdomain.php'));
```

3. kemudian buat sebuat file di route, beri nama link-subdomain.php atau sesuai kasus kamu. isinya :

```
<?php

use App\Http\Controllers\AdsController;
use Illuminate\Http\Request;
use Illuminate\Support\Facades\Route;
use App\Http\Controllers\LinkController;

/*
|--------------------------------------------------------------------------
| Web Routes
|--------------------------------------------------------------------------
|
| Here is where you can register web routes for your application. These
| routes are loaded by the RouteServiceProvider within a group which
| contains the "web" middleware group. Now create something great!
|
*/


Route::get('/', [LinkController::class, 'index'])->name('link.index');
Route::get('/about', [LinkController::class, 'about'])->name('link.about');
Route::get('/preview/{id}', [LinkController::class, 'preview'])->name('link.preview');
```

4. Buat subdomain di hosting Anda. jika public folder untuk aplikasi laravel anda berada di public_html, isi document rootnya subdomain juga di public_html
5. Selesai

[selesai](guide.md)
