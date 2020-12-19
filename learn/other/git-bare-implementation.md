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

lalu siapkan working foldernya : misalkan lomdeskel


nah didalam /bare_lomdeskel/hooks buat sebuah file dengan nama post-receive, isinya :
```
#!/bin/sh
git --work-tree=/var/www/lomdeskel --git-dir=/var/www/bare_lomdeskel checkout -f
```

setelah itu berikan akses executable dengan cara :
```
sudo chmod +x post-receive
```

setelah itu cobalah untuk melakukan git push dari repo lokal ke repo vps
```
git push live master
```

untuk yang menggunakan non-bare biasanya akan ada error

untuk bisa solved bisa pakai cara ini :
```
https://stackoverflow.com/questions/12265729/what-are-the-consequences-of-using-receive-denycurrentbranch-in-git
```