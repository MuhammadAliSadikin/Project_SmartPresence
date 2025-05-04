# SmartPresence
<p align="center" style="margin-bottom: 0px;">SmartPresence</p>
<p align="center" style="margin-top: 0;">Sistem Absensi Siswa Berbasis Web</p>
<p align="center"> <img src="Logo_Proyek.png" width="300" alt="Logo SmartPresence" /> </p>

<p align="center">Muhammad Ali Sadikin</p>
<p align="center">D0223332</p></br>
<p align="center">Framework Web Based</p>
<p align="center">2025</p>
Role dan Fitur
1. Admin
Fokus: Kelola sistem & pengguna

Fitur	Deskripsi
Kelola Data Siswa	CRUD data siswa
Kelola Pengguna	Menentukan peran dan akses
Statistik Absensi	Melihat laporan kehadiran siswa
2. Guru
Fokus: Mengelola kehadiran siswa

Fitur	Deskripsi
Mencatat Kehadiran	Input status hadir atau tidak hadir
Memperbarui Data Siswa	Edit data siswa jika diperlukan
3. Orang Tua
Fokus: Memantau kehadiran anak

Fitur	Deskripsi
Lihat Riwayat Absensi	Cek kehadiran anak berdasarkan akun orang tua
Tabel-tabel database beserta field dan tipe datanya
1. Tabel {roles} (Peran Pengguna)
Field	Tipe Data	Keterangan
id	INT(PK)	Primary Key
name	VARCHAR(100)	Nama peran (admin, guru, orang tua)
2. Tabel {users} (Data Pengguna)
Field	Tipe Data	Keterangan
id	INT(PK)	Primary Key
name	VARCHAR(100)	Nama pengguna
email	VARCHAR(100)	Email unik
password	VARCHAR(255)	Password login
role_id	INT(FK)	Relasi ke {roles.id}
3. Tabel {students} (Data Siswa)
Field	Tipe Data	Keterangan
id	INT(PK)	Primary Key
name	VARCHAR(100)	Nama siswa
class	VARCHAR(50)	Kelas siswa
4. Tabel {parent_student} (Hubungan Orang Tua & Siswa)
Field	Tipe Data	Keterangan
id	INT(PK)	Primary Key
parent_id	INT(FK)	Relasi ke {users.id} (Orang Tua)
student_id	INT(FK)	Relasi ke {students.id} (Siswa)
5. Tabel {attendances} (Catatan Absensi)
Field	Tipe Data	Keterangan
id	INT(PK)	Primary Key
student_id	INT(FK)	Relasi ke {students.id}
attendance_date	DATE	Tanggal absensi
status	ENUM	'Hadir', 'Tidak Hadir'
Jenis relasi dan tabel yang berelasi
Tabel Asal	Tabel Tujuan	Jenis Relasi	Keterangan
{roles.id}	{users.role_id}	One-to-Many	Satu role bisa dimiliki banyak pengguna
{users.id}	{students.id}	Many-to-Many	Satu orang tua bisa memiliki beberapa anak
{students.id}	{attendances.student_id}	One-to-Many	Satu siswa bisa memiliki banyak catatan absensi
