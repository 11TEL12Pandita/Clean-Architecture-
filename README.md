## Fitur Utama

- **Mendaftarkan user baru**
- **Login (mencatat waktu login)**
- **Mengambil profil user yang sedang login** (tanpa bisa melihat informasi user lain)
- **Logout (mencatat waktu logout)**

## Teknologi yang Digunakan

- **Golang**
- **Gin Gonic** (Framework HTTP)
- **JWT (JSON Web Token)** untuk autentikasi
- **In-Memory Database** (data disimpan dalam memori tanpa database eksternal)

## Cara Menjalankan Server

1. **Pastikan kamu sudah menginstall Golang** di komputermu.

2. Clone repository ini atau salin kode sumber ke dalam direktori lokal.

3. Buka terminal atau command prompt, lalu jalankan perintah berikut:

   ```sh
   go run cmd/main.go
   ```

4. Server akan berjalan di `http://localhost:8080`

## Menggunakan REST Client di VS Code

Agar lebih mudah dalam menguji API, kita bisa menggunakan extension **REST Client** di Visual Studio Code.

### Langkah-langkah:

1. **Install extension** REST Client di VS Code.

2. Buat file dengan ekstensi `.http` di dalam proyek, misalnya `api_test.http`.

3. Tambahkan request berikut untuk menguji API:

   ```http
   ### Register User
   POST http://localhost:8080/api/register
   Content-Type: application/json

   {
       "name": "Manu",
       "email": "manu1178@example.com"
   }

   ### Login User
   POST http://localhost:8080/api/login
   Content-Type: application/json

   {
       "email": "manu1178@example.com",
       "password": "password123"
   }

   ### Get Profile
   GET http://localhost:8080/api/profile
   Content-Type: application/json
   Authorization: Bearer <TOKEN>

   ### Logout
   POST http://localhost:8080/api/logout
   Content-Type: application/json
   Authorization: Bearer <TOKEN>
   ```

4. **Jalankan request dengan mengklik tombol "Send Request"** di atas setiap blok request di VS Code.

5. Pastikan mengganti `<TOKEN>` dengan token yang didapat setelah login.

