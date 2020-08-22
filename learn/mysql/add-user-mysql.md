# Membuat user baru di MySQL dan MariaDB

masuk kedalam sistem db sebagai root dulu lalu ketikkan script ini :

```
CREATE USER 'namauser'@'alamatIP/localhost' IDENTIFIED BY 'passwordmu';

ex :

CREATE USER 'taroom'@'localhost' IDENTIFIED BY 'akutaroom';
CREATE USER 'taroom'@'10.10.2.222' IDENTIFIED BY 'akutaroom';
```

untuk memberikan peran/tugas pada user yang baru dibuat gunakan perintah ini :
```
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';

ex :

GRANT ALL PRIVILEGES ON * . * TO 'taroom'@'10.10.2.222';
GRANT ALL PRIVILEGES ON * . * TO 'taroom'@'localhost';
```

akhir dari aktivitas ini, kita harus me-reload permissionnya MySQL dengan 
```
FLUSH PRIVILEGES;
```