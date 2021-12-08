---
title: "Solved Debian: Black Screen Video While Recording Screen Debian 10 Buster"
date: 2021-12-08
category: [ Software ]
tags: [ system ]
image: /assets/images/solved-debian-black-screen-video-while-recording-screen-debian-10-buster.jpg
---
Pada awal install debian 10 buster banyak sekali hal yang saya tidak tahu. Termasuk bagaimana cara rekam layar yang sering saya lakukan untuk membuat video tutorial pada operating system sebelumnya (ubuntu studio). Karena setiap rekam layar di debian 10 buster hasil videonya selalu menampilkan kursor mouse dengan background warna hitam (black screen). Akhirnya saya sering rekam layar dengan install aplikasi kazam dari tails os.<br/>
<br/>
Beberapa hari lalu saya coba install semua aplikasi rekam layar yang ada dari Software center, mulai dari Kazam, vokoscreen, SimpleScreenRecorder, Deepin Screen Recorder. Saya coba semuanya dan hasilnya tetap black screen. Setelah menelusuri di internet, saya menemukan video di youtube yang mengarah ke <a href="https://forum.level1techs.com/t/screen-recorder-for-wayland/112195/21">forum.level1techs.com</a>. Dan Ternyata caranya cukup mudah yaitu menghapus tanda # yang di bagian WaylandEnable pada file "<i>/etc/gdm3/daemon.conf</i>", bisa dilihat pada gambar di bawah ini.<br/>
<br/>
<img class="img-post" src="{{site.baseurl}}/assets/images/wayland-enable.jpg"><br/>
<br/>
Kali ini saya menggunakan nautilus untuk mengedit "<i>/etc/gdm3/daemon.conf</i>", buka Terminal dan ketik urutan di bawah ini untuk masuk mode superuser:<br/>
<br/>
su<br/>
password:<br/>
cd
nautilus<br/>
<br />
Setelah folder nautilus terbuka, dari Filesystem root masuk dan cari file /etc/gdm3/daemon.conf kemudian klik kanan pilih Open With TextEditor. Sebagai panduan, hasil di dalamnya kurang lebih seperti di bawah ini:<br/>
<i>
# GDM configuration storage<br/>
#<br/>
# See /usr/share/gdm/gdm.schemas for a list of available options.<br/>
<br/>
[daemon]<br/>
# Uncomment the line below to force the login screen to use Xorg<br/>
<span style="color:red;">#</span>WaylandEnable=false<br/>
<br/>
# Enabling automatic login<br/>
#  AutomaticLoginEnable = true<br/>
#  AutomaticLogin = user1<br/>
<br/>
# Enabling timed login<br/>
#  TimedLoginEnable = true<br/>
#  TimedLogin = user1<br/>
#  TimedLoginDelay = 10<br/>
<br/>
[security]<br/>
<br/>
[xdmcp]<br/>
<br/>
[chooser]<br/>
<br/>
[debug]<br/>
# Uncomment the line below to turn on debugging<br/>
# More verbose logs<br/>
# Additionally lets the X server dump core if it crashes
#Enable=true<br/>
</i>
<br/>
Silahkan hapus tanda # yang berwarna merah, kemudian klik Save dan Restart.
