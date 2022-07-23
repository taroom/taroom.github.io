# Using CodeCeption on Yii2

## Bootstraping

langkah ini digunakan untuk mempersiapkan konfigurasi codeception yang dapat digunakan untuk testing projek

```
php vendor/bin/codecept bootstrap
```

## Macam Testing

    - Unit Testing. Pengujian terkecil baik menguji metode fungsi di class dsb
    - Functional Testing
    - Acceptance Testing

## Konfigurasi (Berdasarkan Pengalaman Menggunakan Codeception x Yii2)

- Membuat file konfigurasi
  - acceptance.suite.yml
  - functional.suite.yml
  - unit.suite.yml
- Memberikan namespace
- configFile are required di Yii2 (jika cc digunakan dengan framework)
- membuat aktor (yang akan mengeksekusi testing) dengan cara

```
php vendor/bin/codecept build

jika hasil build belum ada namespace, kasih namespace
```

[Contoh Konfigurasi](conf-example-yii.md)

## Membuat File Testing

```
php vendor/bin/codecept generate:cept|cest|test suite[acceptance|functional|unit] TestFileName

ex:
php vendor/bin/codecept generate:cept unit Welcome
php vendor/bin/codecept generate:cept functional Welcome
php vendor/bin/codecept generate:cest acceptance Welcome

hasil file cept menjadi WelcomeCept.php
hasil file cest menjadi WelcomeCest.php
```

### kegunaan CEPT | CEST | TEST (Test Format)

**Cept**
Digunakan untuk membuat sebuah testing sederhana

**Cest**
Digunakan untuk membuat testing dengan bentuk class

**Test**
Digunakan untuk membuat testing menggunakan PHPUnit (??)

### Mengubah file hasil generate test

misalkan kita menggunakan format test cept dan tipe testing Acceptance, biasanya file akan diletakkan di folder **test/acceptance/WelcomeCept**

kita bisa menggunakan I Want To untuk menulis judulnya

## How To RUN Codeception Testing in Yii2

```
php vendor/codeception/codeception/codecept run

atau menggunakan

php vendor/bin/codecept run
```
