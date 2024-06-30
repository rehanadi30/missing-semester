---
layout: lecture
title: "Course overview + the shell"
date: 2020-01-13
ready: true
video:
  aspect: 56.25
  id: Z56Jmr9Z34Q
---

# Motivation

Sebagai _computer scientist_, kita tahu bahwa komputer sangat baik 
dalam membantu tugas-tugas yang sifatnya repetitif. Namun, terlalu sering, 
kita lupa bahwa hal ini berlaku sama halnya dengan penggunaan 
komputer yang kita gunakan dan juga perhitungan yang kita 
inginkan untuk dilakukan oleh program kita. Kita memiliki berbagai 
macam alat yang tersedia di ujung jari kita yang memungkinkan kita 
untuk menjadi lebih produktif dan memecahkan masalah yang lebih kompleks 
ketika mengerjakan masalah yang berhubungan dengan komputer. Namun, 
banyak dari kita yang hanya menggunakan sebagian kecil dari alat-alat 
tersebut; kita hanya mengetahui mantra-mantra ajaib yang dihafalkan, 
dan menyalin-tempel secara membabi buta perintah-perintah dari internet 
ketika kita mengalami kebuntuan.

Kelas ini adalah upaya untuk mengatasi hal ini.

Kami ingin mengajari Anda cara memaksimalkan alat yang Anda ketahui, 
menunjukkan kepada Anda alat baru untuk ditambahkan ke kotak peralatan Anda, 
dan mudah-mudahan menanamkan dalam diri Anda beberapa kegembiraan untuk menjelajahi 
(dan mungkin membangun) lebih banyak alat sendiri. Inilah yang kami yakini 
sebagai semester yang hilang dari sebagian besar kurikulum Ilmu Komputer.

# Class structure

Kelas ini terdiri dari 11 kuliah 1 jam, masing-masing berpusat pada
[particular topic](/2020/). Sebagian besar perkuliahan bersifat mandiri,
meskipun seiring berjalannya semester, kami akan menganggap bahwa Anda sudah terbiasa
dengan materi kuliah sebelumnya. Kami memiliki catatan kuliah
online, tetapi akan ada banyak konten yang dibahas di kelas (mis.
dalam bentuk demo) yang mungkin tidak ada dalam catatan. Kami akan merekam
kuliah dan memposting rekaman secara online.

Kami mencoba untuk mencakup banyak hal hanya dalam waktu 11 jam
kuliah, jadi kuliahnya cukup padat. Untuk memberi Anda waktu untuk
membiasakan diri dengan konten dengan kecepatan Anda sendiri, setiap kuliah mencakup
serangkaian latihan yang memandu Anda melalui poin-poin utama kuliah. Setelah
Setelah setiap kuliah, kami mengadakan jam kerja di mana kami akan hadir untuk
membantu menjawab pertanyaan yang mungkin Anda miliki. Jika Anda menghadiri kelas
online, Anda dapat mengirimkan pertanyaan kepada kami di
[missing-semester@mit.edu](mailto:missing-semester@mit.edu).

Karena keterbatasan waktu yang kami miliki, kami tidak dapat membahas semua kakas
dengan tingkat detail yang sama seperti yang bisa dilakukan oleh kelas skala penuh. Jika memungkinkan, kami
akan mencoba mengarahkan Anda ke sumber daya untuk menggali lebih jauh ke dalam alat
atau topik, tetapi jika ada sesuatu yang menarik perhatian Anda, jangan
ragu untuk menghubungi kami dan meminta petunjuk!

# Topik 1: Shell

## Apa itu shell?

Komputer saat ini memiliki berbagai antarmuka untuk memberikan
perintah; antarmuka pengguna grafis yang fantastis, antarmuka suara, dan
bahkan AR/VR ada di mana-mana. Semua ini sangat bagus untuk 80% kasus penggunaan, tetapi
mereka sering kali secara fundamental dibatasi dalam hal apa yang dapat Anda lakukan -
Anda tidak dapat menekan tombol yang tidak ada di sana atau memberikan perintah suara itu
belum diprogram. Untuk memanfaatkan sepenuhnya alat yang disediakan komputer Anda
komputer Anda, kita harus menggunakan cara lama dan turun ke
antarmuka: Shell.

Hampir semua platform yang bisa Anda dapatkan memiliki shell dalam satu bentuk atau
lain, dan banyak di antaranya memiliki beberapa shell yang dapat Anda pilih.
Meskipun mereka mungkin berbeda dalam detailnya, pada intinya mereka semua kurang lebih
sama: mereka memungkinkan Anda untuk menjalankan program, memberi mereka masukan, dan memeriksa
output mereka dengan cara semi-terstruktur.

Dalam kuliah ini, kita akan fokus pada Bourne Again SHell, atau "bash" untuk
singkatnya. Ini adalah salah satu shell yang paling banyak digunakan, dan sintaksnya adalah
mirip dengan apa yang akan Anda lihat di banyak shell lainnya. Untuk membuka sebuah shell
_prompt_ (tempat Anda dapat mengetikkan perintah), pertama-tama Anda memerlukan _terminal_.
Perangkat Anda mungkin dikirimkan dengan satu terminal yang sudah terinstal, atau Anda dapat menginstalnya
cukup mudah.

## Menggunakan shell

Ketika Anda meluncurkan terminal, Anda akan melihat _prompt_ yang sering terlihat
yang sering terlihat seperti ini:

```console
missing:~$ 
```

Ini adalah antarmuka tekstual utama ke shell. Ini memberitahukan Anda bahwa Anda
Anda sedang berada pada mesin `missing` dan bahwa "_current working directory_" (direktori kerja saat ini) Anda
atau tempat Anda saat ini berada, adalah `~` (kependekan dari "home"). Tanda `$` memberitahukan kepada Anda
bahwa Anda bukan pengguna root (akan dijelaskan lebih lanjut nanti). Pada perintah ini, Anda
Anda dapat mengetikkan sebuah _command_, yang kemudian akan diinterpretasikan oleh shell. 
Perintah-perintah yang paling dasar adalah mengeksekusi sebuah program:

```console
missing:~$ date
Fri 10 Jan 2020 11:49:31 AM EST
missing:~$ 
```

Di sini, kami menjalankan program `date`, yang (secara gamblang)
mencetak tanggal dan waktu saat ini. Shell kemudian meminta kita untuk meminta perintah lain
lain untuk dieksekusi. Kita juga dapat menjalankan perintah dengan _arguments_:

```console
missing:~$ echo hello
hello
```

Dalam kasus ini, kita memberitahu shell untuk mengeksekusi program `echo` dengan argumen
argumen `hello`. Program `echo` hanya mencetak argumennya.
Shell menguraikan perintah dengan memisahkannya dengan spasi, dan kemudian
menjalankan program yang ditunjukkan oleh kata pertama, menyediakan setiap kata berikutnya
berikutnya sebagai argumen yang dapat diakses oleh program. Jika Anda ingin memberikan
argumen yang berisi spasi atau karakter khusus lainnya (mis.
direktori bernama "_My Photos_"), Anda dapat mengutip argumen dengan `'` atau `"` (`"My Photos").
atau `"` (`"My Photos"`), atau keluarkan hanya karakter yang relevan dengan `\`
(`My Photos`).

Tetapi bagaimana shell tahu bagaimana menemukan program `date` atau `echo`?
Nah, shell adalah sebuah lingkungan pemrograman, seperti halnya Python atau Ruby,
sehingga memiliki variabel, kondisional, perulangan, dan fungsi (selanjutnya
kuliah berikutnya!). Ketika Anda menjalankan perintah dalam shell, Anda sebenarnya sedang menulis
sedikit kode yang ditafsirkan oleh shell Anda. Jika shell diminta untuk
mengeksekusi perintah yang tidak sesuai dengan salah satu kata kunci pemrogramannya, shell akan
berkonsultasi dengan sebuah variabel _environment_ yang disebut `$PATH` yang berisi daftar
direktori mana yang harus dicari oleh shell untuk program ketika diberi
perintah:


```console
missing:~$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
missing:~$ which echo
/bin/echo
missing:~$ /bin/echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```

Ketika kita menjalankan perintah `echo`, shell melihat bahwa ia harus mengeksekusi
program `echo`, dan kemudian mencari melalui daftar `:` yang terpisah dari
direktori di `$PATH` untuk mencari file dengan nama tersebut. Ketika ia menemukannya, ia akan
menjalankannya (dengan asumsi bahwa file tersebut _executable_; akan dibahas lebih lanjut nanti). Kita dapat
mengetahui file mana yang dieksekusi untuk nama program tertentu dengan menggunakan perintah
program `which`. Kita juga dapat melewati `$PATH` secara keseluruhan dengan memberikan perintah
_path_ pada file yang ingin kita eksekusi.

## Bernavigasi di dalam shell

Jalur pada shell adalah daftar direktori yang dibatasi; dipisahkan dengan `/`
di Linux dan macOS dan `\` di Windows. Di Linux dan macOS, jalur `/`
adalah "root" dari sistem file, di mana semua direktori dan file
terletak, sedangkan pada Windows ada satu root untuk setiap partisi disk (mis,
`C:\`). Pada umumnya kita akan mengasumsikan bahwa Anda menggunakan sistem file Linux
Linux dalam kelas ini. Jalur yang dimulai dengan `/` disebut jalur _absolute_.
Jalur lainnya adalah jalur _relatif_. Jalur relatif adalah relatif terhadap direktori
direktori kerja saat ini, yang dapat kita lihat dengan perintah `pwd` dan
mengubahnya dengan perintah `cd`. Pada sebuah path, `.` merujuk pada direktori
saat ini, dan `..` ke direktori induknya:

```console
missing:~$ pwd
/home/missing
missing:~$ cd /home
missing:/home$ pwd
/home
missing:/home$ cd ..
missing:/$ pwd
/
missing:/$ cd ./home
missing:/home$ pwd
/home
missing:/home$ cd missing
missing:~$ pwd
/home/missing
missing:~$ ../../bin/echo hello
hello
```

Perhatikan bahwa shell prompt kita memberi informasi kepada kita tentang apa
direktori kerja kita saat ini. Anda dapat mengkonfigurasi prompt Anda untuk menampilkan semua
berbagai macam informasi yang berguna, yang akan kita bahas pada kuliah selanjutnya.

Pada umumnya, ketika kita menjalankan sebuah program, program tersebut akan beroperasi pada direktori
direktori saat ini, kecuali jika kita memerintahkan sebaliknya. Sebagai contoh, biasanya program akan
mencari file di sana, dan membuat file baru di sana jika diperlukan.

Untuk melihat apa yang ada pada direktori tertentu, kita menggunakan _command_ `ls`:

```console
missing:~$ ls
missing:~$ cd ..
missing:/home$ ls
missing
missing:/home$ cd ..
missing:/$ ls
bin
boot
dev
etc
home
...
```

Kecuali jika sebuah direktori diberikan sebagai argumen pertama, `ls` akan mencetak
isi dari direktori saat ini. Kebanyakan perintah menerima flag dan
pilihan (flag dengan nilai) yang dimulai dengan `-` untuk memodifikasi
perilaku mereka. Biasanya, menjalankan sebuah program dengan flag `-h` atau `--help` akan
akan mencetak beberapa teks bantuan yang memberitahukan Anda flag dan pilihan
dan pilihan apa saja yang tersedia. Sebagai contoh, `ls --help` memberitahukan kepada kita:

```
  -l                         use a long listing format
```

```console
missing:~$ ls -l /home
drwxr-xr-x 1 missing  users  4096 Jun 15  2019 missing
```

Ini memberi kita lebih banyak informasi tentang setiap file atau direktori
yang ada. Pertama, `d` pada awal baris memberitahukan kita bahwa
`missing` adalah sebuah direktori. Kemudian ikuti tiga kelompok yang terdiri dari tiga karakter
(`rwx`). Ini menunjukkan hak akses yang dimiliki oleh pemilik file
(`missing`), grup pemilik (`users`), dan semua orang
memiliki pada item yang relevan. Tanda `-` menunjukkan bahwa prinsipal yang diberikan tidak
tidak memiliki izin yang diberikan. Di atas, hanya pemilik yang diizinkan untuk
memodifikasi (`w`) direktori `missing` (misalnya, menambah/menghapus file di dalamnya). Untuk
Untuk masuk ke sebuah direktori, pengguna harus memiliki hak akses "search" (diwakili oleh "execute":
`x`) pada direktori tersebut (dan induknya). Untuk membuat daftar
isi, seorang pengguna harus memiliki hak akses read (`r`) pada direktori tersebut. Untuk
Untuk file-file, hak aksesnya seperti yang Anda harapkan. Perhatikan bahwa hampir semua
file di `/bin` memiliki izin `x` yang disetel untuk kelompok terakhir,
"semua orang", sehingga semua orang dapat mengeksekusi program-program tersebut.

Beberapa program lain yang berguna untuk diketahui pada saat ini adalah `mv` (untuk
mengganti nama/memindahkan file), `cp` (untuk menyalin file), dan `mkdir` (untuk membuat
direktori baru).

Jika Anda menginginkan informasi lebih lanjut mengenai argumen program, input,
keluaran, atau cara kerjanya secara umum, cobalah program `man`. Ini
mengambil sebagai argumen nama program, dan menunjukkan kepada Anda _manual
halaman _manual_. Tekan `q` untuk keluar.

```console
missing:~$ man ls
```

## Menghubungkan program

Di dalam shell, program memiliki dua "aliran" (_stream_) utama yang terkait dengannya:
aliran masukan (_input_) dan aliran keluarannya (_output_). Ketika program mencoba untuk
membaca input, ia membaca dari input stream, dan ketika ia mencetak
sesuatu, ia mencetak ke output stream. Biasanya, input program
masukan dan keluaran adalah terminal Anda. Artinya, keyboard Anda sebagai input dan
layar Anda sebagai output. Namun, kita juga dapat mengatur ulang stream tersebut!

Bentuk pengalihan yang paling sederhana adalah `< file` dan `> file`. Ini memungkinkan Anda
mengalihkan aliran input dan output dari sebuah program ke sebuah file:

```console
missing:~$ echo hello > hello.txt
missing:~$ cat hello.txt
hello
missing:~$ cat < hello.txt
hello
missing:~$ cat < hello.txt > hello2.txt
missing:~$ cat hello2.txt
hello
```

Didemonstrasikan pada contoh di atas, `cat` adalah sebuah program yang mengkonversi
file. Ketika diberi nama file sebagai argumen, program ini akan mencetak isi dari masing-masing
file secara berurutan ke aliran keluarannya. Tetapi ketika `cat` tidak diberikan argumen apapun
argumen apapun, ia akan mencetak isi dari input stream ke output stream (seperti
pada contoh ketiga di atas).

Anda juga dapat menggunakan `>>` untuk menambahkan ke sebuah file. Di mana jenis
pengalihan masukan/keluaran seperti ini benar-benar bersinar dalam penggunaan _pipes_. Operator `|`
memungkinkan Anda untuk "merantai" program sedemikian rupa sehingga output dari satu program adalah
masukan dari program yang lain:

```console
missing:~$ ls -l / | tail -n1
drwxr-xr-x 1 root  root  4096 Jun 20  2019 var
missing:~$ curl --head --silent google.com | grep --ignore-case content-length | cut --delimiter=' ' -f2
219
```

Kami akan membahas lebih detail tentang cara memanfaatkan _pipes_
dalam materi tentang penguraian data (_data wrangling_).

## Alat yang serbaguna dan ampuh

Pada sebagian besar sistem seperti Unix, satu pengguna adalah pengguna yang istimewa: pengguna "root". Anda mungkin
Anda mungkin telah melihatnya pada daftar file di atas. Pengguna root berada di atas (hampir)
semua batasan akses, dan dapat membuat, membaca, mengupdate, dan menghapus
file apa pun di dalam sistem. Anda biasanya tidak akan masuk ke sistem Anda sebagai
sebagai pengguna root, karena terlalu mudah untuk merusak sesuatu secara tidak sengaja.
Sebagai gantinya, Anda akan menggunakan perintah `sudo`. Sesuai dengan namanya, perintah ini
memungkinkan Anda "melakukan" sesuatu "sebagai su" (kependekan dari "super user", atau "root").
Ketika Anda mendapatkan kesalahan penolakan izin, biasanya karena Anda perlu
melakukan sesuatu sebagai root. Namun, pastikan Anda memeriksa ulang terlebih dahulu bahwa Anda
benar-benar ingin melakukannya dengan cara itu!

Satu hal yang harus Anda lakukan untuk menjadi root adalah menulis ke file `sysfs`
yang terpasang di bawah `/sys`. `sysfs` mengekspos sejumlah parameter kernel sebagai
file, sehingga Anda dapat dengan mudah mengkonfigurasi ulang kernel dengan cepat tanpa
alat khusus. **Perhatikan bahwa sysfs tidak ada pada Windows atau macOS.**.

Misalnya, kecerahan layar laptop Anda diekspos melalui file
yang disebut `brightness` di bawah

```
/sys/class/backlight
```

Dengan menulis nilai ke dalam file tersebut, kita dapat mengubah kecerahan layar.
Naluri pertama Anda mungkin akan melakukan sesuatu seperti:

```console
$ sudo find -L /sys/class/backlight -maxdepth 2 -name '*brightness*'
/sys/class/backlight/thinkpad_screen/brightness
$ cd /sys/class/backlight/thinkpad_screen
$ sudo echo 3 > brightness
An error occurred while redirecting file 'brightness'
open: Permission denied
```

Kesalahan ini mungkin mengejutkan. Bagaimanapun, kita menjalankan perintah dengan
`sudo`! Ini adalah hal yang penting untuk diketahui tentang shell. Operasi-operasi
seperti `|`, `>`, dan `<` dilakukan oleh shell, bukan oleh
individual, bukan oleh program. `echo` dan kawan-kawan tidak "tahu" tentang `|`. Mereka hanya membaca dari
input mereka dan menulis ke output mereka, apapun itu. Dalam kasus
di atas, _shell_ (yang diotentikasi sama seperti pengguna Anda) mencoba untuk
membuka file kecerahan untuk ditulis, sebelum mengaturnya sebagai keluaran `sudo
echo`, tetapi dicegah untuk melakukannya karena shell tidak
tidak berjalan sebagai root. Dengan menggunakan pengetahuan ini, kita dapat mengatasi hal ini:

```console
$ echo 3 | sudo tee brightness
```

Karena program `tee` adalah program yang membuka file `/sys` untuk penulisan,
dan _it_ berjalan sebagai `root`, maka semua perijinan akan berjalan dengan baik. Anda dapat
mengendalikan segala macam hal yang menyenangkan dan berguna melalui `/sys`, seperti
status dari berbagai LED sistem (jalur Anda mungkin berbeda):

```console
$ echo 1 | sudo tee /sys/class/leds/input6::scrolllock/brightness
```

# Langkah selanjutnya

Pada titik ini, Anda sudah cukup mengetahui cara menggunakan shell untuk menyelesaikan
tugas-tugas dasar. Anda seharusnya dapat menavigasi untuk menemukan file yang
yang diinginkan dan menggunakan fungsionalitas dasar dari sebagian besar program. Pada kuliah berikutnya
berikutnya, kita akan berbicara tentang bagaimana melakukan dan mengotomatisasi
tugas-tugas menggunakan shell dan banyak program baris perintah yang praktis di luar sana.
di luar sana.

# Latihan

Semua kelas dalam kursus ini disertai dengan serangkaian latihan. Beberapa memberikan
Anda tugas tertentu untuk dilakukan, sementara yang lain bersifat terbuka, seperti "coba gunakan program X dan Y".
Kami sangat menyarankan Anda untuk mencobanya.

Kami tidak menulis solusi untuk latihan-latihan berikut. Jika Anda mengalami kebuntuan pada sesuatu
tertentu, jangan ragu untuk mengirimkan email kepada kami yang menjelaskan apa yang telah Anda coba
sejauh ini, dan kami akan mencoba membantu Anda.

 1. Untuk kursus ini, Anda harus menggunakan shell Unix seperti Bash atau ZSH. Jika Anda
    Anda menggunakan Linux atau macOS, Anda tidak perlu melakukan sesuatu yang khusus. Jika Anda menggunakan
    Windows, Anda harus memastikan bahwa Anda tidak menjalankan cmd.exe atau PowerShell;
    Anda bisa menggunakan [Subsistem Windows untuk
    Linux] (https://docs.microsoft.com/en-us/windows/wsl/) atau virtual Linux untuk menggunakan
    virtual Linux untuk menggunakan alat bantu baris perintah gaya Unix. Untuk memastikan bahwa Anda menjalankan
    menjalankan shell yang sesuai, Anda dapat mencoba perintah `echo $SHELL`. Jika muncul perintah
    seperti `/bin/bash` atau `/usr/bin/zsh`, itu berarti Anda menjalankan program
    program yang benar.
 1. Buat sebuah direktori baru bernama `missing` di bawah `/tmp`.
 1. Cari program `touch`. Program `man` adalah teman Anda.
 1. Gunakan `touch` untuk membuat sebuah file baru bernama `semester` pada `missing`.
 1. Tuliskan berikut ini ke dalam file tersebut, satu baris setiap kali:
    ```
    #!/bin/sh
    curl --head --silent https://missing.csail.mit.edu
    ```
    Baris pertama mungkin sulit untuk dijalankan. Akan sangat membantu jika Anda mengetahui bahwa
    `#` memulai sebuah komentar di Bash, dan `!` memiliki arti khusus bahkan di dalam
    string dengan tanda kutip ganda (`"`). Bash memperlakukan string dengan tanda kutip tunggal (`'`)
    secara berbeda: mereka akan melakukan trik dalam kasus ini. Lihat Bash
    [mengutip](https://www.gnu.org/software/bash/manual/html_node/Quoting.html)
    untuk informasi lebih lanjut.
 1. Cobalah untuk mengeksekusi file tersebut, yaitu dengan mengetikkan path ke skrip (`./semester`)
    ke dalam shell Anda dan tekan enter. Pahami mengapa ia tidak bekerja dengan
    dengan melihat output dari `ls` (petunjuk: lihatlah bit-bit permission dari
    dari file tersebut).
 1. Jalankan perintah dengan secara eksplisit memulai interpreter `sh`, dan berikan
    file `semester` sebagai argumen pertama, yaitu `sh semester`. Mengapa
    ini berhasil, sementara `./semester` tidak?
 1. Carilah program `chmod` (misalnya gunakan `man chmod`).
 1. Gunakan `chmod` untuk memungkinkan untuk menjalankan perintah `./semester` daripada
    harus mengetikkan `sh semester`. Bagaimana shell Anda mengetahui bahwa file tersebut adalah
    seharusnya diinterpretasikan dengan menggunakan `sh`? Lihatlah halaman ini pada laman
    [shebang](https://en.wikipedia.org/wiki/Shebang_(Unix)) untuk informasi lebih lanjut.
    informasi lebih lanjut.
 1. Gunakan `|` dan `>` untuk menulis keluaran tanggal "terakhir dimodifikasi" oleh
    semester` ke dalam sebuah file bernama `last-modified.txt` di direktori home Anda.
    direktori home Anda.
 1. Tulis perintah yang membacakan tingkat daya baterai laptop atau suhu
    suhu CPU mesin desktop Anda dari `/sys`. Catatan: jika Anda adalah pengguna macOS
    Anda adalah pengguna macOS, OS Anda tidak memiliki sysfs, jadi Anda dapat melewati latihan ini.