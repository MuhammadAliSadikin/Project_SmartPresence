# SmartPresence
PROJECT
SmartPresence
(Sistem Absensi Siswa Berbasis Web)






Muhammad Ali Sadikin
D0223332







Framework Web Based
2025

 
Role dan Fitur-fiturnya
Role	Fitur
Admin	Mengelola data siswa, mengatur pengguna, melihat statistic absensi.
Guru	Mencatat kehadiran siswa dan memperbahariu data siswa.
Orang Tua	Melihat Riwayat  kehadiran anak melalui akun mereka


Tabel-Tabel Database Beserta Field dan Tipe Datanya
1.	Tabel roles (Peran pengguna)
Nama field	Tipe data	Keterangan
Id	Integer(Primary Key)	ID unik setiap peran
Name	String	Nama peran
(admin,guru,orangtuan)

2.	Tabel users (Data pengguna)
Nama field	Tipe data	Keterangan
id	Intteger(Primary Key)	ID pengguna
name	String	Nama Pengguna
email	String(Unique)	Email untuk login
password	String	Password login
role id	Integer(Foreign Key)	Hubungan ke  table roles

3.	Tabel students (Data siswa)
Nama field	Tipe  data	Keterangan
Id	Integer(Primary Key)	ID siswa
Neme	String	Nama siswa
class	String	Kelas siswa

4.	Tabel parent_student (Hubungan Orang Tua dengan Siswa)
Nama field	Tipe data	Keterangan
id	Integer(Primary Key)	ID unik hubungan
Parent_id	Integer(Foreign Key)	ID orang tua(mengacu ke users)
Student_id	Integer(Foreign Key)	ID siswaa(mengacu ke students)
5.	Tabel attendances (Catatan Absensi)
Nama fied	Tipe data	Keterangan
Id	Integer(Primary Key)	ID unik absensi
Student_id	Integer(Foreign Key)	ID siswa yang hadir
Attendance_date	Date	Tanggal absensi
status	Enum(Hadir,Tidak Hadir)	Status kehadiran siswa


Jenis Relasi dan Tabel yang Berelasi
Relasi	Tabel yang Berelasi	Jenis
One-to-Many	roles -> users	Satu role bisa dimiliki bayak pengguna
Many-to-Many	Users -> students melalui parent_student	Satu orang tua bisa memiiki beberapa anak
One-to-Many	Students -> attendances	Satu siswa bisa memiliki banyak catatan absensi



