# SQl Column And Table

berbagai script yang mungkin nanti berguna ketika kita sedang mengerjakan projek yang melibatkan database mysql :

### script untuk mengambil nama kolom di dalam database

```SQL
DESCRIBE `nama_table`;
```

script diatas akan menampilkan daftar kolom yang ada di dalam tabel

```SQL
SELECT `COLUMN_NAME`
FROM `INFORMATION_SCHEMA`.`COLUMNS`
WHERE `TABLE_SCHEMA`='yourdatabasename'
    AND `TABLE_NAME`='yourtablename';
```

referensi :

- https://stackoverflow.com/questions/4165195/mysql-query-to-get-column-names/4165253

### script untuk mengambil nama nama tabel dalam database

```SQL
SHOW TABLES;
```

referensi :

- https://www.linuxid.net/31885/cara-menampilkan-semua-table-di-mysql-database/
