# Tutorial Laravel | Step by step

## Create Laravel Project

```sh
php -v
# Output => PHP version 8.3.7 (D:\SourceInstaller\laragon\bin\php\php-8.3.7-Win32-vs16-x64\php.exe)

composer --version
# Output => Composer version 2.7.7 2024-06-10 22:11:12

cd /d/Applications/Data/PHP-Laravel
composer create-project laravel/laravel laravel-backend
# Akan ter-install Laravel version 11.1.1
cd laravel-backend

# Update .env file
cp .env.example .env
## ganti DB_CONNECTION=mysql dll
php artisan migrate

# Generate key
php artisan key:generate
php artisan serve
```

## Starter Project Laravel 10 Stisla

```sh
# Harus sudah mendaftarkan ssh key di github
ssh-keygen
# Copy isi dari file id_rsa.pub ke github
# Git clone
git clone git@github.com:bahrie127/laravel10-stisla.git
cd laravel10-stisla
composer install
npm install
# Edit env file
php artisan key:generate
php artisan migrate
php artisan db:seed
php artisan migrate:refresh

npm run build
npm run dev

php artisan serve

```

## Install Laravel Food Delivery Order

```sh
composer create-project laravel/laravel laravel-food-delivery-backend
# Install Laravel Sanctum
php artisan install:api
# Tambahkan use HasApiTokens di Models\Users dari Laravel\Sanctum\HasApiTokens


# Perbaiki struktur table
php artisan make:migration "add_colum_at_users" --table=users
# atau bisa pakai VS Code Extension Laravel, ketik Artisan Make Migration
# Update file migrationnya, tambahkan field
# Update fillable di Models\User juga


# Buat API Auth untuk Register dan Login
php artisan make:controller Api/AuthController
# Update file routes/api.php untuk auth
php artisan optimize

# Buat API Product model dengan migrationnya
php artisan make:model Product -m
# Update file migrationnya
php artisan migrate
# Update file Models\Product, isi fillable dan relasinya
php artisan make:controller Api/ProductController
# Tambahkan Route::apiResource product di file routes/api.php
php artisan optimize
php artisan route:list


# Buat API Order
php artisan make:model Order -m
php artisan make:model OrderItem -m
php artisan make:controller Api/OrderController
```

## Reference

- [Laravel Sanctum | API Token](https://laravel.com/docs/11.x/sanctum)
