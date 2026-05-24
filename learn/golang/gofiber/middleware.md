# Middleware di GoFiber

Middleware adalah fungsi yang dieksekusi sebelum atau sesudah handler utama.

## Middleware global

```go
app.Use(func(c *fiber.Ctx) error {
    // contoh log sederhana
    fmt.Println(c.Method(), c.Path())
    return c.Next()
})
```

## Middleware bawaan Fiber

Install package middleware:

```bash
go get github.com/gofiber/fiber/v2/middleware/logger
go get github.com/gofiber/fiber/v2/middleware/cors
```

Contoh penggunaan:

```go
import (
    "github.com/gofiber/fiber/v2/middleware/cors"
    "github.com/gofiber/fiber/v2/middleware/logger"
)

app.Use(logger.New())
app.Use(cors.New())
```

## Middleware per group

```go
api := app.Group("/api", authMiddleware)
api.Get("/profile", profileHandler)
```

## Catatan

- Pastikan middleware selalu memanggil `c.Next()` jika request boleh lanjut.
- Middleware auth sebaiknya memvalidasi token sebelum masuk handler.
