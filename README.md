# Tutorial-laravel

Bagaimana cara menjalankan laravel

## Instalasi

Install XAMPP atau paket web server lainnya.

```
https://www.apachefriends.org/index.html
```

Install Composer agar memudahkan saat install paket laravel.

```
https://getcomposer.org/Composer-Setup.exe
```

jalankan diterminal untuk install laravel.

```
composer global require laravel/installer

laravel new example-app

cd example-app

php artisan serve
```

## Membuat Controller

Bisa dengan menjalankan.

```
php artisan make:controller NamaController
```

## Melakukan Migration

Sebelum melakukan migration hubungkan database dengan menjalankan mysql dan buka file .env dan ubah settingan sesuai dengan konfigurasi yang anda perlukan

Di Terminal kita bisa menjalankan

```
php artisan migrate
```

Jika kita ingin menarik migrasi satu tahap setiap melakukan migration
Bisa dengan menjalankan perintah

```
php artisan migrate:rollback
```

## Membuat Tabel Migration

Perlu diperhatikan setiap membuat table harus mengikuti standar dari laravel itu sendiri seperti contoh

```
php artisan make:migration create_tasks_table
```

Menambahkan column tanpa melakukan rollback

```
php artisan make:migration add_column_user_tasks_table --table=tasks
```
