# Operasi Database

## membuat database baru

```
CREATE DATABASE namadatabase;
```

## masuk kedatabase

```
USE namadatabase;
```

## import dari database lain

```
mysql -u namauser -p namadatabase < file.sql
```

## export dari database
```
mysqldump -u namauser -p namadatabase > file.sql
```