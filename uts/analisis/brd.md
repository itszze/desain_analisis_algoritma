# Business Requirement Document (BRD)
## Aplikasi Barang

### 1. Tujuan Aplikasi
Aplikasi ini bertujuan untuk:
- **Mengelola stok barang secara efektif**: Memudahkan pengguna dalam mengelola jumlah barang, menyimpan informasi barang, dan melacak transaksi barang.
- **Penyajian data yang jelas dan akurat**: Menampilkan data barang dengan informasi lengkap, termasuk nama barang, jumlah barang, dan harga barang.
- **Kemudahan akses dan manajemen**: Memudahkan pengguna dalam mengakses dan mengelola data barang baik secara manual maupun melalui integrasi sistem.

### 2. Skema Data
**Tabel `barangs`:**
- `id` (Primary Key): ID unik untuk masing-masing barang.
- `nama_barang` (String): Nama dari barang yang dikelola.
- `jumlah_barang` (String): Jumlah stok barang saat ini.
- `harga_barang` (String): Harga per unit barang.
- `timestamps`: Kolom yang menyimpan waktu pembuatan dan pembaruan data.

### 3. Proses Penyimpanan dan Pengambilan Data
**Model `Barang`:**
- **Fungsi `create`** digunakan untuk menambahkan data barang baru ke tabel `barangs`.
- **Fillable properties**: Atribut `nama_barang`, `jumlah_barang`, dan `harga_barang` yang memungkinkan data ini dapat diisi melalui form input atau API.
- **Relasi**: Model `Barang` dapat berelasi dengan tabel lainnya yang terkait seperti `User` atau `Kategori Barang`.

### 4. Proses Pengelolaan Data Barang
- **Tampilan Dashboard Barang**: Halaman dashboard untuk menampilkan semua data barang yang ada, termasuk informasi jumlah dan harga.
- **Pencarian dan Filter**: Pengguna dapat melakukan pencarian atau menyaring berdasarkan kategori, harga, atau jumlah barang.
- **Pengeditan Data**: Pengguna dapat mengedit informasi mengenai nama barang, jumlah barang, dan harga barang.
- **Penghapusan Data**: Fitur untuk menghapus barang dari daftar tersedia.
- **Validasi Input**: Melakukan validasi data input agar menghindari data yang salah atau tidak valid, seperti nilai negatif pada jumlah atau harga barang.

### 5. Integrasi Database
- **Penggunaan Migrations**: File migrations `2024_11_15_232301_create_barangs_table.php` menciptakan tabel `barangs` yang mencakup kolom `nama_barang`, `jumlah_barang`, dan `harga_barang`.
- **Seeder `BarangSeeder`**: Digunakan untuk menambahkan data awal ke dalam tabel `barangs` (contoh: meja dengan jumlah 5 dan harga 50.000).

### 6. Use Cases
- **Pengelolaan Barang**:
  - **Menambahkan barang baru**: User dapat menambahkan nama, jumlah, dan harga barang baru.
  - **Mengubah jumlah barang**: User dapat mengubah jumlah stok barang jika terjadi penambahan atau pengurangan.
  - **Memodifikasi informasi barang**: User dapat memperbarui informasi seperti nama atau harga barang.
  - **Menghapus barang**: User dapat menghapus barang yang tidak lagi diperlukan.
- **Menampilkan Informasi Barang**:
  - **Menampilkan semua barang**: User dapat melihat semua daftar barang yang tersedia dalam sistem.
  - **Filter dan Pencarian**: User dapat mencari barang berdasarkan nama, kategori, jumlah, dan harga.
  - **Menampilkan detail barang**: User dapat melihat detail barang termasuk jumlah dan harga.

### 7. Validasi dan Keamanan
- **Validasi Input**: Pastikan input pengguna diverifikasi dengan validasi seperti pengecekan nilai positif untuk jumlah barang dan nilai nominal yang valid untuk harga.
- **Hak Akses**: Hak akses berdasarkan peran, seperti hanya 'super_admin' yang dapat menambah, mengedit, atau menghapus data barang.

### 8. Notifikasi dan Log
- **Logging Aksi**: Setiap perubahan atau tindakan pada data barang akan dicatat dalam sistem log untuk tujuan pelacakan dan audit.
- **Pemberitahuan**: Pengguna dapat diberitahu jika stok barang hampir habis atau ada transaksi besar.

### 9. Tampilan Aplikasi
- **Halaman Dashboard Barang**: Berisi ringkasan dan daftar barang.
- **Halaman Pengelolaan Barang**: Berisi form untuk menambah, mengedit, atau menghapus barang.
- **Halaman Detail Barang**: Menampilkan informasi lebih detail tentang barang tertentu.

### 10. Kebutuhan Fitur Tambahan
- **Integrasi API**: Aplikasi dapat terintegrasi dengan API eksternal untuk memudahkan manajemen stok dari berbagai platform atau sistem lainnya.
- **Laporan Stok dan Transaksi**: Menyediakan laporan berkala tentang jumlah stok dan transaksi barang.

---

### Kesimpulan
Aplikasi ini dirancang untuk membantu manajemen stok barang secara efisien dengan fitur pengelolaan barang, validasi input, integrasi database, dan kemudahan akses data yang ditunjang dengan sistem keamanan dan logging yang baik. Proses ini bertujuan untuk mempermudah manajemen inventaris di tingkat internal, serta memungkinkan pengguna untuk mengelola data dan melakukan operasi berdasarkan kebutuhan bisnis yang berbeda.
