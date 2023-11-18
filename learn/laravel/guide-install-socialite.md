# Instalasi Socialite

socialite adalah library yang dapat digunakan untuk login melalui social media di laravel

```
composer require laravel/socialite
```

## persiapan awal

kita harus menyiapkan user dan optional tabel yang menurut saya diperlukan untuk mencatat social login mana saja yang telah masuk. untuk **user** sudah dibuatkan oleh laravel. kita cuma perlu membuat migrasi untuk social loginnya.

silahkan membuat migrasi dulu

```
php artisan make:model SocialAccount -m
```

dengan perintah ini maka kita memiliki 2 file yang akan digenerate oleh artisan

- app\Models\SocialAccount.php
- database\migrations\tanggal_dibuat_social_accounts.php

kita mulai dari tanggal_dibuat_social_accounts.php

pastikan isi up-nya sesuai seperti ini :

```
public function up()
{
  Schema::create('social_accounts', function (Blueprint $table) {
    $table->id();
    $table->bigInteger('user_id');
    $table->string('provider_id')->unique();
    $table->string('provider_name');
    $table->timestamps();
  });
}
```

kalau sudah langsung saja pada terminal

```
php artisan migrate
```

## menambahkan relasi

tambahkan pada file app\Models\User.php

```
public function socialAccounts()
{
  return $this->hasMany(SocialAccount::class);
}
```

tambahkan pada file app\Models\SocialAccount.php

```
public function user()
{
  return $this->belongsTo(User::class);
}
```

## konfigurasi

taruh script di file app/config/service.php

```
'facebook' => [
        'client_id' => env('FACEBOOK_CLIENT_ID'),
        'client_secret' => env('FACEBOOK_CLIENT_SECRET'),
        'redirect' => env('FACEBOOK_CLIENT_REDIRECT'),
],
'google' => [
        'client_id' => env('GOOGLE_CLIENT_ID'),
        'client_secret' => env('GOOGLE_CLIENT_SECRET'),
        'redirect' => env('GOOGLE_CLIENT_REDIRECT'),
],
```

sekarang agar tidak error tambahkan ini di file .env

```
GOOGLE_CLIENT_ID=token_id
GOOGLE_CLIENT_SECRET=token_secret
GOOGLE_CLIENT_REDIRECT=http://localhost:8000/auth/google/callback

GITHUB_CLIENT_ID=token_id
GITHUB_CLIENT_SECRET=token_secret
GITHUB_CLIENT_REDIRECT=http://localhost:8000/auth/github/callback
```

untuk client redirect tolong disesuaikan saja.

## route

nah karena pada file env kita mengarahkan ke alamat /auth/xxx/callback kita harus membuat router rule di router/web.php

```
Route::get('/auth/{provider}', [SocialiteController::class, 'redirectToProvider']);
Route::get('/auth/{provider}/callback', [SocialiteController::class, 'handleProvideCallback']);
```

Route pertama untuk menuju sosmednya, Route kedua digunakan untuk menghandle callback dari token yang didapat saat telah memilih sosmed

## file SocialiteController

kita bisa tulis di terminal seperti dibawah ini untuk membuat controller baru

```
php artisan make:controller Auth/SocialiteController
```

lalu isikan isinya seperti berikut

```
<?php

namespace App\Http\Controllers\Auth;

use App\Http\Controllers\Controller;
use App\Models\SocialAccount;
use App\Models\User;
use Illuminate\Http\Request;
use Laravel\Socialite\Facades\Socialite;

class SocialiteController extends Controller
{
    public function redirectToProvider($provider)
    {
        return Socialite::driver($provider)->redirect();
    }

    public function handleProvideCallback($provider)
    {
        try {

            $user = Socialite::driver($provider)->stateless()->user();
        } catch (Exception $e) {
            return redirect()->back();
        }
        // find or create user and send params user get from socialite and provider
        $authUser = $this->findOrCreateUser($user, $provider);

        // login user
        Auth()->login($authUser, true);

        // setelah login redirect ke dashboard
        return redirect()->route('dashboard');
    }

    public function findOrCreateUser($socialUser, $provider)
    {
        // Get Social Account
        $socialAccount = SocialAccount::where('provider_id', $socialUser->getId())
            ->where('provider_name', $provider)
            ->first();

        // Jika sudah ada
        if ($socialAccount) {
            // return user
            return $socialAccount->user;

            // Jika belum ada
        } else {

            // User berdasarkan email
            $user = User::where('email', $socialUser->getEmail())->first();

            // Jika Tidak ada user
            if (!$user) {
                // Create user baru
                $user = User::create([
                    'name'  => $socialUser->getName(),
                    'email' => $socialUser->getEmail()
                ]);
            }

            // Buat Social Account baru
            $user->socialAccounts()->create([
                'provider_id'   => $socialUser->getId(),
                'provider_name' => $provider
            ]);

            // return user
            return $user;
        }
    }
}
```

## membuat link login via sosmed di halaman login

buka file resources/views/auth/login.php

tambahkan script dibawah ini

```
<a href="{{ url('/auth/google') }}" class="btn btn-danger">Login Via Google</a>

<a href="{{ url('/auth/facebook') }}" class="btn btn-primary">Login Via Facebook</a>
```

[selesai](guide.md)
