---
title: Menjadi jagoan GIT part 2 - Iqball Mohammad Abdul Ghoni
date: 2018-02-24 20:00:12
tags: kulgram
---

# Menjadi jagoan GIT part 2


Hallo sobat semua berikut ini adalah rekapan Kulgram Cirebon Dev pada hari sabtu tanggal 24 Februari 2018 melanjutkan materi kulgram pekan kemarin yakni tentang “Menjadi Jagoan GIT part 2” oleh Iqbal Mohammad Abdul Ghoni
Materi masih bisa di pelajari di https://gist.github.com/Arsfiqball/a3e602951960274705976c3c2d2bf462 
sedikit tips aja, biasain pake
git --help
kalo pengen baca lebih detail command git nya :wink:
atau di git-scm.com lebih lengkap lagi :)

biasanya setiap commandline interface (cli) punya opsi help atau --help untuk melihat cara penggunaannya :)
di linux sendiri juga banyak yang kadang menggunakan man page, misal:
man git

:) :)
oh iya buat yang udah paham git, apalagi udah jago tolong bantu yang belum bisa yah :sweat_smile:
yang masih belajar, kalo ada yang mau ditanyakan, tanyakan :)
 
oke :)
jadi buat mengingat kembali sebelum melanjutkan, jadi di part-part sebelumnya kita membuat branch bernama licensing yang berisi sebuah commit. pada part kelanjutan kali ini kita akan mencoba melakukan merge dengan branch master :)
untuk sekedar mengecek, lakukan
git status
untuk melihat sekarang yang dipakai branch mana? pastikan branch master sesuai dengan kelanjutan episode kemarin.
kalau bukan master (misalkan licensing) lakukan
git checkout master
seperti pada part #24.
 
yaps :)
oke jadi sekarang kelanjutannya yaitu part #26 melakuan
git diff master licensing
untuk melihat perbedaan apa saja antara master dan licensing. fitur ini sangat membantu untuk mereview sebelum kita melakukan merge. jika sudah terbiasa dengan platform github, pasti tau dengan fitur review pada pull request kan? :)
oke apakah ada masalah sebelum kita lanjut? :)
 



