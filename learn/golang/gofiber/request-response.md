# Request dan Response di GoFiber

Memahami request/response penting untuk membuat API yang rapi.

## Membaca body JSON

```go
type LoginRequest struct {
    Email    string `json:"email"`
    Password string `json:"password"`
}

app.Post("/login", func(c *fiber.Ctx) error {
    var req LoginRequest

    if err := c.BodyParser(&req); err != nil {
        return c.Status(fiber.StatusBadRequest).JSON(fiber.Map{
            "message": "Format body tidak valid",
        })
    }

    return c.JSON(fiber.Map{
        "email": req.Email,
    })
})
```

## Mengirim JSON response

```go
return c.Status(fiber.StatusCreated).JSON(fiber.Map{
    "message": "Data berhasil dibuat",
    "data":    result,
})
```

## Header dan status code

```go
c.Set("X-App-Name", "Belajar-GoFiber")
return c.SendStatus(fiber.StatusNoContent)
```

## Validasi sederhana

- Cek field wajib terisi.
- Kembalikan status code sesuai kondisi.
- Gunakan format response error yang konsisten.
