# Basic Routing di GoFiber

Routing adalah cara aplikasi menentukan handler berdasarkan URL dan method HTTP.

## Method routing dasar

```go
app.Get("/", homeHandler)
app.Post("/users", createUserHandler)
app.Put("/users/:id", updateUserHandler)
app.Delete("/users/:id", deleteUserHandler)
```

## Route parameter

```go
app.Get("/users/:id", func(c *fiber.Ctx) error {
    id := c.Params("id")
    return c.JSON(fiber.Map{"id": id})
})
```

## Query parameter

```go
app.Get("/search", func(c *fiber.Ctx) error {
    q := c.Query("q")
    return c.JSON(fiber.Map{"query": q})
})
```

## Group route

```go
api := app.Group("/api")
v1 := api.Group("/v1")

v1.Get("/health", func(c *fiber.Ctx) error {
    return c.SendString("ok")
})
```

## Tips

- Gunakan path yang konsisten, misalnya semua endpoint API diawali `/api/v1`.
- Gunakan nama route yang jelas dan mudah dibaca.

---

[<- Kembali ke Index](index.md)
