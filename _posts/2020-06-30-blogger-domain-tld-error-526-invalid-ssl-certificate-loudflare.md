---
title: "Blogger Domain TLD Error 526 Invalid SSL Certificate CloudFlare"
date: 2020-06-30
category: [ Internet ]
tags: [ website ]
image: assets/images/security.jpg
---
Sebagai pengguna blogger dengan custom domain TLD tentu sudah tidak asing lagi dengan SSL atau fitur tambahan "<i>https</i>" yang semula fitur tersebut hanya untuk subdomain blogspot saja. Meskipun sudah mendapat fitur SSL untuk custom domain TLD, sebagian blogger menggunakan tambahan layanan dari CloudFlare. Hal ini dilakukan untuk menyembunyikan informasi nameserver dari registrar di mana mereka menyewa domain, karena tidak sekaligus membeli proteksi ID domain. Selain itu yang jadi perhatian yaitu adanya fitur <i>Firewall</i> untuk block sumber trafik web spam yang sangat menggangu. Tapi untuk saat ini saya tidak akan membahas hal tersebut, melainkan fitur SSL CloudFlare mengalami "<i>Error 526 Invalid SSL Certificate</i>" pada blogger dengan domain TLD. <br />
<br />
Artikel ini saya ketik berdasarkan pengalaman saya ketika melihat trafik yang tidak seperti biasanya (<i>trafik nol</i>) pada salah satu dasbor blogger yang saya kelola, kemudian saya coba buka langsung untuk memastikan dan benar adanya notifikasi dari CloudFlare tentang "<i>Error 526 Invalid SSL Certificate</i>". Langkah pertama yang saya lakukan yaitu login ke akun cloudflare kemudian saya hapus sementara "<i>Remove Site from Cloudflare</i>" keterkaitan blog dengan cloudflare dan merubah name server ke default di registrar tempat saya menyewa domain. Setelah menunggu beberapa menit proses pointing ternyata blog belum ada perubahan dan terdapat notifikasi masalah pada SSL. Kemudian di bagian dasbor blogger, saya nonaktifkan fitur ketersediaan https pada tab pengaturan. Blog bisa diakses kembali tanpa adanya <i>https</i>, tapi beberapa kali saya aktifkan lagi fitur ketersediaan https yang ada di dasbor blogger masih belum bisa dan selalu muncul notifikasi "<i>Anda belum diizinkan untuk menggunakan domain ini. Harap ikuti petunjuk setelannya.</i>" yang membuat saya memilih untuk menghapus semua settingan "<i>DNS Zone Manager</i>" pada registrar tempat saya menyewa domain dan mengaitkan ulang seperti pertama kali membeli domain ke blogger. Setelah beberapa menit menunggu proses pointing, saya kembali mengaktifkan fitur ketersediaan https pada dasbor blogger dan berhasil. Selanjutnya saya langsung mengaitkan dengan cloudflare.
<br />
<br />
<i>Bersambung...</i>
