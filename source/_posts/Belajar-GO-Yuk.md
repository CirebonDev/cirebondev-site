---
title: Belajar GO Yuk - Rienaldi Muhammad
date: 2018-03-10 20:00:00
tags: kulgram
---

Belajar GO Yuk!
Berikut ini adalah rekapan KULGRAM#6 pada tanggal 10 Maret 2018 oleh Muhammad Rienaldi Full Stack Developer at CommunicBagency
assalamualaikum warahmatullahi wabarakatuh
selamat malam semua
sebelum masuk ke kulgram kali ini, perkenankan saya memperkenalkan diri dulu
saya Muhammad Rienaldi, bisa panggil Aldi atau Rei bebas :D saya kerja di salah satu agency di Jakarta Timur sebagai Full-Stack Developer
selain bekerja di Agency saat ini juga sedang mencoba mendirikan sebuah location-based laundry service startup bersama beberapa teman namanya Marlo, saat ini sedang tahap ideation dan penyusunan MVP minta do'anya supaya cepet rilis :D
sebenernya saya blm begitu lama juga pake Go baru sekitar 3-4 bulan terakhir coding Go, karena di agency saya sendiri banyaknya legacy project yg menggunakan PHP. jadi kalo ada salah2 mohon di maafkan ya :D
oke sblm masuk ke materi utama, mau tau dulu dong berapa banyak yg udah pernah pake Go?
sebelum ke fun partnya yaitu coding menggunakan Go, langkah paling pertama adalah kita harus install Go nya dulu di alat tempur kita. Buat temen - temen yang Go nya udah terinstall boleh simak dulu aja ya
untuk menginstall Go teman - teman boleh buka https://golang.org/dl/
lalu download sesuai dengan OS yang dipakai masing - masing
kalau yang pake Mac mungkin bisa langsung menggunakan perintah brew ya
setelah installasi tadi berhasil selanjutnya adalah mensetup GOPATH kedalam sistem variabel kita
buat yang pake Linux:
$ echo "export PATH=$PATH:/usr/local/go/bin" >> ~/.bashrc
$ source ~/.bashrc
buat yang pake MacOS:
$ echo "export PATH=$PATH:/usr/local/go/bin" >> ~/.bash_profile
$ source ~/.bash_profile
Windows:
Explorer -> Klik kanan "My Computer" / "This PC" -> Properties -> "Advanced System Settings" -> "Environment Variables"
lalu pada "System Variables" klik "New"
lalu tambahkan:
"Variable name" = GOPATH
"Variable value" = C:\GolangProject (boleh diganti sesuai keinginan)
jika instalasi nya berhasil ketika kita ketikan "go" di terminal / command line kita maka akan muncul seperti berikut:

oke kalo sudah berhasil. selanjutnya adalah tempat untuk ngoding Go nya ya
kalo saya sendiri pake Visual Studio Code (https://code.visualstudio.com/).

sebenarnya ada Goland dari JetBrains tapi itu berbayar :D
tapi kalo teman - teman biasa pake Sublime Text atau Notepad++ juga gapapa yang penting code kita ada highlight warna nya aja biar gk pusing :joy::joy:
Ritual wajib pertama pas kita belajar pemrograman adalah belajar bikin "Hello World". Bener gk?
selain bikin Hello World saya juga akan bahas struktur code dari si Golang ini sendiri
kuy mari kita mulai bikin Hello World
silahkan temen - temen bisa ketikan code ini di text editor masing - masing :

oh iya saya lupa biasa nya sblm kita mulai coding kita nentuin dulu folder codenya dimana :D
tadi kan kita udah setup GOPATH
sebaiknya semua project kita disimpan di GOPATH tersebut
untuk project "Hello World" ini silahkan buat folder baru misal namanya "belajar_go" di folder GOPATHNya
lalu buat file baru namanya "main.go" yang isinya code tadi ya
nah sekarang gimana sih cara menjalankan code kita tadi?
caranya adalah buka terminal masing - masing
silahkan change directory ke project foldernya teman - teman
kalau sudah ketikan perintah go run (nama file go)
karena tadi namanya adalah main.go maka
go run main.go
jika berhasil maka hasilnya akan seperti ini

yuk kita bahas struktur codenya
pertama apa sih "package main" itu
package main artinya kita mendeklarasikan package kita sebagai main (utama)
package sendiri pengertian nya adalah "collection of common source code file" atau kalau di bahasa indonesia kira - kira sekumpulan file source code
package dalam Go sendiri terbagi menjadi 2 tipe
yaitu Executeable dan Reuseable
Executeable package adalah package yang bisa di jalankan (run)
Reuseable package adalah package yang berfungsi sebagai library / dependencies
gimana cara membedakan package itu Executeable atau Reuseable?
Executeable dalam Golang pasti dan ekslusif hanya untuk package yang bernama "main", selain package yang bernama "main" Go akan menganggap package itu sebagai reuseable package
kalo bingung yuk kita cobain
source code tadi kita rubah nama packagenya jadi "coba"

setelah itu kita go run main.go
maka hasilnya adalah "cannot run non-main package"

selanjutnya kita bahas "import"
dalam code yang tadi kita tulis, kita menuliskan "import "fmt""
apa sih artinya
import ya sesuai dengan namanya yaitu mengimport (memasukan) fungsi dari package lain ke code kita
fmt sendiri adalah package bawaan dari Go, mungkin kependekan dari ForMaT
untuk list package bawaan dari Go teman - teman bisa lihat di : https://golang.org/pkg/
import sendiri bisa dilakukan dengan banyak package, contoh:

lalu selanjutnya kita menuliskan "func main()"
apasih func
func sendiri dalam Go adalah cara untuk mendeklarasikan function / method
sama seperti function2 dalam PHP, Java, Python dll
function di Go juga bisa menggunakan parameter


function yang akan di running ketika kite men-run "go run" adalah function main
sama seperti java yang di run juga kan function main nya
oke lanjut kita bahas gimana cara mendeklarasikan variabel di Go
ada 3 cara untuk membuat variabel di go

cara pertama adalah kita langsung mengetikan var (nama variabel) = (value)
Go akan otomatis men set tipe datanya sama seperti php
cara kedua adalah dengan mendeklarasikan tipe datanya
var (nama variabel) (tipe data) = (value)
cara ketiga langsung straight forward ya
(nama variabel) := (values)
dia kayak shorthand cara pertama kalo kataku
setelah tadi kita bahas variabel, sekarang kita bahas sodaranya yaitu konstanta
cara mendeklarasikan konstanta sendiri ada 2 di Golang

cara pertama yaitu dengan langsung:
const (nama konstanta) = (value)
kalo cara kedua kita deklarasiin dulu tipe datanya
const (nama konstanta) (tipe data) = (value)
selanjutnya mari kita mulai masuk ke conditional (if, switch)
buat temen - temen yang udah paham bgt coding java atau PHP atau C mungkin gk akan kaget sama gimana cara membuat kondisional if dan switch di Go

sama kan dengan PHP atau Java
mirip lah ya
nah kalo switch nya kayak gini

bedanya dia engga pake break;
untuk perulangan di Go setauku cuman ada For aja
karena di tour of Gonya juga begitu
https://tour.golang.org/flowcontrol/3
code For loop di Golang adalah seperti ini:

selanjutnya mari kita bahas mengenai Arrays, Slice dan Map
untuk pendeklarasian array di Go sendiri sama seperti di bahasa bahasa pemrograman lain nya menggunakan variabel lalu di ikuti dengan []
contoh:


atau

untuk mengabil salah satu index dari array juga sama menggunakan (nama variable)[(nomor index)]

untuk menset index array juga sama menggunakan: (nama variable)[(nomor index)] = (value baru)

untuk menghitung jumlah data yang terdapat dalam 1 array kita bisa menggunakan function len()
cara penggunaan nya len([nama array yang akan dihitung])
contoh

hebatnya kita bisa langsung print semua array tapi harus loop

hasilnya

udah pada pusing belum? :joy::joy:
selanjutnya kita bahas tentang slice
slice adalah tipe data key yang ada di Go
biasanya nanti banyak dipakai untuk membuat Model
untuk membuat slice kita bisa menggunakan function make()
misal:
contoh membuat slice:

cara untuk menset value slice adalah:
(nama slice)[(index value)] = (value)
contoh:

index valuenya tidak boleh lebih dari yang sudah kita set pertama ya
kalo lebih akan menghasilkan error


untuk mengambil value berdasarkan index juga sama seperti array
contoh:

fungsi len untuk menghitung banyak data juga bisa di terapkan pada slice


Oke saya rasa untuk kulgram tentang basic Go nya cukup sampai disini dulu. karena waktunya udah 1 setengah jam juga
kalo temen - temen mau belajar bisa kunjugi link - link berikut:
1) https://tour.golang.org/welcome/1
2) https://gobyexample.com/
 

# QA
Asrini
Tour go itu apa mas?
JAWAB
Tour of Go itu situs untuk bejalar Go dari Gonya langsung mba as
Asrini
Boleh ga mas kalau naro projek go nya diluar folder path yg tadi udah di setting?
JAWAB
tidak di sarankan mba as, tapi kalo boleh atau engga sih boleh aja

kenapa tidak sarankan?
karena nanti ketika kita menggunakan dependencies lain menggunakan perintah "go get", dia akan clone nya ke GOPATH yang tadi kita setting jadi biar file management nya rapih
CMIIW ya

Pril 
Mas saya kan baru blajar Linux pake ubuntu nah ini folder path nya itu ada di /usr/local/go/bin tah? Tp kena permission denied
Pas ngesave
Jadi bingung sendiri
 
JAWAB
engga harus mba, sesuai extractnya saja dimana. bisa di /home/username/go/bin juga boleh
oh iya mba kalo di /usr/local dia harus root atau sudo tadi saya cmn contoh aja disitu :D
 
kalau mau ganti path nya edit di bash rc nya mba
https://stackoverflow.com/questions/20384075/what-is-bashrc-how-to-find-the-startup-file-putty
biasanya ada di /home/username
jadi bisa langsung nano /home/username/.env
.bashrc sorry


Fawaz Rifqi
Diluar teknis ya pak @saberienaldi pertanyaannya ya, kenapa tertarik dengan "Go" nih kalo boleh tau?
JAWAB
banyak faktor ya. salah satunya hype yg sedang terjadi komunitas itu sendiri. Jadi waktu itu saya lagi nyari bahasa apa yang kira2 harus dipelajari selain PHP pilihan nya jatuh ke Java, Node JS, Golang, Python, Ruby. tapi setelah dipersempit lagi akhinrya cmn jatuh ke Node JS atau Golang cuman saya kurang begitu sreg sama codenya javascript jadi pilihan nya jatuh ke Golang karena lebih C-like codenya kayak java or PHP

keuda Go sendiri ini bisa dibilang language sangat oke buat multiprocessing dan banyak fitur2 keren lain nya


AyaT
mas @saberienaldi apakah di golang sudah ada package managementnya mas?, sofar masih langsung dari github, menggunakan `go get github.com/xxxxxx` , nah dari situ saya mengalami kendala ketika sudah banyak menggunakan library, karena harus go get satu satu, adakah cara best practice seperti di php/node kan ada composer.json/package.json, ketika ready to production tinggal composer install / npm install / yarn install
JAWAB
dependencies manager di go sendiri sudah ada namanya dep (https://github.com/golang/dep) mungkin boleh langsung di coba mas Ayat :D

Ayat
ohh mas @saberienaldi ternyata selain dep ada lagi glide namanya https://glide.sh/ :grin:, mas pake yg mana?
JAWAB
kalo saya pake dep mas, soalnya official dari Go nya :D tapi itu personal preferences



oke sekian dulu telegram dari saya
sampai juga di kulgram kulgram lain nya ya :D


