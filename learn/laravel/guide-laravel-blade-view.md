# Laravel Blade View

pastikan extensi yang semula **index.php** menjadi **index.blade.php**

## Contoh Form Dengan Inputan Lengkap

```
<form action="{{ route('tujuan') }}" method="POST">
    @csrf
    <input type="text" id="t" name="t" class="form-control">
    <select class="form-control" id="s" name="s">
        <option value="1">1</option>
        <option value="1">1</option>
        <option value="1">1</option>
    </select>

    <button type="submit">Kirim</button>
</form>
```

[selesai](guide.md)
