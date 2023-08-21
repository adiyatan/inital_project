# [SIULP LKPP](https://simku-dev.merapi.javan.id)

# Daftar isi
1. [Requirements](#requirements)
2. [Tutorial Menjalankan Aplikasi](#tutorial-menjalankan-aplikasi)
3. [Tutorial Setup Folder](#tutorial-setup-folder)
4. [Tutorial Setup PHP](#tutorial-setup-php)
5. [Tutorial Database](#tutorial-database)
6. [Tutorial Copy DB from Merapi to Local](#tutorial-copy-isi-db-merapi-ke-local)
7. [Tutorial Menjalankan Aplikasi](#tutorial-menjalankan-aplikasi)

## Requirements
1. [PHP 7.1](https://windows.php.net/downloads/releases/archives/)
2. [Composer 2](https://getcomposer.org/download/)
3. MySQL
4. [DBeaver](https://dbeaver.io/download/)
5. [Laragon](https://laragon.org/download/index.html)
6. [Navicat](https://www.navicat.com/en/download/navicat-for-mysql)
7. PHP.ini extensions:
   - ext-dir
   - ext-curl
   - ext-pgsql

## Tutorial Setup Folder
1. Clone repository
2. Buka folder `protected`
3. Ekstrak file `vendor.zip` dan `optimus.zip` pada lokasi folder yang sama sehingga tampilannya seperti ini:
4. Buka kode editor anda dan masuk buka folder `protected`
5. Tekan `.env-old` lalu copy semua kode yang ada dan buat file baru di folder `protected ` dengan nama `.env` dan pastekan kode yang di copy.
6. Buat folder `storage`, lalu didalamnya buat folder `framework` dan didalamnya lagi tambahkan 3 folder baru bernama `cache`, `sessions`, dan `views`

## Pastikan setup folder seperti ini =

SIULP LKPP/

├─ protected/

│  ├─ Optimus

│  ├─ Storage

│  │  ├─ Framework

│  │  │  ├─ Cache

│  │  │  ├─ Sessions

│  │  │  ├─ Views

│  ├─ Vendor

│  ├─ .env

│  ├─ ... (other project files)

├─ ... (other project directories and files)

## Tutorial Setup PHP
1. Pastikan anda menggunakan PHP versi 7.1, gunakan terminal untuk mengecek dan ketikan `PHP -v` di folder simku
2. Jika versi tidak sesuai maka download file php pada link diatas dan simpan di folder laragon seperti berikut
  ![php](https://github.com/adiyatan/inital_project/blob/main/gambar/php.png)
3. Jika sudah tekan `windows` pada keyboard ketikan `environment variabel`
4. Maka sistem akan membuka  `system properties` seperti berikut =
   ![environment]( https://github.com/adiyatan/inital_project/blob/main/gambar/environtmen.png)
5. Lalu tekan tombol environment variabel dibawah
6. Cari `path` dan tekan 2x
 ![path](https://github.com/adiyatan/inital_project/blob/main/gambar/path.png)
7. Tekan tombol `new` dan pastekan link sesuai dengan versi PHP yang anda download, misal `C:\laragon\bin\php\php-7.1.33-Win32-vc14-x64`
8. Buka ulang vscode dan lakukan `PHP -v` dan pastikan menggunakan PHP versi 7.1
9. Jika sudah buka laragon lalu click kanan -> php -> php.ini dan cari 3 extension diatas. jika ketemu maka hapus `;` dibelakangnya

## Tutorial database
1. Buka laragon -> click kanan -> MySQL -> startMySQL
2. (Sambungkan DB merapi) Buka DBeaver -> tambah koneksi -> sesuaikan dengan DB merapi
   
| Host    | merapi.javan.id |
|---------|-----------------|
|DB       |simku_lkpp_dev   |
|user     |root             |
|pw       |J4v4nDev!@#      |
|port     |33307            |

3. (Buat DB local) Buka DBeaver -> tambah koneksi -> isi bebas, contoh

| Host     | localhost       |
|----------|-----------------|
| DB       | siulp           |
| User     | root            |
| Password |                 |
| Port     | 3306            |

4. Jika sudah maka seting `.env` sesuai dengan DB local, contoh =
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=siulp
DB_USERNAME=root
DB_PASSWORD=
```

## Tutorial copy isi DB merapi ke local
1. Buka `navicat`
2. Tekan tombol `connection` di ujung kiri atas dan isi sesuai dengan `DB merapi` dan `DB local`
3. Download file sql pada link berikut, [tekan disini](https://drive.google.com/file/d/1WnMs9aKo4T2hKN5JUSj6XYOvy2UjTukv/view)
4. Buka file `sql` yang sudah di download dan replace `0000-00-00` dengan `2022-01-01` (replace all)
5. Jika sudah buka `navicat` dan klik Db local -> nama table -> execute sql
   
   ![navicat](https://github.com/adiyatan/inital_project/blob/main/gambar/navicat.png)
6. execute sql

## Tutorial Menjalankan Aplikasi
pastikan semua tutorial diatas sudah dilakukan
1. buka folder project di vscode
2.  buka terminal dan jalankan skrip berikut = `cd proteched`
3.  lalu jalankan `php artisan config:clear` dan `php artisan cache:clear`
4.  jalankan skrip berikut = `cd..`
5.  jalankan `php -S localhost:8000`
6.  aplikasi akan berjalan di `http://localhost:8000/`
