# PulauTerbang

PulauTerbang adalah widget desktop kecil untuk Windows. Panelnya muncul dari tepi atas layar dan menyediakan kontrol musik serta alat bantu harian tanpa perlu berpindah jendela.

## Fitur

- **Kontrol musik** — membaca pemutar media Windows, menampilkan sampul, judul, artis, posisi lagu, dan menyediakan tombol putar/jeda, berikutnya, sebelumnya, dan pencarian posisi.
- **Volume sistem** — penggeser ringkas untuk mengatur volume perangkat audio aktif.
- **Lirik** — menampilkan lirik tersinkron jika tersedia dari LRCLIB. Permintaan lirik mengirim judul, artis, dan durasi lagu.
- **Warna sampul** — menyesuaikan aksen panel dengan sampul lagu; pilihan tema juga tersedia lewat menu ikon tray.
- **Mode Always On dan Standby** — Always On menjaga notch tetap terlihat. Standby menyelipkannya ke tepi atas setelah 8 detik tanpa aktivitas; arahkan kursor ke pegangan untuk membuka kembali.
- **Fokus** — timer fokus dan istirahat dengan kontrol mulai, jeda, reset, dan ganti mode.
- **Catatan minum** — mencatat konsumsi air harian dan mengingatkan untuk minum.
- **Shelf** — menyimpan pintasan file atau folder yang diseret ke panel.
- **Tugas** — daftar tugas dengan tanggal dan kalender.
- **Status perangkat** — pemberitahuan saat daya, jaringan, atau perangkat audio berubah.

## Cara memasang

PulauTerbang berjalan di Windows dan memerlukan **.NET 8 Desktop Runtime x64**.

1. Pasang .NET 8 Desktop Runtime x64 jika belum tersedia.
2. Unduh atau clone repositori ini, lalu buka terminal di folder proyek.
3. Jalankan perintah berikut untuk membuat aplikasi:

   ```powershell
   dotnet publish PulauTerbang.csproj -c Release -r win-x64 --self-contained false -p:UseAppHost=true -o publish
   ```

4. Jalankan `publish\PulauTerbang.exe`. Simpan seluruh isi folder `publish` bersama-sama.
5. Untuk mengatur agar aplikasi mulai bersama Windows, klik kanan ikon PulauTerbang di system tray.

## Cara menggunakan

- Arahkan kursor ke notch di tengah tepi atas layar untuk membuka panel; jauhkan kursor untuk menutupnya.
- Pilih halaman Musik, Fokus, Air, Shelf, Tugas, atau Pengaturan dari ikon navigasi di bagian atas panel.
- Di Pengaturan, pilih **Always On** atau **Standby** sesuai kebutuhan.
- Klik kanan ikon system tray untuk memilih tema warna, mengatur startup, atau keluar dari aplikasi.

## Alasan dibuat

PulauTerbang dibuat untuk menaruh kontrol musik dan alat bantu sederhana di satu panel kecil yang mudah dijangkau. Tujuannya mengurangi perpindahan tab saat bekerja, sambil menyediakan mode Standby supaya panel tidak terus menutupi bagian atas jendela lain.

## Data dan privasi

Pengaturan, tugas, catatan air, dan daftar Shelf disimpan lokal di `%APPDATA%\Pulau\data.json`. Saat meminta lirik, aplikasi mengirim judul, artis, dan durasi lagu ke LRCLIB. Aplikasi tidak mengirim daftar tugas atau data lokal lainnya.

## Pengembangan

Proyek memakai WPF dan Windows Forms pada .NET 8. Untuk membangun dari sumber:

```powershell
dotnet restore PulauTerbang.csproj
dotnet build PulauTerbang.csproj -c Release
```
