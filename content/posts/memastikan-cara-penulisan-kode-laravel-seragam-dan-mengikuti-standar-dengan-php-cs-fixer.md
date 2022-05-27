+++
title = "Memastikan cara penulisan kode Laravel seragam dan mengikuti standar dengan PHP CS Fixer"
date = 2021-02-10T12:31:39+07:00
draft = false
tags = ["coding-style", "laravel", "phpcsfixer"]
categories = ["Laravel"]
meta = true
+++

## Pengantar

Kali ini saya akan menunjukkan cara menggunakan tool [PHP Coding Standards Fixer (PHP CS Fixer)](https://github.com/FriendsOfPHP/PHP-CS-Fixer) di proyek aplikasi [Laravel](https://laravel.com) kalian. Jika sebelumnya kalian ingin cara penulisan kodenya mengikuti standar pengkodean PHP seperti yang didefinisikan dalam PSR-1, PSR-2, dll, atau seragam antar programmer meskipun menggunakan IDE/editor yang berbeda, maka tutorial ini bisa sangat ngebantu.

## Persyaratan

* Versi minimum [PHP](https://www.php.net) yang digunakan harus PHP 5.6.0.

* Pastikan teman-teman menjalankan perintah-perintah berikut didalam proyek [Laravel](https://laravel.com) kalian ya.

## Instalasi

    composer require friendsofphp/php-cs-fixer --dev

## Konfigurasi

Menentukan aturan yang ingin digunakan dalam proyek [Laravel](https://laravel.com) kalian:

Buat file *.php_cs* di direktori root proyek kalian, dan gunakan contoh aturan ini: [*Laravel Coding Style Ruleset](https://gist.github.com/FransiscusRolandaMalau/41d5c147dc4a7ff8dd1a02edb2bdabdf)*.

Jangan lupa untuk menambahkan *.php_cs.cache* ke file *gitignore *kalian ya.

## Pemakaian

Melakukan perbaikan secara otomatis:

    vendor/bin/php-cs-fixer fix --allow-risky=yes --diff

Untuk melakukan pengecekan saja tanpa perbaikan, tambahkan opsi --dry-run:

    vendor/bin/php-cs-fixer fix --allow-risky=yes --diff --dry-run
    vendor/bin/php-cs-fixer fix --allow-risky=yes --diff --dry-run

## Penutup

Dalam tutorial sederhana ini, kita telah memastikan cara penulisan kode [Laravel](https://laravel.com) kita mengikuti standar dengan menggunakan PHP CS Fixer. Selain itu, kalian juga dapat membagikan file gaya aturan kalian (.php_cs) ke teman-teman kalian agar gaya kode kalian seragam.

Semoga tutorial ini bisa membatu:).
