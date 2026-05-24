# Struktur Project GoFiber

Struktur folder yang rapi memudahkan scaling aplikasi.

## Contoh struktur

```text
belajar-gofiber/
  cmd/
    api/
      main.go
  internal/
    handler/
    service/
    repository/
    model/
  pkg/
    response/
  configs/
  go.mod
```

## Penjelasan singkat

- `cmd/api/main.go`: entry point aplikasi.
- `internal/handler`: menerima request dan mengembalikan response.
- `internal/service`: business logic.
- `internal/repository`: akses data/database.
- `internal/model`: definisi struct dan entity.
- `pkg/response`: helper response agar format API konsisten.

## Rekomendasi

- Pisahkan logic HTTP, business logic, dan data access.
- Hindari business logic tebal di handler.
- Gunakan environment variable untuk konfigurasi.

---

[<- Kembali ke Index](index.md)
