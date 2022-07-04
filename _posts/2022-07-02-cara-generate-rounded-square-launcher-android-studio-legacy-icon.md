---
title: "Solved: Cara Generate Rounded Square Launcher Android Studio Legacy Icon"
date: 2022-07-02
category: [ Software ]
tags: [ system ]
image: /assets/images/generate-rounded-square-launcher-android-studio.png
---
Beberapa hari lalu saya mencoba membuat aplikasi sederhana di <a href="https://developer.android.com/studio" style="color:#007bff;">android studio</a> dengan panduan video tutorial. Karena kurang jeli dalam melihat fitur-fitur yang ada di android studio, saya mencari cukup lama tentang icon launcher ketika di install hasilnya selalu versi lama (legacy icon). Di beberapa forum atau situs web menyarankan untuk menggunakan tool online, tetapi hal tersebut saya pikir bukan solusi yang saya cari. Karena saya bisa membuatnya sendiri di <a href="https://inkscape.org" style="color:#007bff;">inkscape</a>.<br/>
<br/>
Saya coba perhatikan lebih teliti lagi, mungkin ada fitur yang saya lewatkan. Dan benar saja, fitur tersebut tersedia di dalamnya. Untuk mengeditnya tidak perlu merubah icon launcher yang sudah dipasang. Karena ini langkah tambahan dimana projek aplikasi yang sudah ada ketika di intall hasil icon launchernya versi lama (legacy icon).<br/>
<br/>
<i style="color:#888;">"Catatan: Ini hanya panduan tambahan, mengenai tutorial cara pasang icon launcher dari awal bisa lihat video youtube."</i><br/>
<br/>
Langkahnya buka projek aplikasi yang sudah dibuat, dimana ketika di install icon launchernya versi lama (legacy icon). Kemudian pilih klik kanan pada <i style="color:#888;">app</i> pilih <i style="color:#888;">New</i> cari dan pilih <i style="color:#888;">Image Asset</i>. Kurang lebihnya seperti pada tampilan gambar di bawah ini.<br/>
<br/>
<img class="img-post" src="{{site.baseurl}}/assets/images/app-new-image-asset-android-studio.jpg"><br/>
<br/>
Setelah itu akan terbuka tampilan <i style="color:#888;">Configure Image Asset</i>, di sini tidak akan upload ulang gambar icon. Melainkan pilih tab <i style="color:#888;">Options</i> dan pada menu ceklis <i style="color:#888;">Generate</i> yang semula <i style="color:#888;">Yes</i> ganti menjadi <i style="color:#888;">No</i>. Kemudian untuk menyimpan hasilnya pilih <i style="color:#888;">Next</i> dan <i style="color:#888;">Finish</i>. Tampilannya kurang lebih seperti gambar di bawah ini.<br/>
<br/>
<img class="img-post" src="{{site.baseurl}}/assets/images/configure-image-asset-android-studio.png"><br/>
<br/>
<i style="color:#888;">Informasi tambahan:</i> Dari tampilan yang ada di menu Options, dapat diketahui bahwa untuk munculkan generate launcher terbaru secara otomatis (Rounded Square) harus menggunakan minimum SDK di API 25: Android 7.1.1 (Nougat) pada projek yang dibuat. Karena saya membuat projek pada minimum SDK di API 21: Android 5.0 (Lollipop) maka hasilnya generate launcher yang muncul adalah versi "Legacy Icon (API ≤ 25)". Pengaturan tersebut bisa disesuaikan dengan kebutuhan.
