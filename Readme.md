# Golang RESTful API with Gin & GORM

Ini adalah project sederhana RESTful API menggunakan bahasa pemrograman **Go (Golang)** dengan framework **Gin** dan ORM **GORM**. Project ini menyediakan fungsi CRUD (Create, Read, Update, Delete) untuk entitas `Post`.

## 🛠️ Tech Stack

* **Language:** Go (Golang)
* **Web Framework:** [Gin](https://github.com/gin-gonic/gin)
* **ORM:** [GORM](https://gorm.io/)
* **Database:** MySQL
* **Validation:** Go Playground Validator

## 📋 Prasyarat

Sebelum menjalankan project ini, pastikan kamu sudah menginstall:

1.  [Go](https://go.dev/dl/) (versi terbaru disarankan)
2.  [MySQL Server](https://dev.mysql.com/downloads/mysql/)

## 🚀 Cara Menjalankan

### 1. Clone Repository

```bash
git clone https://github.com/muhammadkusuma/golang-restful-api.git
cd golang-restful-api
```


### 2. Konfigurasi Database

1. Buat database baru di MySQL bernama `db_go_api`:
```sql
CREATE DATABASE db_go_api;
```


2. Buka file `models/setup.go` dan sesuaikan konfigurasi database (username, password, host) dengan environment kamu:
```go
// Format: user:password@tcp(host:port)/dbname
gorm.Open(mysql.Open("root:password_kamu@tcp(127.0.0.1:3306)/db_go_api"), &gorm.Config{})
```



### 3. Install Dependencies

Download semua library yang dibutuhkan:

```bash
go mod tidy
```

### 4. Jalankan Server

Jalankan aplikasi dengan perintah:

```bash
go run main.go
```

Server akan berjalan di `http://localhost:3000`.

## 🔌 API Endpoints

Berikut adalah daftar endpoint yang tersedia:

| Method | Endpoint | Deskripsi |
| --- | --- | --- |
| GET | `/` | Cek status server |
| GET | `/api/posts` | Mengambil semua data |
| POST | `/api/posts` | Membuat data baru |
| GET | `/api/posts/:id` | Mengambil detail data |
| PUT | `/api/posts/:id` | Mengupdate data |
| DELETE | `/api/posts/:id` | Menghapus data |

## 🧪 Contoh Penggunaan (Testing)

Kamu bisa menggunakan Postman atau **cURL** di terminal untuk mengetes API.

### 1. Create Post (POST)

```bash
curl -X POST http://localhost:3000/api/posts \
  -H "Content-Type: application/json" \
  -d '{"title": "Belajar Golang", "content": "Membuat REST API dengan Gin"}'
```

### 2. Get All Posts (GET)

```bash
curl http://localhost:3000/api/posts
```

### 3. Get Single Post (GET)

```bash
curl http://localhost:3000/api/posts/1
```

### 4. Update Post (PUT)

```bash
curl -X PUT http://localhost:3000/api/posts/1 \
  -H "Content-Type: application/json" \
  -d '{"title": "Belajar Golang [Updated]", "content": "Update konten materi"}'
```

### 5. Delete Post (DELETE)

```bash
curl -X DELETE http://localhost:3000/api/posts/1
```

## 📂 Struktur Folder

```
├── controllers
│   └── postsController.go  # Logic handler untuk setiap request
├── models
│   ├── post.go             # Struct/Schema database
│   └── setup.go            # Konfigurasi koneksi database
├── main.go                 # Entry point & definisi routing
├── go.mod                  # Dependencies management
└── README.md               # Dokumentasi project

```

## 📝 Catatan

Project ini dibuat sebagai bahan pembelajaran RESTful API menggunakan Golang. Referensi kode berdasarkan tutorial dari SantriKoding.
