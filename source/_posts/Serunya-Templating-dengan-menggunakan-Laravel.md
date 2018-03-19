---
title: 'Serunya Templating dengan menggunakan Laravel - Gita Citra Puspita'
date: 2018-02-10 20:12:38
tags: kulgram
---


Berikut ini adalah rekapan kulgram Cirebon Dev pada hari sabtu malam minggu 10 Februari 2018 oleh Kak Gita Citra Puspita 

Assalamu'alaikum teman-teman.
Perkenalkan nama saya adalah Gita Citra Puspita.
Saya adalah Web Developer dan Trainer di Kolla.
Saya juga merupakan Sekertaris di Komunitas FemaleGeek PHP Indonesia.
Tools yang diperlukan: 
For Linux/Mac:
- xampp
- php cli 7 (dependency-nya)
- composer

For Windows:
- xampp
- composer

Tutorial Dasar Laravel yang harus dibaca:
- http://bit.ly/gitasharepengenalanlaravel1
- http://bit.ly/gitasharepengenalanlaravel2
- http://bit.ly/gitashareroutinglaravel

Aku tidak akan menjelaskan dari proses instalasi atau pengenalan tentang laravel. Aku akan langsung masuk ke pengenalan tentang blade dan praktiknya.
Jadi teman-teman yang baru menggunakan Laravel bisa baca-baca dulu materi yang aku siapkan disini.

Pada malam ini saya akan mengajak teman-teman untuk belajar templating/layouting di Laravel dengan menggunakan blade.
Oke template apa yang akan kita oprek?
Okay, sebelum kita masuk ke templating aku mau kenalkan kalian terlebih dahulu dengan Blade.
Apa itu blade?
Blade adalah salah satu fitur dalam laravel yang digunakan untuk menampilkan output pada view. 

Fitur blade ini bisa dibilang sangat canggih, karena kita dapat membuat coding tanpa perlu tag PHP (<?php ?>). 

Selain menampilkan output, blade juga digunakan untuk membuat layout website.
Nah kita akan coba lihat perbedaan sebuah view pada laravel yang menggunakan blade dan tidak menggunakan blade.
Okay, teman - teman silahkan buka laptop masing-masing dan kita akan mulai membuat sebuah project laravel.
Berikut ini aku akan jelaskan langkah-langkah dan perintah untuk membuat project laravel:

1. Buka terminal / command prompt.

2. Lalu ketik perintah
`cd Desktop`

3. Setelah itu kita buat project Laravel baru. Kamu akan membuat project Laravel pada Desktop. Pastikan local computer kamu terkoneksi dengan jaringan internet ya.

4. Perintah untuk membuat project baru di Laravel : 
`composer create-project — prefer-dist laravel/laravel serunya-templating-dengan-menggunakan-laravel`

5. Selanjutnya, Composer akan secara otomatis melakukan download dan instalasi package Laravel. Lumayan lama, sekitar 10 menit. Jadi sambil menunggu kamu proses download kamu bisa bikin kopi, susu, atau teh dulu.

6. Oke, kalau berhasil seharusnya kamu menemukan sebuah folder dengan nama serunya-templating-dengan-menggunakan-laravel pada Desktop kamu.

Oh iya, pada kulgram ini aku masih menggunakan Laravel 5.5, aku belum cari tahu sih perbedaannya apa dengan Laravel 5.6. Tapi semoga tidak mempengaruhi yap..
Kalau ada kendala/error. Jangan sungkan tanya ya..
coba dilihat versi laravelnya mba. Ada di dalam file composer.json
Oh, oke untuk laravel 5.2 route masih dalam bentuk file route.php
apa kamu menemukan file itu?
app/Http/routes.php
Ada di situ mba
coba kamu buka folder app
Lalu buka folder Http
Oke, setelah kalian memiliki project laravel. Buka folder dengan nama resource. Kalian akan melihat tampilan seperti pada gambar di bawah ini.


Sekarang coba teman-teman buat 2 buah file di dalam folder views. Yang satu nama filenya contoh1.php dan yang satu lagi dengan nama contoh2.blade.php. Seperti pada gambar di bawah ini.

Isi file contoh1.php dengan tulisan di bawah ini.
```php
Hallo, <?php echo $nama ?> ! <br\>
Selamat bergabung di website ini.
```

Setelah itu jangan lupa simpan ya hasil perubahan yang ada pada file contoh1.php.
Isi file contoh2.blade.php dengan tulisan di bawah ini.

```php
Hallo, {{ $nama }}! <br\>
Selamat bergabung di website ini.
```

Setelah itu jangan lupa simpan ya hasil perubahan yang ada pada file contoh2.blade.php.
Coba kalian buat seperti itu yap...
 
Jika sudah selanjutnya kalian tambahkan 2 buah route baru.

Kalau di laravel 5.2 kamu bisa tambahkan di dalam file rotue.php

Kalau pada laravel di atas 5.3 kamu bisa tambahkan di dalam file web.php yang ada pada folder route

```php
<?php

//route untuk memanggil view contoh1.php
Route::get('/contoh1/{nama}', function ($nama) {
  return view('contoh1',['nama'=>$nama]);
});
//route untuk memanggil view contoh2.php
Route::get('/contoh2/{nama}', function ($nama) {
  return view('contoh2',['nama'=>$nama]);
});
```

`['nama'=>$nama]` sama aja seperti `compact('nama')` 
Okay setelah itu jangan lupa setiap perubahan/penambahan pada file di simpan yap..
 
Sekarang kita coba jalankan service web pada laravel di terminal dengan perintah:
php artisan serve

Selanjutnya buka browser dan akses URL seperti di bawah ini.
`http://localhost:8000/contoh1/gita`
Hasilnya akan seperti pada gambar di bawah ini.

Kemudian coba kalian akses URL seperti di bawah ini.
`http://localhost:8000/contoh2/gita`

Hasilnya akan seperti pada gambar di atas.
 
Outputnya memang sama. Namun cara menampilkan parameter `$nama` yang dikirmkan dari route yang berbeda.

Jika tidak menggunakan blade, kita masih memerlukan tag php untuk mencetak nilai parameter. 

Coba bayangkan kalau dalam halaman view ada banyak parameter yang kita ingin cetak namun di bagian yang berbeda. Mungkin akan ada banyak tag php yang bertebaran.
Nah, kalau kita menggunakan blade, kita cukup panggil nama variabel yang akan di tampilkan nilainya. Lalu di lingkupi dengan blade {% raw %} `{{}}` {% endraw %} Keunggulan blade ini. Kita bisa sisipkan di html bagian manapun. Hehehe. Lebih bersih coding kita dari tah-tag php.
Oke, selanjutnya ktia akan langsung masuk saja ke penggunaan blade sebagai layout pada laravel ya.
 
Teman-teman bisa coba download contoh template bootstrap yang saya tampilkan gambarnya.
Downloadnya di sini ya.
[https://medium.com/r/?url=https://github.com/BlackrockDigital/startbootstrap-creative/archive/gh-pages.zip](https://medium.com/r/?url=https://github.com/BlackrockDigital/startbootstrap-creative/archive/gh-pages.zip)

Okey setelah teman-teman download, jangan lupa ekstrak yap.
Berarti sekarang teman-teman memiliki 2 folder dan 1 file seperti pada gambar di bawah ini.

Okay, kita cek isi dari folder startbootstrap-creative-gh-pages.

Oke.. Sekarang kita bersiap untuk masukan template ini ke dalam project Laravel kita.
 
Berikut langkah-langkahnya ya:
1. Copy folder vendor, js, img, dan css yang ada di dalam folder startbootstrap-creative-gh-pages ke dalam folder public yang ada pada project laravel kamu

Gambar di atas adalah folder yang harus kamu copy.

Nah, folder tersebut teman-teman paste di dalam folder public laravel ya. Hasilnya akan seperti pada gambar di atas.
Okay, selanjutnya kita tinggal pindahkan file index.html ke dalam folder views yang ada di dalam folder resource

Simpan di dalam folder views seperti pada gambar di bawah ini.

Ganti nama file yang tadinya index.html menjadi index.blade.php

Oke, selanjutnya kita buka file web.php yang ada pada route, dan kita buat sebuah route yang akan memanggil template ini.

Aku memilih mengubah route '/' yang tadinya memanggil file view welcome.blade.php menjadi memanggil file view index.blade.php.
Oke selanjutnya kamu bisa coba akses URL `http://localhost:8000/`
 
Hasilnya jika sama akan seperti pada gambar di bawah ini.

Nah, kita sudah menerapkan sebuah template bootstrap pada projet laravel. Sekarang kita akan mulai layouting template ini dengan menggunakan blade.
 
Okay, sekarang coba teman-teman buka file index.blade.php yang ada di dalam folder resource/view.
 
Beuh, panjang banget ya line codenya ada 272 line code. Nah ini mau kita bagi-bagi. Agar apa. Agar lebih enak aja nanti pas mau edit atau tambah-tambah element pada tampilan.
 
Aku biasanya akan membuat beberapa folder di dalam view laraver seperti ini.

Nah biasanya aku suka pisah-pisah seperti gambar di atas
 
Di dalam folder eksternal-files biasanya aku simpan file meta, css, dan javascript yang di panggil oleh layout.
 
Okay kita buat filenya dulu ya..

Semua file dan folder ini aku buat manual ya. Tidak menggunakan perintah artisan.
 
Okay, selanjutnya, apa yang akan kita lakukan? Kita akan mulai memindahkan file css dulu yang ada pada file index.blade.php ke dalam file css.blade.php.

Ini akan kita pindahkan ke dalam file css.blade.php
Setelah itu kita simpan perubahan pada file css.blade.php
 
Kemudian kembali ke file index.blade.php
 
Kita panggil css template dengan menggunakan perintah blade
`@includeif('eksternal-files.css')` seperti pada gambar di bawah ini.

Oke aku akan jelaskan fungsi dari 
`@includeif`
 
`@includeif` ini sebenarnya sama seperti penggunakan include pada php. 

Kegunaannya untuk menyisipkan isi file php ke dalam file php lainnya.

Oh iya selain `@includeif` di blade juga memiliki perintah `@include`.

Apa perbedaan antara @includeif dengan `@include`?

Kalau file view yang diakses pada `@includeif` tidak ada, maka tidak akan terjadi error saat service web dijalankan.

Jika menggunakan `@include` dan file view yang diakses tidak ada, maka akan langsung error saat halaman di akses.
`@includeif('eksternal-files.css')`

Nah, aku akan jelaskan maksud dari eksternal-files.css.

Sama seperti memanggil path / alamat file css.blade.php. 
Kalau di blade untuk fungsi`@include` , `@includeif`, dan `@extends` akan seperti itu
Oke, kita akan lakukan hal yang sama untuk `meta.blade.css`

Selanjutnya simpan perubahan yang ada pada file `meta.blade.php`
 
Pada file index.blade.php kita panggil file meta ini dengan fungsi `@includeif`

Selanjutnya file `js.blade.php`

kita pindahkan ke dalam file `js.blade.php`

Uupps, sorry guys. Tadi nama file js-nya salah :joy:

Selanjutnya simpan perubahan yang ada pada file `js.blade.php`
Pada file index.blade.php kita panggil file js ini dengan fungsi `@includeif`

oke, sekarang kita sudah memisahkan eksternal file yang ada di dalam folder `index.blade.php` pada masing-masing bagian.
 
Next selanjutnya kita pisahkan item-item yang ada pada file `index.blade.php`
 
Coba kita lihat dahulu ya, ada item apa saya pada file `index.blade.php`

Ada 7 bagian pada file `index.blade.php`. Aku akan pisahkan 7 bagian itu dalam 7 file berbeda pada folder items. Kita beri tanda dan nama dulu ya. biar gak salah urutan susunannya. Hehehe..
 
Nah, aku tandai seperti pada gambar di bawah ini.

Oke, selanjutnya kita tinggal buat file-file tersebut di dalam folder items yang ada pada views.

Oke aku sudah buat 7 file, sekarang tinggal memindahkan isi yang ada pada file `index.blade.php` ke dalam masing-masing file tersebut. Cara memanggilnya juga sama seperti saat memanggil file `css.blade.php`.

Untuk bagian ini tidak perlu aku rinci ya. hehehe

Hasilnya nanti akan seperti ini pada file `index.blade.php`


Nah, sekarang file index.blade.php kita lebih enak dilihat ya. Hehehe
 
Hems karena contoh yang aku buat ini adalah landing page, jadi untuk layout mungkin aku hanya akan memisahkan navigation dengan konten saja.
 
Kita buat file landing-page pada folder pages ya.

nah kita pindahkan beberapa konten yang ada pada `index.blade.php` ke dalam landing-pages.blade.php
ini isi file `landing-pages.blade.php` untuk sementara
Oke selanjutnya kita buat sebuah file dengan nama `landing-pages-layouts.blade.php` di dalam folder layouts.

Oke selanjutnya kita pidahkan semua isi index.blade.php ke dalam file `landing-pages-layouts.blade.php`

Lalu kita tambahkan laber `@yield('content')` di bawah `@includeif('items.navigation')`

Oke, kita menemukan fungsi blade baru yaitu `@yield`
 
apa guna fungsi blade ini?
 
Gita Citra Pus
`@yield()` merupakan fungsi blade yang digunakan untuk mengextend suatu script html.

Jika diibaratkan sebagai suatu pewarisan, `landing-pages-layouts.blade.php` merupakan suatu parent view.

Ketika ada sebuah file view sebagai child view meng-extend parent view ini, maka bagian yang di beri label `@yield()` dapat dijabarkan script htmlnya pada child view.
 
Oke selanjutnya kita buka file landing-pages.blade.php. Ubah isinya seperti pada gambar di bawah ini ya.

Nah, `landing-pages.blade.php` adalah sebuah child view yang menerapkan parent view `landing-pages-layouts.blade.php.`
 
Ini terlihat dari fungsi blade `@extends('layouts.landing-pages-layouts')`
 
Nah, pada file landing-pages.blade.php kita menjabarkan isi dari `@yield('content')` yang ada pada parent view `landing-pages-layouts.blade.php` dengan menggunakan blade `@section('content')`.
 
Oh iya, ini aku buatnya memang hanya satu `@yield` ya pada parent-view dan satu `@section` pada child-view.
 
Kalian bisa membuat banyak `@yield `pada parent-view sesuai kebutuhan. Nanti pada child-viewnya kalian tinggal jabarkan setiap isi yang diinginkan dengan menggunakan `@section`.

Jangan lupa `@section` harus di tutup dengan @endsection
 
Nah, sekarang kita tinggal ubah isi route pada `web.php` menjadi seperti gambar di bawah ini.

Kita sudah tidak memakai file index.blade.php lagi. Jadi yang diakses langsung file landing-pages.blade.php yang ada di dalam folder pages.

Tampilannya seperti di atas.
Nah, selanjutnya aku mau kenalkan kamu sama blade yang namanya `@each`
 
`@each` ini digunakan untuk merender setiap elemen dalam array atau koleksi dimana setiap element dalam array mengimplementasikan bentuk view yang sama.
 
Ini bisa diterapkan pada bagian service

dan pada bagian portofolio

Oke, kita kerjakan bagian service dulu..

Kita lihat, ada sebuah konten yang sebenarnya tampilan viewnya sama yang berbeda hanya isinya saja.
 
Bagian yang mana?

nah, kita buat file baru namanya sub-`services.blade.php` di dalam folder items

Isi file `sub-services.blade.php` dengan script pada gambar di atas

nah selanjutnya file sub-services.blade.php di ubah isinya seperti pada gambar di bawah ini

aku salah kasih nama yang sub-service.blade.phpnya

Okay, isi file `services.blade.php` di buat seperti pada gambar di bawah ini.

Okay, aku akan jelaskan dulu ya..

pada file services.blade.php kita menggunakan 2 buah fungsi blade ya.

```php
@php
$dummy_service = array(
array(
'icon' => "fa-diamond",
'title' => "Sturdy Templates 1",
'description' => "Our templates are updated regularly so they don't break. 1"
),
array(
'icon' => "fa-paper-plane",
'title' => "Sturdy Templates 2",
'description' => "Our templates are updated regularly so they don't break 2."
)
);
@endphp
```
11:13 PM
Aku perlu sebuah data dummy_service yang akan di repeat untuk sebuah view di bawah ini.

Aku buat dummynya hanya dua data dulu.

```php
@php
$dummy_service = array(
  array(
  'icon' => "fa-diamond",
  'title' => "Sturdy Templates 1",
  'description' => "Our templates are updated regularly so they don't break. 1"
  ),
  array(
  'icon' => "fa-paper-plane",
  'title' => "Sturdy Templates 2",
  'description' => "Our templates are updated regularly so they don't break 2."
  )
);
@endphp
```

Fungsi di atas itu sama seperti ini kalau tanpa blade ya.

```php
<?php
$dummy_service = array(
  array(
  'icon' => "fa-diamond",
  'title' => "Sturdy Templates 1",
  'description' => "Our templates are updated regularly so they don't break. 1"
  ),
  array(
  'icon' => "fa-paper-plane",
  'title' => "Sturdy Templates 2",
  'description' => "Our templates are updated regularly so they don't break 2."
  )
);
?>
```
 
Okay selanjutnya ada fungsi blade`@each`

@each('items.sub-services', $dummy_service, 'service')
 
$dummy_service adalah sebuah data array yang akan di render dan tampilkan secara berulang dengan script html yang ada pada items.sub-services.
 
Isi dari file `sub-service.blade.php`

```php
<div class="col-lg-3 col-md-6 text-center">
<div class="service-box mt-5 mx-auto">
<i class="fa fa-4x {{ $service['icon'] }} text-primary mb-3 sr-`icons "></i>
<h3 class="mb-3"> {!! $service['title'] !!} </h3>
<p class="text-muted mb-0"> {!! $service['description'] !!} </p>
</div>
</div>
```
 
Nah, cara menampilkan isi dari array `$dummy_service` pada view sub-service.blade.php dengan memanggil variabel service
 
Hasil tampilan service jadi seperti apa?

Hanya menampilkan 2 service karena array `$dummy_service` hanya ada 2 data.
`@each` ini kalau pada blade hampir sama fungsinya dengan `@foreach` hanya saja `@each` lebih simpeld dari itu.
Mungkin nanti aku buat artikel saja ya atau bisa dilanjutkan.
Baiklah teman-teman. Aku akhir Kulgram malam ini ya.
Terimakasih untuk partisipasinya.

Insya Allah aku akan buatkan artikelnya dan akan share disini.
Bagi teman-teman yang ingin bertanya bisa tanyakan di sini atau japri ya.
Selamat malam dan selamat beristirahat
 
# Q&A
HILMI KHOIRULLOH
Nah mba misalkan kita mau buat variable baru di tapi bukan lewat parameter yang dioper saat manggil fungsi view

Saya disini biasanya makenya 
```php
@php
$new_var = null;
@endphp
```

Misalkan saya pakai metode diatas saya ngerasa kaya pake php biasa. 
Jadi intinya apakah bisa membuat variabel baru pada bladenya saja tanpa melalui kode `@php @endphp` ?
JAWABAN
Kalau ini berarti kamu melakukan deklarasi nilai variabel pada view ya?

Iya kalau itu pake bladenya `@php` dan `@endphp`.

Jika menggunakan konsep MVC sebenarnya lebih baik kalau sebuah variabel di definisikan pada controller mas. Kurang tepat jika di definisikan pada view. Memang cara untuk deklarasikan variabel dengan `@php` dan `@endphp`

Hilmi Khoirulloh
Misalkan `@each` data arraynya `[]` error apa tetap ke render mba ?
 
JAWABAN
kosong maksudnya? Kalau kosong dia tidak akan ada tampilan apa-apa
kalo datanya kosong ,hasilnya juga blank ngga error
