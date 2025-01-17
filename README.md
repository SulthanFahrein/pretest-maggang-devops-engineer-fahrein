# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

JAWABAN
1. Apa yang anda ketahui tentang DevOps?
DevOps adalah pendekatan dalam pengembangan perangkat lunak yang menggabungkan pengembangan (Development) dan operasi (Operations) untuk meningkatkan kolaborasi, pengiriman perangkat lunak yang lebih cepat, dan kualitas yang lebih baik. Tujuannya adalah mengotomatiskan proses, mengurangi hambatan antara tim pengembang dan operasi, serta mendorong pengiriman yang lebih sering melalui praktik Continuous Integration (CI) dan Continuous Deployment (CD).

2. Apa yang anda ketahui tentang Infrastructure?
Infrastruktur merujuk pada seluruh perangkat keras, perangkat lunak, dan layanan yang mendukung operasional suatu sistem atau aplikasi. Ini meliputi komponen seperti server, jaringan, database, dan lingkungan lainnya yang diperlukan untuk menjalankan suatu aplikasi.

3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
Server adalah komputer yang menyediakan layanan atau sumber daya kepada komputer lainnya melalui jaringan. Contohnya adalah web server yang menyajikan halaman web kepada pengguna (misalnya, Apache atau Nginx), atau server basis data yang menyimpan dan mengelola data (misalnya, MySQL atau PostgreSQL).

4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
Server diperlukan dalam pengembangan perangkat lunak untuk menguji, mengelola, dan menyediakan lingkungan tempat aplikasi berjalan. Tim pengembang dapat menguji perangkat lunak mereka di lingkungan yang serupa dengan produksi, mengidentifikasi masalah, dan memastikan kinerja yang baik sebelum perilisan ke pengguna akhir.

5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
Virtualisasi adalah teknologi yang memungkinkan beberapa sistem operasi dan aplikasi berjalan pada satu fisik server. Container adalah teknologi virtualisasi yang lebih ringan, memungkinkan isolasi aplikasi dengan menggunakan bagian yang sama dari sistem operasi yang di-host.

6. Mengapa teknology container saat ini sangat populer?
Teknologi kontainer populer karena efisiensi dan portabilitasnya. Kontainer membungkus aplikasi dan dependensinya, memastikan konsistensi dalam berbagai lingkungan, seperti pengembangan, pengujian, dan produksi. Ini memungkinkan pengiriman yang konsisten dan cepat.

7. Apa yang anda ketahui tentang Orchestration Container System?
Orkestrasi kontainer adalah pengelolaan otomatisasi dan penjadwalan kontainer yang kompleks. Contohnya adalah Kubernetes, yang memungkinkan pengelolaan skala besar dan otomatisasi operasi seperti penyebaran, penskalaan, pemulihan, dan manajemen sumber daya.
   
Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

