# Intervention Image

adalah library yang digunakan untuk utiliti gambar, mulai crop, watermark, filter dan masih banyak lagi.

kita bisa membuat memulai dengan menggunakan perintah ini untuk menginstall intervention :

persyaratan :
* GD Image Libary / Imagick

```
composer require intervention/image -vvv
```

lalu, kita akan bisa menggunakannya dengan menggunakan :
```
use Intervention\Image\ImageManager;

// membuat instance object ImageManager dan memilih library imagenya, bisa imagick/gd tergantung yang mana yang kita install
$manager = new ImageManager(array('driver' => 'imagick'));

// mengambil image yang akan di ganti ukuran dimensinya menjadi 300 X  300
$image = $manager->make('public/foo.jpg')->resize(300, 200);
```

atau dengan cara static
```
use Intervention\Image\ImageManagerStatic as Image;

// membuat instance object ImageManager dan memilih library imagenya, bisa imagick/gd tergantung yang mana yang kita install
Image::configure(array('driver' => 'imagick'));

// mengambil image yang akan di ganti ukuran dimensinya menjadi 400 X  300
$image = Image::make('public/foo.jpg')->resize(400, 300);
```