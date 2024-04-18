# Linux Find Operation

## Find

berfungsi untuk mencari file

```
find /var/www/html/ -type f -name '.*.php'
```

find path_lokasi_pencarian -type f -name '.\*.php' ini akan mencari file dengan format :

- .apasih.php
- .adalahh.php
- .kadang.php

### Find Then Delete

```
find /var/www/html/ -type f -name '.*.php' -delete
```

tambahan -delete akan menghapus semua file tanpa konfirmasi, jadi pastikan list yang muncul (sebelum diberi opsi -delete) adalah sesuai dengan harapan Anda.

### Find Then Output As File

```
find /var/www/html/ -type f -name '.*.php' > /your/location/note.txt
```

ini akan menyimpan output ke file note.txt harap pastikan kemana akan disimpan

https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/
