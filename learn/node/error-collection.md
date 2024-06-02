# Daftar Error yang Mungkin Bisa Diperbaiki

## NPM Install Error:Unexpected end of JSON input while parsing near

adalah error ketika saya menginstall node js, terjadi ketika akan menggunakan NPM untuk menginstall package secara global

```
npm i -g package
```

kita bisa memperbaikinya dengan cara membersihkan cache npm terlebih dahulu (firts aid)

```
npm cache clean --force

npm i -g package
ex : npm i -g @vue/cli
```

---
