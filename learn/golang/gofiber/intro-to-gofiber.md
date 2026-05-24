# Intro to GoFiber

GoFiber adalah web framework untuk Go yang terinspirasi dari Express.js (Node.js).
Fokus utamanya adalah performa, kemudahan, dan pengembangan API yang cepat.

## Kenapa pakai GoFiber

- Cepat dan ringan karena dibangun di atas Fasthttp.
- Sintaks sederhana dan mudah dipelajari.
- Cocok untuk REST API, backend service, dan microservice.

## Kapan sebaiknya dipakai

- Saat butuh API dengan performa tinggi.
- Saat tim ingin struktur backend yang simpel.
- Saat ingin membangun service Go dengan gaya seperti Express.

## Instalasi

1. Pastikan Go sudah terpasang.
2. Inisialisasi project:

```bash
go mod init belajar-gofiber
```

3. Install Fiber:

```bash
go get github.com/gofiber/fiber/v2
```

## Hello World

```go
package main

import "github.com/gofiber/fiber/v2"

func main() {
    app := fiber.New()

    app.Get("/", func(c *fiber.Ctx) error {
        return c.SendString("Hello, GoFiber!")
    })

    app.Listen(":3000")
}
```

## Menjalankan aplikasi

```bash
go run main.go
```

Buka browser: http://localhost:3000
