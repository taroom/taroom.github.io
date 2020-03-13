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

pertanyaan yang sedang dicari :
* apakah kita bisa membuat 2 fitur bersamaan ?

### release

release adalah salah satu keadaan dimana kode siap untuk dibawa ke master (produksi) nah untuk memulai proses perilisan kita bisa menggunakan :

```
git flow release start nama_rilis
ex : git flow release start 0.0.1
```

pada proses ini kita masih bisa melakukan perbaikan dalam lingkup kecil, semisal tipo kata, kalimat dsb. setelah selesai dengan proses tersebut maka kita bisa mengakhiri release dengan cara : 
```
git flow release finish nama_rilis
ex : git flow release finish 0.0.1
```
pertanyaan yang sedang dicari :
* bagaimana cara untuk kembali ke branch develop, ketika banyak bug yang harus di perbaiki? dan bagaimana nasib branch releasenya?

### hotfix

hotfix adalah tindakan cepat untuk memperbaiki kode pasca rilis (sudah di branch master), nah untuk membuat sebuah tindakan hotfix kita bisa menggunakan cara :
```
git flow hotfix start nama_hotfix
ex : git flow hotfix start nama_hotfix
```

### Bonus
silahkan copy paste script berikut ini untuk bisa digunakan di terminal (menyingkat perintah) :
bisa digunakan untuk terminal git bash for windows atau di linux bisa di pasang di .bashrc

```
alias gfi='git flow init'
alias gffs='git flow feature start'
alias gfff='git flow feature finish'
alias gfhs='git flow hotfix start'
alias gfhf='git flow hotfix finish'
alias gfrs='git flow release start'
alias gfrf='git flow release finish'

contoh penggunaan diterminal :
gffs fitur_button
gfff fitur_button
```