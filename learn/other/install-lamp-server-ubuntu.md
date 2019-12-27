# Install LAMP untuk Laptop Installan Baru

pertama install LAMP Server dengan menggunakan perintah :

```
sudo apt install lamp-server^
```

perintah diatas akan menginstall apache2, php (terakhir) dan mysql 5.7

kalau sudah kita bisa install phpmyadmin
```
sudo apt install phpmyadmin
```

kemudian kita membuat user baru mysql dengan cara masuk ke terminal ketikkan perintah 
```
sudo mysql -u root -p
```

lalu ikuti panduan ini untuk membuat user baru

[buat user mysql](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql)

installing sublimetext 3

```
sudo apt install sublime-text
```

install teamviewer
-download di website teamviewer

install composer
```
sudo apt install composer
```

install nodejs
```
sudo apt install nodejs
```

install npm
```
sudo apt install npm
```

install bower
```
sudo npm install -g bower
```

[setting virtual host](../apache2/setting-domain-local.md)

install git
```
sudo apt install git
```

connect to gitlab with ssh
```
- buat key baru
ssh-keygen -t rsa

- output file key.pub
cat /filepub_rsa

- copykan string ke gitlab
```
coba git clone kesalah satu contoh project

ketikkan composer install -vvv

