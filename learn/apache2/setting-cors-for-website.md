# Setting CORS untuk interkoneksi antar website lokal
- cukup taruh .htaccess di folder web yang melarang origin
isi .htaccess
```
Header set Access-Control-Allow-Origin "*"
```

- jika diperlukan aktifkan header
```
a2enmod headers
```

- reload apache2
```
sudo service apache2 refresh/reload
```

Referensi : 

* https://tecadmin.net/set-access-control-allow-origin-cors-in-apache/
* https://enable-cors.org/server_apache.html
