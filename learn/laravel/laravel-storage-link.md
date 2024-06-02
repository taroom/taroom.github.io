# Laravel Storage Link

untuk menghubungkan antara folder storage dan public/storage kita bisa menggunakan perintah artisan sebagai berikut :

```
php artisan storage:link
```

namun jika tidak bisa maka kita bisa menggunakan perintah ini untuk membuat soft link antar folder storage dan public/storage

```
ln -s ../storage/app/public storage
```

pastikan anda dapat mengakses SSH atau Terminal lalu posisikan path anda di folder public
src : [disini](https://stackoverflow.com/questions/70381201/call-to-undefined-function-illuminate-filesystem-symlink)
