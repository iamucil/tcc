# Berkolaborasi di git repository

Selain untuk mengelola aset digital milik diri sendiri, kita bisa menggunakan Git untuk berkolaborasi dalam suatu repo di GitHub yang bisa diakses bersama. Dalam kasus seperti ini, berarti ada 2 peran:

1. Pemilik repo, sering disebut sebagai *upstream author*.
2. Kontributor, yaitu orang-orang yang akan berkontribusi memberikan konten.

Untuk situasi seperti ini, diasumsikan:

1. *Upstream author* telah membuat repo git di GitHub
2. Kontributor telah mengetahui adanya repo tersebut, tertarik untuk berkontribusi, sudah mengetahui apa yang akan diberikan ke proyek (repo GitHub *upstream author*) tersebut.
3. Pembahasan selanjutnya adalah tentang bagaimana kontributor bisa mengirimkan kontribusi ke repo GitHub milik *upstream author*.

Skenario:

1. *Upstream author* adalah *stodioo*.
2. Kontributor adalah *iamucil*
3. Repo dari *upstream author* adalah **roast** yang bisa diakses di [https://github.com/stodioo/roast](https://github.com/stodioo/roast)

## Forking

Fork adalah membuat clone dari suatu repo di GitHub milik *upstream author*, diletakkan ke milik kontributor. Fork hanya dilakukan sekali saja. Kontributor harus mem-*fork* repo *upstream author* sehingga di repo kontributor muncul repo tersebut. Proses *forking* ini dijelaskan dengan langkah-langkah berikut:

1. Login ke Github
2. Akses repository *Upstream Author* di [https://github.com/stodioo/roast](https://github.com/stodioo/roast)

3. Pada sisi kanan atas, pilih fork.

    ![Fork Repository](imgs/01_fork_repository.png)

4. Pilih repository akan ditaruh di akun yang mana

    ![Choose account](imgs/02_fork_repository_pilih_lokasi_fork.png)

    dalam kasus ini, hasil forking akan ditaruh pada akun *iamucil*

    ![Process forking](imgs/03_proses_forking.png)

5. Setelah selesai proses forking, clone repository ke local untuk mulai berkontribusi. Dengan cara, pilih tombol *Clone or Download* yang ada di sisi kanan atas, terdapat 2 protocol untuk clone repository yaitu **ssh** dan **https**. Sesuaikan dengan kenyamanan.

    ![clone url](imgs/04_copy_repo_url.png)

    Clone repostory ke local dengan menjalanlan perintah:

    ```git clone repository_url```

    ![Clone local](imgs/05_clone_repository.png)

    Keterangan: Clone repository [https://github.com/iamucil/roast](https://github.com/iamucil/roast) ke folder local `/data/github.com/iamucil/roast`

6. Buat perubahan. Dalam kasus ini melakukan perubahan file `README.md`.

    ```bash
    cd roast
    vim README.md
    ```

7. Lihat perubahan dengan perintah `git status`

    ![Git Status](imgs/07_git_status.png)

    Keterangan: `git status` adalah perintah `git` untuk melihat perubahan apa saja yang ada di local, dalam hal ini terlihat ada 1 buath file `README.md` berbeda dengan remote.

8. Update perubahan dengan perintah `git add .` atau `git add NAMA_FILE/FOLDER` seperti yang ada di layar.

    `git add .` dengan perintah ini git akan menambahkan semua file yang berubah atau file baru yang di deteksi oleh git, jika ada perubahan di local.\
    `git add NAMA_FILE/FOLDER` dengan perintah ini user bisa menentukan file folder mana yang akan di tambahkan.

    ![Git add](imgs/08_git_add.png)

    Keterangan: `git add .` perintah ini digunakan untuk menambahkan `untracked files` yang ada di `local` ke `remote`. Jalankan perintah `git status` untuk memastikan file sudah daftarkan untuk di tambah ke remote repository ketika di lakukan push, ditandai dengan status `new file: .empty` dengan warna hijau.

9. `git commit`: Setelah perubahan yang diinginkan sudah selesai di lakukan, file/folder sudah ditata dan sudah ditambahkan, langkah selanjutnya rekam perubahan (commit).

    ![Commit](imgs/10_git_comit.png)

    Keterangan: `git commit -am 'update README.md'` perintah ini digunakan untuk merekam perubahan yang ada di local dan memberikan pesan perubahan apa yang dilakukan atau memeberi pesan kepada author/kontributor lain tentang pekerjaan yang sudah dilakukan.

10. Push/kirim perubahan yang ada di local ke repository git, setelah perubahan yang ada dilocal di commit.

    ![Git push](imgs/11_git_push.png)

    Keterangan: `git push origin master` > Push (kirim) perubahan ke remote:origin yaitu repository milik sendiri, `master` adalah nama branch yang digunakan untuk menyimpan file/asset yang sudah di ubah.

11. Akses repository git untuk melihat perubahan yang dilakukan sudah berhasil di kirim.

    ![New Change](imgs/14_new_change.png)

    Terdapat pesan `this branch is 1 commit ahead of stodioo:master` menandakan perubahan sudah berhasil dilakukan dan sudah terkirim ke repository yang ada di github, dan siap untuk di *PR*

12. Pull request ke `upstream` repo, dengan cara klik pada tombol `New pull request`

    ![Compare changes](imgs/15_compare_repo.png)

    Muncul halaman baru untuk melakukan pull request, halaman ini digunakan untuk melihat dan membandingkan perubahan apa saja yang di lakukan di head repository dengan base repository. Halaman ini juga digunakan untuk memastikan bahwa perubahan sudah sesuai dengan keinginan dan tidak ada `conflict` ketika akan di lakukan *PR*.

    Jika sudah yakin dengan perubahan yang dilakukan, klik tombol hijau : `Create pull request` untuk melakukan Pull Request.

13. *Open Pull Request*

    ![Open Pull Request](imgs/16_open_pr.png)

    Jika file yang diubah tidak ada conflict akan ada notifikasi `Able to merge` ini menandakan tidak ada masalah dengan perubahan yang kita lakukan dengan base repository, dan pull request bisa di merge. Form ini digunakan untuk mencatat pesan PR ke pemilik base repository. Klik tombol `Create pull request` untuk melakukan `pull request`.

    ![PR Opened](imgs/17_pr_opened.png)

    Keterangan: Tampilan PR sudah dibuka, dan menunggu proses `aprove` dari pemilik base/upstream repository.

14. Pada repo `upstream author`, muncul angka 1 (artinya jumlahnya 1) pada Pull requests di bagian atas.

15. *Upstream author* bisa menyetujui setelah melakukan review: klik pada ```Pull requests```, akan muncul PR dengan message seperti yang ditulis oleh kontributor (*Add: contributor*). Klik pada PR tersebut, review kemudian klik ```Merge pull request``` diikuti dengan ```Confirm merge```. Setelah itu, status akan berubah menjadi ```Merged```.

    ![PR Merged](imgs/18_pr_merged.png)

    > *PR Closed* adalah `close a pull request` tanpa harus melakukan merge. Perubahan yang di request oleh kontributor tidak akan di merge oleh `upstream author`, hal ini bisa di karenakan perubahan yang direquest dianggap tidak relevan atau sudah tidak perlukan lagi.

    ![PR Closed](imgs/19_pr_closed.png)

## Conflict

Konflik dalam git menandakan terdapat persamaan antara source file milik kontributor dan `upstream author`, hal ini bisa dikarenakan satu user dan yang lain melakukan edit/update file yang sama, sehingga `PR` tidak bisa langsung di merge. Untuk mengatasi konflik ini, kontributor harus membenarkan file yang konflik, menyocokkan dengan upstream, setelah itu lakukan proses commit dan push perubahan sehingga status conflict hilang dari halaman PR.

## Sinkronisasi dengan Upstream

Untuk selalu update dengan base repository, tambahkan base/upstream repository di repository local. Untuk melihat daftar remote repository jalankan perintah

```bash
git remote -v
```

![Git remote view](imgs/20_git_remote_view.png)

Tambahkan upstream repository url dengan nama upstream.

![git remote add upstream](imgs/21_git_remote_add_upstream.png)

Untuk memastikan remote repository berhasil di daftarkan jalankan kembali
```bash
git remote -v
```

Untuk update local dengan upstream, jalankan perintah

```bash
git fetch --all
git merge upstream/master
```

![git fetch](imgs/22_git_fetch_merge.png)

Perintah di atas digunakan untuk mencocokan remote repository dengan local. Jika ada perubahan akan muncul seperti pada gambar di atas, untuk melakukan update yang di local jalankan perintah `git merge repository`.

Jalankan `git push origin master` untuk melakukan update origin dengan upstream.

[<< Halaman Utama](../README.md)
