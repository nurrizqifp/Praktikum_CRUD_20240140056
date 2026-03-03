<img width="1852" height="979" alt="image" src="https://github.com/user-attachments/assets/3eacb3e2-28b8-4d8a-8897-86918b6727e1" />

# Praktikum CRUD 20240140056 - Nur Rizqi Febriansyah Putra

## Deskripsi Proyek

Aplikasi ini merupakan implementasi sederhana operasi **CRUD (Create, Read, Update, Delete)** menggunakan **Spring Boot**. Proyek ini dibuat untuk memenuhi kebutuhan praktikum pada mata kuliah Deployment Perangkat Lunak.

Aplikasi memungkinkan pengguna untuk:

* Menambahkan data
* Melihat daftar data
* Mengubah data
* Menghapus data

---

## [Tools] Teknologi yang Digunakan

* Java 25
* Spring Boot
* Spring Data JPA
* Spring Validation
* Spring WebMVC
* MySQL
* Maven
* Lombok
* MapStruct

---

## [Structure] Struktur Proyek

```
Praktikum_CRUD_20240140056
│
├── .mvn/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── (package aplikasi)
│   │   │       ├── controller/
│   │   │       ├── model/
│   │   │       ├── repository/
│   │   │       └── service/
│   │   └── resources/
│   │       ├── application.properties
│   │       └── templates/
│
├── pom.xml
└── README.md
```

---

## [Config] Konfigurasi Database

Buat database terlebih dahulu, misalnya:

```sql
USE spring;

CREATE TABLE users (
    id VARCHAR(255) NOT NULL,
    name VARCHAR(255) NOT NULL,
    age INT NOT NULL,
    PRIMARY KEY (id)
) ENGINE=InnoDB;
```

Kemudian sesuaikan konfigurasi pada file:

```
src/main/resources/application.properties
```

Contoh konfigurasi:

```
spring.application.name=praktikum1
spring.jpa.hibernate.ddl.auto = update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect

spring.datasource.url = ${DATABASE_URL}
spring.datasource.username = ${DATABASE_USERNAME}
spring.datasource.password = ${DATABASE_PASSWORD}
spring.datasource.driver-class-name = com.mysql.cj.jdbc.Driver

spring.config.import = file:.env[.properties]
```

---

## » Cara Menjalankan Aplikasi

### 1️⃣ Clone Repository

```bash
git clone https://github.com/nurrizqifp/Praktikum_CRUD_20240140056.git
cd Praktikum_CRUD_20240140056
```

### 2️⃣ Build Project

```bash
mvn clean install
```

### 3️⃣ Jalankan Aplikasi

```bash
mvn spring-boot:run
```

Aplikasi akan berjalan di:

```
http://localhost:8080
```

---

## * Contoh Endpoint (Jika REST API)

| Method | Endpoint    | Fungsi                  |
| ------ | ----------- | ----------------------- |
| GET    | /items      | Menampilkan semua data  |
| GET    | /items/{id} | Menampilkan detail data |
| POST   | /items      | Menambahkan data        |
| PUT    | /items/{id} | Mengubah data           |
| DELETE | /items/{id} | Menghapus data          |

---

## [Build] Build Tool

Project ini menggunakan **Maven** sebagai dependency management dan build automation.

Untuk menjalankan unit test:

```bash
mvn test
```

---

## [Notes] Catatan

* Pastikan MySQL sudah berjalan sebelum aplikasi dijalankan.
* Pastikan port 8080 tidak digunakan oleh aplikasi lain.
* Import project sebagai Maven Project jika menggunakan IntelliJ IDEA atau Eclipse.

---
