# LabMobile7_Fadhila-Galih-Maheswara_ShiftD
Praktikum Pemrograman Mobile - Tugas 7 (Pertemuan 8)

# Cara Kerja Login pada Ionic
1. Membuat Login Form (LoginPage): Pengguna memasukkan username dan password dalam formulir login yang memicu fungsi login(). Fungsi ini akan mengambil data dari dua input username dan password.
2. Mengirim Data ke Backend (AuthenticationService): Fungsi login() pada LoginPage memanggil fungsi postMethod() di AuthenticationService, yang mengirimkan data username dan password ke endpoint backend (login.php). Jika respons dari backend memiliki status_login bernilai "berhasil", maka login berhasil.
3. Menyimpan Data Autentikasi: Setelah berhasil, token dan username disimpan menggunakan fungsi saveData() dari AuthenticationService. Data ini disimpan dalam Preferences dengan kunci TOKEN_KEY untuk token dan USER_KEY untuk nama pengguna. Data ini juga diperbarui pada variabel token dan nama di dalam service, dan status autentikasi diubah menjadi true menggunakan isAuthenticated.next(true).
4. Memuat Data Autentikasi Saat Aplikasi Dimulai: Ketika aplikasi dimulai, loadData() dijalankan untuk memeriksa apakah token dan username telah disimpan sebelumnya. Jika ditemukan, pengguna dianggap telah login, dan status autentikasi diperbarui menjadi true.
5. Mengelola Status Autentikasi dengan Guards:
   a. authGuard: Guard ini mencegah pengguna yang belum login untuk mengakses halaman home. Jika pengguna belum login, mereka akan diarahkan ke halaman login.
   b. autoLoginGuard: Guard ini memeriksa apakah pengguna sudah login ketika mencoba mengakses halaman login. Jika sudah login, pengguna akan diarahkan langsung ke halaman home, sehingga tidak perlu login kembali.
7. Logout: Fungsi logout() menghapus data token dan nama pengguna dari Preferences dan mengubah status autentikasi menjadi false, mengeluarkan pengguna dari aplikasi.

# Screenshot
<div style="display: flex; justify-content: space-between;">
  <img src="src/assets/SS/Screenshot 2024-10-24 212755.png" width="19%">
</div>
