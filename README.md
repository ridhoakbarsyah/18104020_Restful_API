# 18104020_Restful_API

Step #1. Design EndPoint RESTful API Ini penting! Sebelum membuat RESTful API, ada baiknya di kita deznisikan dulu EndPoint dari RESTful API yang akan dibuat. EndPoint merupakan routes dari API yang akan kita buat. RESTful API menggunakan HTTP verbs (https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods). HTTP verbs yang umum digunakan adalah GET, POST, PUT, dan DELETE. GET untuk mendapatkan data dari server atau lebih dikenal dengan istilah READ,
POST untuk meng-CREATE new data, PUT untuk UPDATE data, dan DELETE untuk menghapus data. Atau lebih dikenal dengan istilah CRUD (Create-Read-Update-Delete)

Pada tutorial kali ini, saya akan sharing bagaimana membuat RESTful API sederhana untuk mengambil data dari server (GET), membuat data baru ke server (POST), mengupdate data ke server (PUT), dan menghapus data ke server (DELETE) dari suatu table di database yaitu table product

Step #2. Buat Database dan Table Buat sebuah database baru dengan MySQL, Anda dapat menggunakan tools seperti SQLyog, PHPMyAdmin atau sejenisnya. Disini saya membuat database dengan nama restful_db. Jika Anda membuat database dengan nama yang sama itu lebih baik.


Step #3. Instalasi CodeIgniter 4

Download zle Codeigniter 4 pada link berikut: https://codeigniter.com (https://codeigniter.com) Kemudian extract di web server Anda

Jika Anda menggunakan XAMPP, extract di folder:
C:\xampp\htdocs

Pada tutorial ini, saya menggunakan XAMPP. Kemudian rename (ganti nama) menjadi “restfulapi”

Kemudian open project restful api dengan code editor, disini saya menggunakan Sublime Text 3

Step #4. Membuat koneksi ke database Buka zle “Database.php” yang terdapat pada folder “app/Conzg”, kemudian ubah kode menjadi:

public $default = [
 'DSN' => '',
 'hostname' => 'localhost',
 'username' => 'root',
 'password' => '',
 'database' => 'restful_db',
 'DBDriver' => 'MySQLi',
 'DBPrefix' => '',
 'pConnect' => false,
 'DBDebug' => (ENVIRONMENT !== 'production'),
 'cacheOn' => false,
 'cacheDir' => '',
 'charset' => 'utf8',
 'DBCollat' => 'utf8_general_ci',
 'swapPre' => '',
 'encrypt' => false,
 'compress' => false,
 'strictOn' => false,
 'failover' => [],
 'port' => 3306,
];

Selanjutnya, Ini penting! Agar Anda memiliki interface yang baik untuk menangani error, temukan zle env pada
root project, kemudian rename (ganti nama) menjadi .env dan open zle tersebut. Kemudian ubah kode  menjadi:


CI_ENVIRONMENT = development

Step #5. Membuat file Model Buat sebuah zle model bernama “ProductModel.php” pada folder “app/Models”, 
 
CodeIgniter 4 telah memberikan kemudahan bagi web developer dalam membuat RESTful API. Dapat dilihat pada controller Products.php diatas, dengan hanya mengextends ResourceController (http://codeigniter.com/user_guide/incoming/restful.html) kita telah dapat membuat RESTful API. Tidak hanya itu, Kita juga bisa dengan mudah membuat response dengan menggunakan API
ResponseTrait (http://codeigniter.com/user_guide/outgoing/api_responses.html). Step #7. Konfigurasi Routes.php Langkah terakhir yang tidak kalah pentingnya yaitu melakukan sedikit konzgurasi pada zle Routes.php yang terdapat pada folder “app/Conzg”. Buka zle “Routes.php” pada folder “app/Conzg”, kemudian temukan kode berikut:

Step #8. Aktifkan CORS (Cross-Origin Resources Sharing) Ini penting! Agar resources dapat diakses di luar domain, kita perlu mengaktifkan CORS. Untuk menaktifkan CORS, buat zle bernama “Cors.php” pada folder “app/Filters”.


Step #9. Testing Untuk menguji coba API yang telah kita buat, ada banyak tools yang dapat digunakan. Pada tutorial ini, saya menggunakan POSTMAN. Saya juga menyarankan Anda untuk menggunakan POSTMAN.
Anda dapat mendownload POSTMAN di website resminya: https://www.getpostman.com/ (https://www.getpostman.com/) Download dan Install POSTMAN di komputer Anda kemudian open. Jalankan project dengan mengetikkan perintah berikut pada Terminal / Command
Prompt:
