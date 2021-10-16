---
title: "Debian: [FAILED] Failed to start Raise network interfaces. See 'systemctl status networking.service' for details"
date: 2021-10-16
category: [ Software ]
tags: [ system ]
image: /assets/images/debian-failed-to-start-raise-network-interfaces-see-systemctl-networking-service-for-details.jpg
---
Sebelum tampilan login di debian muncul, setelah install biasanya saya melihat ada loading screen dan terdapat pesan <i>[FAILED] Failed to start Raise network interfaces. See 'systemctl status networking.service' for details</i>. Dalam beberapa waktu saya abaikan karena semua berfungsi dengan normal. Tetapi semakin penasaran bagaimana cara mengatasi hal tersebut. Setelah mencari akhirnya saya menemukannya di forum <a style="color: #008eff;" href="https://askubuntu.com/questions/824376/failed-to-start-raise-network-interfaces-after-upgrading-to-16-04">askubuntu.com</a> yang sudah diposting beberapa tahun lalu.<br />
<br />
Dari sumber tersebut, langkah yang saya ambil untuk mengatasi pada debian 10 buster yang saya gunakan yaitu, buka <i>Terminal</i> sebagai super-user dengan ketik <i>su</i> kemudian masukan password, ketik <i>cd</i> enter dan ketik <i>nautilus</i>. Setelah terbuka folder, masuk ke system. Ubah isi file <i>/etc/network/interfaces.d/setup</i> dari:<br />
<br />
<i>
auto lo<br />
iface lo inet loopback<br />
auto eth0<br />
iface eth0 inet dhcp<br />
</i>
<br />
menjadi:<br />
<br />
<i>
auto lo<br />
iface lo inet loopback<br />
allow-hotplug eth0<br />
iface eth0 inet dhcp<br />
</i>
<br />
Simpan dan restart untuk melihat hasilnya.<br />
