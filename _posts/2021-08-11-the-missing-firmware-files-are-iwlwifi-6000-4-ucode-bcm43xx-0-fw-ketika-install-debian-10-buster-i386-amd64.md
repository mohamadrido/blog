---
title: "The missing firmware files are: iwlwifi-6000-4.ucode/bcm43xx-0.fw Ketika Install Debian 10 Buster i386/amd64"
date: 2021-08-11
category: [ Software ]
tags: [ system ]
image: /assets/images/the-missing-firmware-files-are-iwlwifi-6000-4-ucode-bcm43xx-0-fw-ketika-install-debian-10-buster-i386-amd64.jpg
---
Setelah melakukan banyak pertimbangan dari beberapa distro linux, akhirnya saya memilih untuk menggunakan OS Debian 10 Buster di semua notebook 32-bit dan 64-bit pada Hardisk utamanya. Meskipun lebih sering menggunakan Tails OS untuk keperluan akses internet, pembuatan model 3D hingga rendering.<br /> 
Ketika proses install OS muncul <i>The missing firmware files are: iwlwifi-6000-4.ucode</i> di versi amd64 dan <i>The missing firmware files are: brcm/bcm43xx-0.fw</i> di versi i386. Pada tampilan pilih "No" untuk lanjut, atau intinya tetap jalankan install debian sampai selesai tanpa koneksi internet dan wifi yang tidak terdeteksi.<br />
<br />
<img class="img-post" src="{{site.baseurl}}/assets/images/img-20210810-152918.jpg"><br />
<br />
Berikut ini langkah-langkah setelah install OS sudah selesai, buka Terminal dan ketik:<br />
<br />
su<br />
cd<br />
nautilus<br />
<br />
Cari file yang berada di <i>Filesystem root</i> atau <i>Computer/etc/apt/sources.list</i> dengan klik kanan buka dengan <i>TextEditor</i>. Ganti semua isinya dengan di bawah ini dan Save:<br />
<br />
<i>deb http://deb.debian.org/debian buster main contrib non-free<br />
deb-src http://deb.debian.org/debian buster main contrib non-free<br />
<br />
deb http://deb.debian.org/debian-security/ buster/updates main contrib non-free<br />
deb-src http://deb.debian.org/debian-security/ buster/updates main contrib non-free<br />
<br />
deb http://deb.debian.org/debian buster-updates main contrib non-free<br />
deb-src http://deb.debian.org/debian buster-updates main contrib non-free<br />
<br />
deb http://deb.debian.org/debian buster-backports main contrib non-free<br />
deb-src http://deb.debian.org/debian buster-backports main contrib non-free<br /></i>
<br />
Sampai di sini pastikan terhubung dengan koneksi internet, jika tidak ada koneksi LAN/Wired Ethernet bisa menggunakan USB Tethering smartphone. Setelah terhubung ke internet buka Terminal lagi dan ketik:<br />
<br />
sudo apt update<br />
sudo apt upgrade<br />
sudo dmesg<br />
<br />
Maksud dari <i>sudo dmesg</i> untuk mengetahui firmware yang belum di install, bisanya ditandai dengan tulisan berwarna merah. Perintah ini bisa langsung di skip saja jika sudah mengetahui firmware yang akan di install. Karena saya sudah mengetahui firmware yang akan saya install jadi langsung menggunakan perintah <i>sudo apt install firmware-name</i> tanpa perlu menggunakan <i>sudo apt-cache search firmware-missingname</i> untuk memastikan nama fiermware wifi yang akan di install.<br />
<br />
Untuk instalasi di PC amd64 ketik:<br />
<br />
sudo apt-cache search firmware-iwlwifi-6000-4.ucode<br />
sudo apt install firmware-iwlwifi<br />
<br />
Untuk instalasi di PC i386 ketik:<br />
<br />
sudo apt-cache search brcm/bcm43xx-0.fw<br />
sudo apt install firmware-bcm43xx-0.fw<br />
<br />
Setelah selesai Restart komputer untuk melihat hasilnya.<br />
