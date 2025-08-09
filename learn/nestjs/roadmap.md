# Nest JS

## Reference

- Programmer Zaman Now
  - https://youtu.be/BXTEwuoDkDQ?si=Dn-Q9khR2fR-_Ogc&t=1917 (2025-08-05 00:19:57)
- Tech Vision
  - https://www.youtube.com/watch?v=IdsBwplQAMw

## Dasar-dasar NestJS

- Pelajari arsitektur NestJS
- Pahami konsep Modules, Controllers, dan Providers
- Buat proyek NestJS pertama Anda

  [klik disini](1-arsitektur.md)

  [Langkah-Langkah pemrograman ](2.langkah-langkah-flow.md)

## Apa yang bisa Anda buat dengan Nest JS

- Restfull API
- Microservice (mirip restfull API tapi bisa berkomunikasi tak hanya dengan https aja, contoh bisa menggunakan TCP, NAT dsb)
- Standalone Aplikasi, aplikasi yang tidak punya listener jaringan, contohnya: CLI Tools, Scheduling Task Tool

dari semua itu, yang menjadi benang merah dari semuanya adalah mereka semua butuh 1 modul utama (root module) lihat bagian module

## CLI

Nest Add Packages [klik disini](30.nest-cli-add.md)

## Routing dan Controllers

- Pelajari pembuatan routes
- Implementasikan HTTP methods (GET, POST, PUT, DELETE)
- Gunakan route parameters dan query strings
- **dto** data transfer object [klik disini](10.dto.md)

## Providers dan Dependency Injection

- Pahami konsep Dependency Injection di NestJS
- Buat dan gunakan Custom Providers
- Pelajari Scopes (Singleton, Request, Transient)

## Modules

- module explanation. [lihat disini](3.module.md)
- Buat dan organisasikan Modules
- Pelajari Module importing dan exporting

## Middleware

- Implementasikan Middleware functions
- Gunakan Built-in Middleware
- Buat Custom Middleware

## Exception Handling

- Pelajari Exception filters
- Implementasikan Custom exceptions

## Pipes

- Gunakan Built-in Pipes untuk validasi dan transformasi
- Buat Custom Pipes

## Guards

- Implementasikan Authentication Guards
- Buat Custom Guards untuk Authorization

## Interceptors

- Pelajari penggunaan Interceptors
- Implementasikan logging dan transformasi response

## Custom Decorators

- Buat dan gunakan Custom Decorators

## Database Integration

- Integrasi dengan database (misalnya, TypeORM atau Mongoose)
- Buat CRUD operations

## Validation

- Implementasikan validasi menggunakan class-validator

## Caching

- Pelajari dan implementasikan caching strategies

## File Upload

- Implementasikan file upload functionality

## Task Scheduling

- Pelajari dan gunakan @nestjs/schedule untuk cron jobs

## WebSockets

- Implementasikan real-time communication dengan WebSockets

## GraphQL

- Pelajari integrasi GraphQL dengan NestJS
- Buat GraphQL API

## Testing

- Tulis unit tests
- Implementasikan integration tests
- Lakukan e2e testing

## Deployment

- Pelajari proses deployment NestJS applications

## Best Practices dan Advanced Topics

- Pelajari NestJS best practices
- Eksplorasi topik lanjutan seperti microservices atau serverless

## Library Yang Dapat Digunakan Di Nest

library bersifat pribadi pengalaman mempelajari

- zod
- bcrypt
- typeorm
- mongoose (untuk koneksi ke mongodb)
- dsb
  [klik disini](100.library-yang-dapat-digunakan-di-nest.md)
