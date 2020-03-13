# Cara menggunakan git flow

### init

untuk memulai projek menggunakan pattern flow kita mengunakan :

```
git flow init
```
kita akan dihadapkan dengan beberapa pertanyaan tentang penamaan branch dan beberapa hal seperti :
* nama master (branch untuk produksi)
* nama develop (branch untuk proses membangun aplikasi)
* nama feature (branch untuk proses membangun fitur dalam aplikasi)
* nama release (branch untuk proses perilisan aplikasi ke master)
* nama hotfix (branch untuk proses pembenahan bug (biasanya dalam lingkup kecil) di yang nanti akan langsung di merge (digabungkan dengan) master)

proses ini akan menciptakan :
* folder .git beserta perangkatnya
* branch master dan develop (nama tergantung)

kemudian git akan checkout ke branch develop

### feature

karena kita sudah di folder develop, kita bisa membuat branch fitur baru dengan cara
```
git flow feature start nama_fitur
ex : git flow feature start tombolbaru
```

setelah selesai membangun fitur maka kita harus menggunakan cara 
```
git flow feature finish nama_fitur
ex : git flow feature finish tombolbaru
```