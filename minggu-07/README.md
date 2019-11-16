# PaaS Provider

## Google App Engine

![Google App Engine](./img/google_app_engine.jpg)

### Apa itu Google App Engine

Google App Engine merupakan salah satu layanan PaaS (Platfrom as a Services) dari Google. App Engine merupakan platform yang memungkinkan pengembang untuk membuat dan menjalankan aplikasi-aplikasi dengan fasilitas infrastruktur milik Google. Versi gratis dari platform ini memiliki kapasitas penyimpanan 500 MB dan kapasitas CPU dan bandwith yang cukup untuk 5 juta page-view setiap bulannya.

Saat diluncurkan, bahasa pemrograman yang mendukung adalah Python. Versi terbatas dari web framework Django juga tersedia. Demikian halnya dengan framework  aplikasi Goole yang fungsinya sama dengan JSP atau ASP.NET. Dengan _runtime Java_ App Engine, pengguna dapat membangun aplikasi menggunakan standar teknologi java, termasuk JVM, Java Servlet dan bahasa pemrograman Java atau bahasa lainnya menggunakan JVM-Based atau compiler, seperti javascript atau Ruby. App Engine juga menyediakan runtime khusus Python, yang mencakup bahasa Python dan standar library dari python. Saat ini Google App Engine tersedia untuk beberapa runtime bahasa pemrograman selain java dan python.

![Google App Engine Language Selection](./img/gae_runtime.png)

Lingkungan runtime ini dibangun guna memastikan bahwa aplikasi yang dibangun dapat berjalan cepat, aman,  tanpa gangguan dari aplikasi lain pada sistem. Klik tautan untuk memulai >> [Google App Engine](https://cloud.google.com/appengine/docs/).

## GIGALIXIR

Gigalixir adalah sebuah Platform-as-a-service yang khusus digunakan untuk menjalankan aplikasi yang menggunakan bahasa pemrograman elixir. Dengan [gigalixir](https://gigalixir.com), developer tidak perlu memikirkan setup platform dan environment yang akan digunakan untuk menjalankan aplikasi menggunakan bahasa pemrograman elixir, mengingat pemrograman ini terbilang masih baru. Lihat lebih detail di https://gigalixir.com.

Untuk bisa menggunakan service gigalixir, lakukan pendaftaran di gigalixir.com, Jalankan step-step yang ada sampai akun terverifikasi.

## Gigalixir CLI

### Prerequisites:

1. Python3, Python2
2. git
3. pip
4. os linux

### Install gigalixir cli untuk melakukan upload app dari local ke gigalixir.

![install gigalixir cli](img/gigalixir_02_install_cli.png)

Parameter `--user` disematkan supaya binary dari gigalixir bisa dijalankan oleh user biasa, tanpa perintah sudo.

### Login gigalixir

![gigalixir login](img/gigalixir_03_login.png)

Login dengan menggunakan email dan password yang sudah terdaftar dan terverifikasi dari gigalixir.

### Buat app

![Create an app](img/gigalixir_03_create.png)

Verifikasi jika app sudah sukses di buat dengan mengakses halaman dashboard gigalixir. https://www.gigalixir.com/#/dashboard

![dashboard](img/gigalixir_04_dash.png)

### Deploy

Build dan deploy, untuk build dan deploy gigalixir menggunakan perintah `git`. Pastika remote url sudah ada yaitu gigalixir. Jalankan perintah `git remote -v` untuk menampilkan daftar remote repository. Untuk build dan deploy ke gigalixir lakukan push local ke remote repository (gigalixir)

```bash
git push gigalixir master
```

![build and deploy](img/gigalixir_04_build_deploy.png)

Jika proses build dan deploy sudah berhasil cek menggunakan perintah curl

```bash
curl -v https://helo.gigalixir.com
```

Sesuaikan `helo` dengan nama aplikasi yang dibuat.

> Issue: Tidak bisa deploy ke gigalixir
    ![issue](img/gigalixir_issue.png)

[<< Halaman Utama](../README.md)
