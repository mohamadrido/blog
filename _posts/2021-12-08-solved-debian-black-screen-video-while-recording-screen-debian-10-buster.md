---
title: "Solved Debian: Black Screen Video While Recording Screen Debian 10 Buster"
date: 2021-12-08
category: [ Software ]
tags: [ system ]
image: /assets/images/solved-debian-black-screen-video-while-recording-screen-debian-10-buster.jpg
---
Pada awal install debian 10 buster banyak sekali hal yang saya tidak tahu. Termasuk bagaimana cara rekam layar yang sering saya lakukan untuk membuat video tutorial pada operating system sebelumnya (ubuntu studio). Karena setiap rekam layar di debian 10 buster hasil videonya selalu menampilkan kursor mouse dengan background warna hitam (black screen). Akhirnya saya sering rekam layar dari tails os dengan install aplikasi kazam.<br/>
<br/>
Beberapa hari lalu saya coba install semua aplikasi rekam layar yang ada dari Software center, mulai dari Kazam, vokoscreen, SimpleScreenRecorder, Deepin Screen Recorder. Saya coba semuanya dan hasilnya tetap black screen. Setelah menelusuri di internet, saya menemukan video di youtube yang mengarah ke <a href="https://forum.level1techs.com/t/screen-recorder-for-wayland/112195/21">forum.level1techs.com</a>. Dan Ternyata caranya cukup mudah yaitu menghapus tanda # yang di bagian WaylandEnable pada file "<i>/etc/gdm3/daemon.conf</i>".<br/>
<br/>
<img class="img-post" src="{{site.baseurl}}/assets/images/wayland-enable.jpg"><br/>
<br/>
Kali ini saya menggunakan nautilus untuk mengedit "<i>/etc/gdm3/daemon.conf</i>", buka Terminal dan ketik urutan di bawah ini untuk masuk mode superuser:<br/>
<br/>
su<br/>
password:<br/>
cd<br/>
nautilus<br/>
<br />
Setelah folder nautilus terbuka, dari Filesystem root masuk dan cari file /etc/gdm3/daemon.conf kemudian klik kanan pilih Open With TextEditor. Selanjutnya carilah kode seperti di bawah ini:<br/>
<br/>
#WaylandEnable=false<br/>
<br/>
Silahkan hapus tanda # yang ada di depan WaylandEnable=false, kemudian klik Save dan Restart.
