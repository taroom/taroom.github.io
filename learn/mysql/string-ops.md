# String Operation

## Replace

berfungsi untuk menggantikan karakter

```
... REPLACE(kolom, pencarian, pengganti)

... REPLACE(nama, '.', '') AS nama_tanpa_titik

kode diatas akan mengganti titik menjadi karakter 0
```

## Char_length / LENGTH

berfungsi untuk menghitung jumlah karakter value dari kolom

```
... CHAR_LENGTH(kolom) AS jml_karakter
```

## SUBSTRING

berfungsi untuk memenggal string

```
... SUBSTRING(kolom, posisi, panjang)

... SUBSTRING('contoh isi kolom', 8, 3) // output: isi
```
