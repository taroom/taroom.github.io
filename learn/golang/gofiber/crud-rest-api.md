# CRUD REST API dengan GoFiber

Contoh endpoint CRUD sederhana untuk resource `products`.

## Daftar endpoint

- GET `/api/v1/products`
- GET `/api/v1/products/:id`
- POST `/api/v1/products`
- PUT `/api/v1/products/:id`
- DELETE `/api/v1/products/:id`

## Contoh struktur data

```go
type Product struct {
    ID    int     `json:"id"`
    Name  string  `json:"name"`
    Price float64 `json:"price"`
}
```

## Contoh create handler

```go
app.Post("/api/v1/products", func(c *fiber.Ctx) error {
    var payload Product

    if err := c.BodyParser(&payload); err != nil {
        return c.Status(fiber.StatusBadRequest).JSON(fiber.Map{
            "message": "Payload tidak valid",
        })
    }

    // Simulasi insert data
    payload.ID = 1

    return c.Status(fiber.StatusCreated).JSON(fiber.Map{
        "message": "Product dibuat",
        "data":    payload,
    })
})
```

## Langkah pengembangan

1. Mulai dari in-memory data untuk memahami alur.
2. Lanjut ke database (MySQL/PostgreSQL) saat alur sudah benar.
3. Tambahkan validasi, pagination, dan filter.

---

[<- Kembali ke Index](index.md)
