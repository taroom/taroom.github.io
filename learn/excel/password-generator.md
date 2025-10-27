# Password Generator

formula untuk membuat password

```excel
=MID("123456789";RANDBETWEEN(1;9);1)&
MID("123456789";RANDBETWEEN(1;9);1)&
MID("123456789";RANDBETWEEN(1;9);1)&
MID("123456789";RANDBETWEEN(1;9);1)&
MID("ABCDEFGHIJKLMNPQRSTUVWXYZ";RANDBETWEEN(1;25);1)&
MID("ABCDEFGHIJKLMNPQRSTUVWXYZ";RANDBETWEEN(1;25);1)&
MID("ABCDEFGHIJKLMNPQRSTUVWXYZ";RANDBETWEEN(1;25);1)&
MID("ABCDEFGHIJKLMNPQRSTUVWXYZ";RANDBETWEEN(1;25);1)
```

formula diatas akan menghasilkan password acak yang terdiri dari 4 angka dan 4 huruf kapital (tanpa huruf O untuk menghindari kebingungan dengan angka 0).
