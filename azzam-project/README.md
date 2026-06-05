Fetch API
Fetch API itu adalah fungsi bawaan JavaScript yang gunanya buat mengambil data dari internet (API/Server) secara asynchronous (jalan di latar belakang tanpa bikin web kita nge-lag atau freeze).

Di Project Ini: Kita pakai Fetch API di dalam file App.jsx buat nembak ke URL https://jsonplaceholder.typicode.com/users. Data mentah berformat JSON dari sana diambil, diubah jadi array, lalu dipakai buat nampilin daftar profil user otomatis di halaman web.

Component dan fungsinya
Biar struktur kodingan gak numpuk jadi satu file gajah, aplikasi Instazam ini dibagi menjadi beberapa komponen kecil:

main.jsx: Gerbang utama tempat aplikasi React kita pertama kali dinyalain dan ditempelin ke HTML (#root).

App.jsx: Komponen induk (bos besar) yang ngatur susunan tata letak halaman (Navbar, Main Content, Footer), sekaligus nge-filter nama user pas kita ngetik di kolom search.

Navbar.jsx: Komponen navigasi di bagian atas halaman. Fungsinya buat nampilin nama aplikasi kita ("Instazam") sekaligus memunculkan angka Total Likes App yang sinkron dari seluruh kartu user.

UserCard.jsx: Komponen kartu profil untuk masing-masing user. Isinya ada nama, username, email, tombol Like, dan tombol Follow.

Footer.jsx: Komponen catatan kaki di bagian paling bawah web buat nampilin teks info hak cipta tugas PAS 2026.

useState : Hook yang digunakan untuk membuat State.
const [users, setUsers] = useState([]); -> menyimpan data semua user dari Fetch API.
const [search, setSearch] = useState(""); -> menyimpan hasil teks yang user ketik di pencarian.
const [likes, setLikes] = useState(0); -> menghitung jumlah like dari masing masing user.
useEffect : Untuk mengatur fungsi fetch data user agar hanya berjalan satu kali saja saat aplikasi baru dibuka di browser.

useContext : Untuk memerintah tombol di dalam UserCard agar langsung menambah hitungan total likes.

useRef : Berfungsi untuk ketika web selesai dimuat, kursor keyboard otomatis aktif dan berkedip. Agar user bisa langsung mengetik tanpa harus mengklik kotak input terlebih dahulu.