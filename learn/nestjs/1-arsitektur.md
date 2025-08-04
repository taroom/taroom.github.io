[kembali](roadmap.md)

- [referensi 1](https://www.youtube.com/playlist?list=PLhnVDNT5zYN_PfPXedWpMy_UTeYNExbfR)
- [referensi 2](https://www.udemy.com/course/nestjs-zero-to-hero)
- [referensi 3](https://www.udemy.com/course/mastering-nestjs/)
- [referensi 4](https://www.freecodecamp.org/news/the-nestjs-handbook-learn-to-use-nest-with-code-examples/)

Baik, mari kita mulai dengan point 1: Dasar-dasar NestJS. Saya akan menjelaskan setiap subpoin dengan lebih detail.

1. Pelajari arsitektur NestJS:
   NestJS adalah framework Node.js yang menggunakan TypeScript dan mengadopsi konsep arsitektur modular. Arsitektur NestJS terinspirasi dari Angular, yang membuatnya mudah dipahami bagi pengembang yang familiar dengan Angular.

   Kunci utama arsitektur NestJS:

   - Modular: Aplikasi dibagi menjadi modul-modul yang dapat digunakan kembali.
   - Dependency Injection: Memungkinkan manajemen dependensi yang efisien.
   - Decorators: Digunakan untuk menambahkan metadata ke kelas dan fungsi. hal ini lebih mirip memberikan senjata atau tools untuk yang diberikan decorator. nanti Anda akan memahami apa yang saya maksud
   - menggunakan typescript dalam pemrogramannya (lebih disarankan), namun javascript murni juga boleh aja. walaupun hasil akhir tetap akan menjadi javascript (dengan transpiller babel) dalam masa development lebih disarankan menggunakan **typescript**
   - **express.js** wrapper : membungkus [expressjs](https://expressjs.com/) dengan script yang lebih ke nest friendly. [fastify](https://fastify.dev/) juga didukung loh

2. Pahami konsep Modules, Controllers, dan Providers:

   - Modules: Unit dasar aplikasi NestJS yang mengelompokkan komponen terkait. dia seperti ketua kelompok yang mengorganisasi anggota macam, controller, service, import, export dsb
   - Controllers: Menangani http requests yang datang dari client dan mengembalikan lagi responses ke client.
   - Providers: Layanan yang menyediakan fungsionalitas tertentu dan dapat diinjeksi ke komponen lain. biasanya provider bisa dikatakan service, yang mana bertugas menghubungkan logika bisnis dengan data source macam **database**

3. Buat proyek NestJS pertama Anda:
   Untuk memulai, Anda perlu menginstal NestJS CLI dan membuat proyek baru. Berikut langkah-langkahnya:

   ```
   npm i -g @nestjs/cli
   nest new project-name
   cd project-name
   npm run start
   ```

   Setelah proyek dibuat, Anda akan melihat struktur folder dasar yang mencakup:

   - src/main.ts: Entry point aplikasi
   - src/app.module.ts: Root module aplikasi
   - src/app.controller.ts: Contoh basic controller
   - src/app.service.ts: Contoh basic service/yang berkenaan dengan data aplikasi

   Cobalah untuk memahami struktur ini dan bagaimana komponen-komponen tersebut bekerja bersama.

Untuk memulai, saya sarankan Anda:

1. Baca dokumentasi resmi NestJS untuk memahami konsep-konsep dasar.
2. Buat proyek sederhana dan eksplorasi struktur dasar yang dihasilkan terlebih dahulu.
3. Coba modifikasi controller dan service yang ada untuk memahami cara kerjanya.
4. Buat endpoint baru di controller dan lihat bagaimana itu berfungsi.

## Lanjutan

komponen-komponen utama dalam arsitektur NestJS:

### Modules:

Modules adalah inti dari organisasi aplikasi NestJS. Setiap aplikasi memiliki setidaknya satu modul, yaitu root module. Modules membantu dalam mengorganisir kode aplikasi menjadi unit-unit yang dapat dikelola.

Contoh sederhana modul:

```typescript
import { Module } from "@nestjs/common";
import { CatsController } from "./cats.controller";
import { CatsService } from "./cats.service";

@Module({
  controllers: [CatsController],
  providers: [CatsService],
})
export class CatsModule {}
```

Decorator @Module() digunakan untuk mendefinisikan sebuah modul. Properti yang umum digunakan dalam decorator ini adalah:

- **controllers**: Array dari controllers yang didefinisikan dalam modul ini. dalam contoh diatas **CatsController** yang mengarah ke file _src/cats.controller.ts_
- **providers**: Array dari services atau providers yang akan diinstansiasi oleh Nest injector. ingat kembali apa itu service sesuai petunjuk diatas
- **imports**: List dari modules yang diimpor, yang ekspornya dibutuhkan oleh modul ini.
- **exports**: Array dari providers yang harus disediakan oleh module ini untuk digunakan di modul lain yang telah mengimpor modul ini.

### Controllers:

Controllers bertanggung jawab untuk menangani incoming requests dan mengembalikan responses kepada client. Routing mechanism mengontrol controller mana yang menerima requests tertentu.

Contoh sederhana controller:

```typescript
import { Controller, Get, Post, Body } from "@nestjs/common";
import { CatsService } from "./cats.service";
import { CreateCatDto } from "./dto/create-cat.dto";

@Controller("cats")
export class CatsController {
  constructor(private catsService: CatsService) {}

  @Get()
  findAll() {
    return this.catsService.findAll();
  }

  @Post()
  create(@Body() createCatDto: CreateCatDto) {
    return this.catsService.create(createCatDto);
  }
}
```

Decorator @Controller('cats') menentukan bahwa ini adalah controller untuk route '/cats'. Decorator @Get() dan @Post() menentukan HTTP verbs methods untuk routes tertentu.

### Providers:

Providers adalah konsep fundamental dalam NestJS. Banyak kelas dasar NestJS dapat diperlakukan sebagai provider – services, repositories, factories, helpers, dan sebagainya. Ide utama di balik provider adalah bahwa ia dapat diinjeksi sebagai dependensi.

Contoh sederhana service (yang merupakan jenis provider):

```typescript
import { Injectable } from "@nestjs/common";
import { Cat } from "./interfaces/cat.interface";

@Injectable()
export class CatsService {
  private readonly cats: Cat[] = [];

  create(cat: Cat) {
    this.cats.push(cat);
  }

  findAll(): Cat[] {
    return this.cats;
  }
}
```

Decorator @Injectable() menandai kelas CatsService sebagai provider yang dapat diinjeksi ke script lain.

### Dependency Injection:

NestJS membangun sistem Dependency Injection di sekitar konsep provider. Providers dapat diinjeksi ke constructors jika didekorasi dengan @Injectable().

Contoh:

```typescript
constructor(private catsService: CatsService) {}
```

Ini adalah contoh constructor injection, di mana CatsService diinjeksi ke dalam constructor controller dari **CatsController** misalnya (lihat pada bagian controller diatas).

Memahami konsep-konsep ini akan memberikan Anda dasar yang kuat untuk memulai dengan NestJS. Saat Anda mempraktikkannya, Anda akan melihat bagaimana komponen-komponen ini bekerja bersama untuk membuat aplikasi yang terstruktur dan mudah dikelola.

Apakah ada aspek tertentu dari penjelasan ini yang ingin Anda dalami lebih lanjut?
[kembali](roadmap.md)
[Langkah - Langkah Flow Pemrograman](2.langkah-langkah-flow.md)
