---
title: Menjadi jagoan GIT part 1 - Iqball Mohammad Abdul Ghoni
date: 2018-02-17 20:00:00
tags: kulgram
---

# Menjadi jagoan GIT part 1


Hallo sobat semua berikut ini adalah rekapan Kulgram Cirebon Dev pada tanggal 17 Februari 2018 yang di sampaikan oleh Iqbal Mohammad Abdul Ghoni

Perkenalkan nama saya Iqbal Mohammad Abdul Ghoni. Saya mahasiswa teknik elektro di Universitas Sultan Ageng Tirtayasa, buat yang belum tau, kampusnya ada di Cilegon Banten :)
Pada kesempatan kali ini saya akan membahas tentang Git :)
temantemans silahkan baca ini dulu :)
https://gist.github.com/Arsfiqball/a3e602951960274705976c3c2d2bf462
keliatan lambat, repetitive, dan membosankan di section#1 karena emang objektifnya agar kita membiasakan diri nyaman dan terbiasa.
bisa dianggap berhasil kalo sudah menganggap Git adalah hal biasa yang ga kerenkeren amat 
di section#2 bahasannya mulai teknis, tapi belum masuk kolaborasi :)
nanti di bawahnya sectionsection berikutnya bisa ditambahin :)
Apa itu Git? Kenapa harus pakai Git?
Pertanyaanpertanyaan seperti itu bisa Anda cari jawabannya sendiri kan? 
Oke tapi sekarang saya akan ceritakan awal mulanya saya sering menggunakan Git :)
Sebelumnya, saya sudah menggunakan Git sebatas basic dan hanya karena ikutikutan saja, dan semua itu berubah ketika di semester 1 tahun 2016 kemarin saya mengikuti event BesutKode yang saat itu diadakan untuk SMA dan Universitas. Dimana event tersebut diadakan untuk mempersiapkan codercoder muda yang berbakat bukan hanya dalam hal skill coding tapi juga bagaimana menjaga kualitas kode dan beradaptasi pada lingkungan yang kolaboratif. :)
Salah satu tujuan utama event tersebut adalah mempersiapkan siswa SMA untuk menghadapi Google Code-in. dan Mahasiswa untuk Google Summer of Code. Salah satu tools paling vital yang digunakan pada event tersebut adalah Git. karena hampir seluruh organisasi yang tergabung adalah organisasi OpenSource.
 
Jadi, bagi kalian siswa SMA atau mahasiswa, belajar Git akan sangat berguna untuk kalian, banyak peluang untuk bergaul di dalam komunitas opensource dan lebih banyak ilmu yang akan kalian dapat.
 
buat spoiler aja sih, Google Code-in diadakan sekitar awal semester ganjil di indonesia. Sementara google summer of code sebentar lagi fase submit proposal :)
 
Google Code-in levelnya 10x lebih mudah daripada Google summer of code tapi 2x lebih intense :)
oke backto story :)
jadi pada event besutkode tersebut, saya menggunakan Git terusmenerus selama sebulan setiap hari. dan setiap 3 hari harus ada pull request.
jadi buat kalian yang mengira belajar Git itu teoritis dan bisa cepat dikuasai. kalian salah.
karena penggunaan Git lebih ke kebiasaan :)
oke segitu cukup yah intronya kenapa saya sekarang jadi lancar pakai Git :)
 
kalian akan menemukan manfaatnya saat menggunakannya :)
Oke sekarang masuk ke sesi practicenya :)
eh sebelumnya apakah ada yang ditanyakan?
 
baca ini dulu, saya udah revisi ini setengah jam yang lalu :)
https://gist.github.com/Arsfiqball/a3e602951960274705976c3c2d2bf462
santai saja dalam kulgram ini ga usah buru buru sampai part #60 :)
kalian lihat di situ saya bilang persiapkan ide reponya, apakah udah pada siap? :)
 
ga harus coding aplikasi, bisa bikin css styles tah atau bikin open data pake json tentang reporepo keren di cirebon misalkan. bebas, berimajinasi ajah dulu. yang penting sekarang ada namanya :)
 
oh iya harus ga pake library pihak ketiga sama sekali :)
 
kayak laravel, vue tuh gaboleh 
sebenernya kata repository sendiri bisa berarti macammacam. tapi dalam Git, itu sebutan untuk satu project Git kita. sederhananya gitu :)
 
oke lah semuanya silahkan buka terminalnya (atau Git Bash buat di Windows)
 
ada yang pake windows? :)
Kalo di windows bisa masuk dir project dulu kemudian klik kanan git bash
 
masuk ke part 1, membuat directory. semuanya bisa kan?
directory = folder
kalau membuat directory usahakan selalu menggunakan mkdir misal:
mkdir repo-gw
 
kalau mau masuk ke repo nya pakai cd repo-gw 
yaps di part #2 masuk ke repo pakai cd <nama-folder> seperti yang @IhwanID bilang :)
 
gimana? aman semua paham sampai part 2? apakah ada yang kesulitan? :)
masuk ke part #3
lakukan:

git init

di repo kalian :)
jadi saat kita lakukan git init ini yang terjadi adalah direktory tersembunyi .git akan dibuat. dimana kita masih bisa mengaksesnya via commandline cd
kalem yah, saya jelasin satu persatu partnya 
 
oh iya jadi git init tuh membuat direktori .git tersembunyi. konfigurasi dan informasi tentang git kita akan di simpan di sana :) jadi kalau kalian copy folder tersebut, repo kalian tidak tercopy juga sebenarnya.
.git juga menyimpan informasi tentang commit kita
.git juga menyimpan staged files dan stash yang nantinya bisa dicommit
jadi kalo dibilang repo itu apa sih sebenarnya? yah yang ada di directory .git tersebut :)
 
oke lanjut ke part #4
git status
kalian lihat bahwa git akan mengatakan kalian ada di branch master, branch ini secara default dibuat oleh git dan biasanya adalah branch utama di setiap project.
branch master ini sangat spesial. tidak disarankan untuk melakukan commit langsung ke branch ini nantinya. apalagi ketika repo kalian sudah mulai dikerjakan lebih dari satu orang :)
namun, ketika baru memulai ini tidak masalah :)
gimana ada yang pernah pake git dan selalu commit ke master terus?
hayo ngaku 
 
oke saya lanjut ya :)
di part #5 #6 #7 #8 adalah tentang konfigurasi git
pada tutorial seperti https://www.petanikode.com/git-install/ biasanya terdapat opsi --global dimana ini digunakan untuk mensetting pengaturan global pada git.
jadi pada git itu ada config global dan config local. apa bila nama anda tidak pernah ganti, maka anda bisa lakukan part #5 dengan cara:

git config --global user.name "Tulis nama asli anda"
begitupun dengan part #6, apabila email kalian tidak pernah ganti untuk repo manapun. kalian bisa lakukan:

git config --global user.email "user@email.com"

misalkan kayak gitu :)
oke pada part #6 ini masih aman kan? sekarang part #7
 
ini adalah konfigurasi untuk editor untuk digunakan oleh git nantinya, misalkan untuk mengedit commit. secara default Git menggunakan "vi" untuk editornya.
kita skip part ini juga tidak apaapa sebenarnya untuk section#1 :)
pada part #7 yang saya tulis itu ada subl -w, adalah perintah commandline untuk membuka sublimetext dengan opsi -w (wait/tungguin). itu konfigurasi yang saya gunakan saat ini. sebenarnya subl saja sudah cukup. :)
> kalau visual studio code gimana?
searching aja nama di commandlinenya apa :)
code aja 
karena di windows tuh, aplikasi tidak secara umum bisa dijalankan melalui commandline, tidak seperti linux dan mac
hmm... kalau bisa, silahkan configure git nya biar bisa open 
fyi juga, kalau kalian melakukan git commit nantinya tanpa passing -m maka editor itu yang dipilih buat nulis commitnya.
^ contoh kasusnya
pada saat rebasing yang paling membantu tuh
kalo ngobrol di coala terus ada yang gabisa rebasing tuh bikin kesel, biasanya sih orang india. pas dijelasin, basicnya gabisa juga :joy:
ngasih tau doang :v
 
part #8 juga lewat yah, lanjut :)
sudah saya duga ini membosankan :(
pada maunya cepet :(
 
part #9 buat file bernama readme.md di repo kalian :)
satu repo, 
satu akun paling saya pernah bisanya :joy:
part #9 dan #10 silahkan bikin file readme.md terus isi dengan nama repo kalian :)

Readme.md itu ekstensi buat file apa ya?
 
 part #9 buat file bernama readme.md di repo kalian :)
Bkin file nya manual ta mas?
file markdown, buat dokumen biasanya. tapi lebih sederhana :)
 
part #11
git status
buat melihat status repo saat ini :)
ada yang merah? :)
di situ tulisannya untracked files.
mari kita tracking file tersebut dengan melakukan staging
 
di part #12
git add readme.md
 
lalu part #13
git status
ada yang hijau? :)
 
yap ke part #14 lakukan
git commit readme.md -m "Create README"
setelah part #14 lalu part #15 cek status:

git status
sudah tidak ada yang hijau merah lagi kan? :)
 
sekarang part #16

git log
buat nampilin story :)
udah lihat story nya pakai git log? :)
oke kita coba branching sekarang :)
 
part #17

git checkout -b licensing
jadi di part itu kita akan membuat branch (cabang) dengan nama "licensing" :)
udah? :)
terus buat file bernama "LICENSE" di repo kalian
#udah pada bisa bikin file LICENSE? (tanpa ekstensi)
biar gampang, tentukan dulu projectnya termasuk ke dalam Software atau Data
kalau Software, pilih MIT license saja copy text nya dari:
https://choosealicense.com/licenses/mit/
kalau Data, pilih CC BY 4.0 license aja :)
copy textnya dari:
https://creativecommons.org/licenses/by/4.0/legalcode.txt
lisensi ini penting untuk melindungi kode kalian secara hukum, meskipun opensource, tetap harus terlindungi :)
kebanyakan software menggunakan GPL (atau keluarganya) dan MIT untuk lisensinya
sementara Open Data biasanya menggunakan CreativeCommons (CC) untuk lisensinya :)
udah semua? :)
 
> eh mas, misal ada yg ngelanggar lisensi, kita nuntutnya gimana?
itu aturan internasional nya, tergantung indonesianya juga sih kalo soal pengamanan. sebenarnya setiap karya cipta kan punya hak cipta. yang menjalankan hukum mah pada akhirnya negara masingmasing.
dan tau sendiri indonesia tuh pembajakannya kayak gimana :joy:
 
oke part #19 cek status lagi: git status
pasti ada yang unstaged kan? :)
part #19 #20 #21 ngerti lah ya :)
 
part #22 itu titiktitiknya diganti nama lisensi kita MIT atau CC BY 4.0 :)
abis itu silahkan mainmain sendiri, udah tau kan fungsi git status untuk apa? :)
git log dulu juga silahkan :)
 
gimana part #23 udah? :)
lihat teks terakhirnya apa? :)
jadi log/catatan/story yang di simpan di simpan di situ hanya tentang branch licensing saja :)
coba git status lagi, cek apa yang git katakan? kalau belum checkout master, harusnya masih di branch licensing :)
udah gada hijau merahnya? tah udah pada checkout master? :)
gimana log terakhirnya? udah bertuliskan Add... license gitu? :)
 
oke bisa lanjut ke part #24
git checkout master
lalu coba part #25
git status
harusnya sekarang kita ada di branch master :)
sekian dulu untuk sementara kulgram tentang Git hari ini :)
saya ucapkan terimakasih untuk yang telah berpartisipasi :)
wassalamualaikum wr.wb.
buat yang mau tanyatanya bisa langung chat saya juga tidak masalah, tapi mungkin ga langsung dibales :)
oke, tracking progres kulgram saya bisa dilihat di https://gist.github.com/Arsfiqball/a3e602951960274705976c3c2d2bf462
:)
 


