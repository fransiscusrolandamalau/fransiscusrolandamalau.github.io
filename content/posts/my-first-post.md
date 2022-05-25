+++
title = "Tutorial Laravel Mix"
date = 2020-10-17T12:31:39+07:00
draft = false
tags = ["laravel", "webpack"]
categories = ["laravel"]
meta = true
+++

![](https://cdn-images-1.medium.com/max/2400/1*Yr2m6xaljXodc_ovPibikQ.png)

## Pengantar

Dalam tutorial ini saya akan menunjukkan cara menggunakan Laravel Mix diaplikasi Laravel Teman-teman. Jika Teman-teman yang udah pake Laravel cuman masih belum tau apa itu Laravel Mix atau udah tau cuman masih belum terlalu paham cara penggunaannya semoga tutorial bisa ngebantu teman-teman sekalian yaa.

## Apa itu Laravel Mix?

Menurut [Laravel’s Offical Documentation](https://laravel.com/docs/8.x/mix)
> # Laravel Mix provides a fluent API for defining Webpack build steps for your Laravel application using several common CSS and JavaScript pre-processors.

Singkatnya ginilah: Laravel Mix itu sebuah package frontend yang disiapkan untuk manajemen asset di Laravel. Asset yang dimasud bisa berupa CSS, JS, Image, Font, dan lain-lain.

## Proses Instalasi Laravel Mix

Dalam instalasi baru Laravel, Teman-teman akan menemukan file package.json diroot struktur direktori Anda. File default ini akan menyertakan semua yang Teman-teman butuhkan untuk memulai. Pastikan juga telah menginstal NPM diserver local kita ya.
Atau Teman-teman dapat menginstal dependensi yang direferensikan dengan menjalankan:

    npm install

## Menjalankan Mix

Mix adalah lapisan konfigurasi di atas Webpack, jadi untuk menjankannya Teman-teman hanya perlu menjalankan salah satu skrip NPM berikut:

    // menggabungkan tanpa minify…
    npm run dev

    // jika ingin yang terminify..
    npm run production

## Melihat Assets yang Melakukan Perubahan

Perintah npm run watch akan terus berjalan diterminal Teman-teman dan melihat semua perubahan pada file yang relevan. Webpack kemudian akan secara otomatis mengompilasi ulang asset Teman-teman ketika mendeteksi perubahan.

    npm run watch

## Mari Memulai dari Stylesheets

File webpack.mix.js adalah untuk kompilasi asset. Anggap saja sebagai konfigurasi ringan Webpack.

### Sass

mix.sass memungkinkan Teman-teman untuk mengkompilasi Sass ke dalam CSS. Teman-teman dapat menggunakan seperti ini:

    mix.sass('resources/sass/app.scss', 'public/css');

Kalo lebih dari satu:

    mix.sass('resources/sass/app.sass', 'public/css')
        .sass('resources/sass/admin.sass', 'public/css/admin');

### Plain Css

Jika Teman-teman ingin menggabungkan beberapa CSS biasa menjadi satu file juga bisa, gini caranya:

    mix.styles([
        'resources/assets/vendor/css/bootstrap.min.css',
        'resources/assets/vendor/css/owl.carousel.min.css',
        'resources/assets/vendor/css/owl.theme.default.min.css',
        'resources/assets/vendor/css/slick.css',
        'resources/assets/vendor/css/slick-theme.css'
    ], 'public/css/vendor.css');

## Kita lanjut dengan JavaScript

Gimana kalo untuk file JavaScript? tinggal gini aja nanti dia akan mengompilasi kode JSnya.

    mix.js('resoureces/app.js', 'public/js');

Kalo beberapa JS juga biasa menjadi satu file juga bisa, gini caranya:

    mix.scripts([
        'resources/assets/vendor/js/jquery-3.5.1.min.js',
        'presources/assets/vendor/js/bootstrap.bundle.min.js'
    ], 'public/js/vendor.js');

## Copy File atau Direktori

Untuk copy file atau direktori juga bisa, contoh dibawah adalah memindahkan beberapa file font dari folder node_modules ke lokasi lain.

    mix.copy('node_modules/font-awesome/fonts/*', 'public/fonts/');

Kalo untuk mindahin folder pake yang ini.

    mix.copyDirectory(‘resources/img’, ‘public/img’);

## Versioning

Nah ada lagi nih fitur versioning yang secara otomatis bakal nambahin hash unik ke nama file yang kita kompilasi, dan juga untuk merecord versi asset sehingga ketika ada perubahan nggak akan ngecache di browser client

    mix.js('resources/js/app.js', 'public/js')
        .version();

Kalo semua pengen diversioning pas production bisa pake cara ini.

    if (mix.inProduction()) {
     mix.version
    }

Semoga tutorial ini bisa membatu Teman-teman.
