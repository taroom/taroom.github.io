# Prisma

Prisma merupakan salah satu ORM yang didukung oleh NEST Js. untuk memulai kita bisa menuliskan perintah di terminal

```
pnpm add prisma --save-dev
atau
npm i prisma --save-dev
```

disini kita menggunakan pnpm, setelah proses instal selesai maka kita lanjutkan dengan init

```
pnpm prisma init
```

nah anda akan dibuatkan 2 file, yakni

- .env
- prisma/prisma.schema

contoh koneksi yang terdapat di .env

```
DATABASE_URL="postgresql://johndoe:randompassword@localhost:5432/mydb?schema=public"
```
