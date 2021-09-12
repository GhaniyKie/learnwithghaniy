---
title: Instalasi HUGO di Ubuntu 20.04
description: Berkenalan dengan SSG (Static Site Generator) serta Petunjuk instalasi Hugo v0.87.0 di Ubuntu 20.04
date: 2021-08-12
author: Abdul Hakim Ghaniy
keywords: ["Ubuntu 20.04", "Hugo", "Install", "Static Page"]
tags: [hugo, ubuntu, static-site]
---

Sebelum kita mulai, alangkah baiknya kita ketahui dahulu apa itu Hugo, Static Site Generator, CMS dan Perbedaan Hugo dengan CMS _(Content Management System)_ lainnya.


|**Daftar Isi**  |
|---------|
|[Apa itu Hugo dan _Static Site Generator_](#apa-itu-hugo-dan-_static-site-generator_)|
|[Mengapa Hugo Berbeda Dari CMS Lain?](#mengapa-hugo-berbeda-dari-cms-lain)|
|[Persiapan Instalasi](#persiapan-instalasi)|
|- [Instalasi GIT](#instalasi-git)|
|- [Instalasi Snap](#instalasi-snap)|
|[Instalasi Hugo](#instalasi-hugo)|


# Apa Itu Hugo dan _Static Site Generator_?

_Static Site Generator_ atau SSG adalah sebuah _tools_ yang dapat membantu kita untuk membuat website statis **"Secara Dinamis"**. Pengertian "Dinamis" disini adalah kita dapat membuat setiap struktur yang ada di halaman Web seperti _Header_, _Main_, _Article_ dan _Section_, _Footer_ serta bagian-bagian lainnya menjadi sub-sub bagian yang terpisah secara mandiri, **dan dapat dipakai berkali-kali** layaknya membuat _layouts_ untuk website dinamis.

Lalu, yang membedakan antara website dinamis dengan website statis adalah bagaimana website tersebut menanggapi permintaan "data". Jika pada website dinamis kita dapat memberikan informasi ke server seperti informasi login, password, atau kartu kredit, pada website statis halaman yang ditampilkan hanyalah apa yang sudah dimiliki server. Kita tidak dapat mengirimkan data apapun ke server. Jenis dari Website statis ini biasanya berupa halaman blog (seperti website [Learn With Ghaniy](https://learnwithghaniy.web.id)), ataupun berupa _profile page_, baik perusahaan atau perseorangan. Situs Blogger juga termasuk dari Website Statis. ```Kita akan membahas perbedaan web statis dan dinamis secara terperinci di artikel selanjutnya```.

Nah, Hugo sendiri adalah salah satu dari berbagai macam _tools_ atau _framework_ SSG tersebut.

# Mengapa Hugo Berbeda Dari CMS Lain?

CMS adalah salah satu _tools_ yang biasa digunakan untuk membuat website dinamis (dapat mengirim permintaan dan server akan mengirim data yang diminta tersebut) tanpa perlu membuat website tersebut **dari nol**. Kita dapat mengatur website -sekalipun- tanpa pengetahuan pemrograman samasekali.

CMS juga sering digunakan untuk membuat blog, _company profile_, situs belanja daring, dan lain-lain.

Lalu apasih bedanya Hugo dengan CMS lainnya seperti Wordpress, Drupal dsb?

- Pertama, Hugo (dan SSG) pada umumnya **hanya** menyajikan konten **Statis**.
- Kedua, perlu pengaturan awal untuk mulai menggunakan SSG.
- Ketiga, SSG lebih leluasa untuk berkreasi dengan tampilannya (jika kita sudah memiliki dasar pemrograman, khususnya web) dibanding CMS pada umumnya.
- Keempat, CMS membutuhkan Sumber Daya yang lebih besar dibanding SSG (butuh server khusus untuk proses menjalankan bahasa _Server Side_ dan juga _Database_ nya).
- Kelima, SSG **lebih aman** dibanding CMS. (Ini suatu hukum timbal-balik karena Server SSG tidak memproses Permintaan Data apapun dari Klien)
- Keenam, untuk mulai menggunakan SSG, kita harus sudah memiliki pengetahuan dasar tentang GIT _Version Control_, dan perintah-perintah di Terminal Linux / _Command Line_ Windows, serta pengetahuan dasar pemrograman Web.

Kita sudah mengetahui perbedaan mendasar dari CMS dan SSG. Silahkan dipertimbangkan untuk menggunakan SSG atau CMS sesuai dengan kebutuhan kalian.

Oke... Sekarang kita lanjut ke persiapan instalasi Hugo.

# Persiapan Instalasi

Sebelum mulai, pastikan bahwa GIT Version Control sudah terinstal di komputer kalian dengan mengetik perintah ```git --version```. Perintah tersebut akan menampilkan versi terkini dari GIT yang terinstal. Jika ada pesan kesalahan yang muncul seperti ```git: command not found```, kemungkinan besar GIT belum terinstal di komputer kalian.

Skip persiapan ini dengan melanjutkan ke tahap **[Instalasi Snap](#instalasi-snap)** jika Git sudah terinstal dan berjalan dengan baik.

## Instalasi GIT

Ikuti langkah-langkah berikut:
- Buka terminal kalian dengan mengklik tombol ```CTRL+ALT+T``` berbarengan.
- Pastikan untuk mengupdate repository dari Ubuntu dengan perintah ```sudo apt update -y && sudo apt dist-upgrade -y```.
- Tunggu sampai proses update selesai.
- Jika sudah, masukkan perintah berikut ```sudo apt install git```.
- Pastikan instalasi GIT tersebut berhasil dengan perintah berikut ```git --version```.
- Pastikan kalian sudah memiliki akun (pilih salah satu: [Github](https://github.com/), [Gitlab](https://gitlab.com/), [Atlassian Bitbucket](https://bitbucket.org/)) atau provider GIT lainnya.
- Masukkan Username GIT kalian pada konfigurasi global GIT di komputer dengan perintah ```git config --global user.name "USERNAME_GIT_KALIAN"```.
- Masukkan Email GIT kalian pada konfigurasi global GIT di komputer dengan perintah ```git config --global user.email "email.kalian@example.com"```.
- Mulailah berlatih menggunakan GIT dengan banyak membaca tutorial dan dokumentasi.

## Instalasi Snap

Ada banyak sekali cara untuk menginstal Hugo, salah satunya menggunakan _Snap Package_. Untuk user Linux (terlebih Ubuntu) sangat disarankan untuk menggunakan _Snap Package_ saat instalasi Hugo dibanding menggunakan apt _package_, tarball, atau _build from source_. Karena update terkini dari release yang minim bug, serta otomatis update ke versi yang lebih baru jika Snap mendeteksi adanya pembaruan.

Pastikan Snap telah terinstal di komputer kalian dengan mengetik perintah ```snap --version``` di terminal. Jika versi terkini yang muncul, kalian bisa melanjutkan ke tahap **[Instalasi Hugo](#instalasi-hugo)**. Jika ada pesan kesalahan yang muncul seperti ```snap: command not found```, kemungkinan besar Snap belum terinstal di komputer kalian.

Ikuti langkah-langkah berikut:
- Buka terminal kalian dengan mengklik tombol ```CTRL+ALT+T``` berbarengan.
- Pastikan untuk mengupdate repository dari Ubuntu dengan perintah ```sudo apt update -y && sudo apt dist-upgrade -y```.
- Tunggu sampai proses update selesai.
- Jika sudah, masukkan perintah berikut ```sudo apt install snapd```.
- Untuk mengetes keberhasilan instalasi snap, masukkan perintah berikut ```sudo snap install hello-world```.
- Lalu ketik ```hello-world```.
- Jika belum muncul perintah Snap coba _restart_ komputer kalian.

# Instalasi Hugo

Jika _pre-installation requirements_ diatas sudah terpenuhi, saatnya kita menginstall Hugo.

Ikuti langkah-langkah berikut:
- Buka terminal kalian dengan mengklik tombol ```CTRL+ALT+T``` berbarengan.
- Ketik perintah berikut ```snap install hugo```.
- Jika sudah selesai, pastikan kalian dapat menjalankan perintah Hugo dengan mengetik perintah ```hugo version```.
- Jika terjadi galat, coba tutup terminal saat ini dan buka terminal di jendela baru lalu ketikkan perintah diatas.
- Jika masih belum bisa, coba _restart_ komputer kalian. Ulangi cara instalasi diatas jika masih terjadi galat.

---
SELESAI.

Sampai disini telah selesai cara instalasi Hugo untuk versi Ubuntu 20.04 :beers::clap:

Jangan lupa untuk baca dokumentasi resmi dari Hugo ya :wink:

Untuk membuat projek Hugo baru, instalasi Tema, dan Konfigurasi Dasar Hugo ada di artikel selanjutnya. :fire:

Semoga bermanfaat...