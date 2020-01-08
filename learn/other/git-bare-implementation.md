# catatan git bare pada vps

- buat sebuah folder : misalkan bare_lomdeskel
- hak akses 777
```
chmod -R 777 bare_lomdeskel
```
- git bare
```
cd bare_lomdeskel
git init --bare
```


dari lokal buat sebuah koneksi lain di repo local (selain origin)
```
git remote add live ssh://ds@36.66.195.234:1097/var/www/bare_lomdeskel
```

lalu siapkan working foldernya