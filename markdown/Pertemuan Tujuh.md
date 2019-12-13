# Pertemuan Tujuh: Pemrosesan File Text

![Process](img/process.jpg)

## Outline

- [Pemrosesan Text](#pemrosesan-text--text-processing)
- [Cat (Concatenate)](#cat-(concatenate))
- [More dan Less](#more-dan-less)
- [Head dan Tail](#head-dan-tail)
- [Wc (Word Count)](#wc-(word-count))
- [Cut](#cut)
- [Sort](#sort)
- [Tr (Translate)](#tr-(translate))
- [Sed (Stream Editor)](#sed-(stream-editor))
- [Grep (Global Regular Expression Print)](#grep-(global-regular-expression-print))
- [Find](#find)
- [Challenge](#challenge)

## Pemrosesan Text / Text Processing

Di dalam Linux terdapat banyak perintah yang dapat digunakan untuk memanipulasi text (Text Processing).

## Cat (Concatenate)

#### Teori

Cat (Concatenate) adalah perintah untuk membuat, menambah, menampilkan isi file teks sederhana.

Sintaks: `cat [OPTION] [FILE]`.

Keterangan:

- OPTION:
  - `-n` : menampilkan nomor baris
  - `-v` : menampilkan non-printing character
- FILE: nama file teks.

#### Praktikum

Buat file latihan dan tambahkan kalimat "Belajar Pemrosesan Text":

- `cat > latihan`
- "Belajar Pemrosesan Text"
- Untuk keluar tekan: `CTRL + D`

Baca file latihan:

- `cat latihan`

Tambah isi file latihan dengan kalimat "Belajat Pemrosesan Text":

- `cat >> latihan`
- "Belajat Pemrosesan Text"
- Untuk keluar tekan: `CTRL + D`

**Note:**

Standard output linux:

- `>` : overwrite (menimpa)
- `>>` : append (digabung)

## More dan Less

#### Teori

More dan Less digunakan untuk membaca file teks berhenti per layar.

Sintaks: `more [FILE]` atau `less [FILE]`.

#### Praktikum

Membaca file /etc/passwd dengan cat:

- `cat /etc/passwd`

Membaca file /etc/passwd dengan more:

- `more /etc/passwd`

Membaca file /etc/passwd dengan less:

- `less /etc/passwd`

Menampilkan isi direktori lalu digabung dengan more:

- `ls -l /etc | more`

## Head dan Tail

#### Teori

**Head**

Head digunakan untuk menampilkan bagian awal dari suatu file.

Sintaks: `head [OPTION] [FILE]`.

Keterangan:

- OPTION:
  - `-c n`: menampilkan n karakter pertama
  - `-n n`: menampilkan n baris pertama (defalt 10)
- FILE: nama file teks

**Tail**

Tail digunakan untuk menampilkan bagian akhir dari suatu file.

Sintaks: `tail [OPTION] [FILE]`.

Keterangan:

- OPTION:
  - `-c n`: menampilkan n karakter terakhir
  - `-n n`: menampilkan n baris terakhir.
  - `-n +n`: menampilkan mulai dari baris n sampai akhir.
- FILE: nama file teks.

#### Praktikum

Menampilkan bagian awal dari file /etc/passwd:

- `head /etc/passwd`

Menampilkan bagian akhir dari file /etc/passwd:

- `tail /etc/passwd`

Menampilkan 5 baris pertama dari file /etc/passwd:

- `head -n5 /etc/passwd`

Menampikan 5 baris terakhir dari file /etc/passwd:

- `tail -n5 /etc/passwd`

Menampilkan dari baris 5 sampai terakhir:

- `tail -n+5 /etc/passwd`

## Wc (Word Count)

#### Teori

Perintah wc digunakan untuk menghitung jumlah baris, kata, dan karakter pada suatu file.

Sintaks: wc [OPTION] [FILE]

Keterangan:

- OPTION:
  - `-l` : line/baris
  - `-w` : word/kata
  - `-c` : character/karakter
- FILE: nama file teks.

#### Praktikum

Menampilkan jumlah baris, kata, dan karakter dari file /etc/passwd:

- `wc /etc/passwd`

Menampilkan jumlah baris dari file /etc/passwd:

- `wc -l /etc/passwd`

Menampilkan jumlah kata dari file /etc/passwd:

- `wc -w /etc/passwd`

Menampilkan jumlah karakter dari file /etc/passwd:

- `wc -c /etc/passwd`

## Cut

#### Teori

Perintah cut digunakan untuk menampilkan bagian baris sesuai kriteria tertentu.

Sintaks: `cut [OPTION] [FILE]`.

Keterangan:

- OPTION:
  - `-c` : berdasarkan karakter
  - `-f` : berdasarkan field atau kolom
  - `-d` : karakter yang digunakan sebagai pemisah antar kolom
- FILE: nama file teks.

#### Praktikum

Menampilkan karakter 1-4 dari file /etc/passwd:

- `cut -c1-4 /etc/passwd`

Menampilkan karakter 1 dan 4 dari file /etc/passwd:

- `cut -c1,4 /etc/passwd`

Menampilkan kolom 1-3 dari file /etc/passwd:

- `cut -f1-3 -d":" /etc/passwd`

Menampilkan kolom 1 dan 3 dari file /etc/passwd:

- `cut -f1,3 -d":" /etc/passwd`

## Sort

#### Teori

Perintah sort digunakan untuk mengurutkan isi file.

Sintaks: sort [OPTION] [FILE]

Keterangan:

- OPTION:
  - `-t` : karakter yang digunakan sebagai pemisah antar kolom.
  - `-k` : mengurutkan berdasarkan kolom tertentu.
  - `-n` : menggunakan nilai numerk.
  - `-r` : mengurutkan secara desceding (besar ke kecil).
- FILE: nama file teks.

#### Praktikum

Mengurutkan file /etc/passwd:

- `sort /etc/passwd`

Mengurukan file /etc/passwd secara descending:

- `sort -r /etc/passwd`

Mengurutkan berdasarkan kolom 3:

- `sort -k3 -t":" /etc/passwd`
- `sort -k3 -t":" -n /etc/passwd`

## Tr (Translate)

#### Teori

Perintah tr digunakan untuk mengubah atau mengkonversi karakter ke karakter lainnya.

Sintaks: `tr [OPTION] kar1 kar2`.

Keterangan:

- OPTION:
  - `-d` : delete, menghapus karakter pada kar1
- kar1: karakter yang akan dikonversi.
- kar2: karakter hasil konversi.

#### Praktikum

Mengubah huruf abc menjadi ABC:

- `tr abc ABC < /etc/passwd`

Mengubah a-z menjadi A-Z:

- `tr a-z A-Z < /etc/passwd`

Menghapus karakter aiueo:

- `tr -d aiueo < /etc/passwd`

## Sed (Stream Editor)

#### Teori

Perintah sed digunakan untuk melakukan pengeditan file teks dari baris perintah.

Sintaks: `sed [OPTION] [FILE]`.

Keterangan:

- OPTION:
  - `-e script` : skrip yang akan dieksekusi.
  - `-f script-file` : file berisi skrip yang akan dieksekusi.
- FILE: nama file teks.

#### Praktikum

Mengganti kata root menjadi badu pada file /etc/passwd:

- `sed -e "s/root/badu/" /etc/passwd`
- `sed "s/root/badu/" /etc/passwd`

Mengganti semua kata root menjadi badu:

- `sed -e "s/root/badu/g" /etc/passwd`

## Grep (Global Regular Expression Print)

#### Teori

Perintah grep digunakan untuk menampilkan baris yang mengandung pola yang dicari.

Sintaks: `grep [OPTION] [PATTERN] [FILE]`.

Keterangan:

- OPTION:
  - `-i` atau `--ignore-case` : mengabaikan huruf kecil/kecil.
  - `-v` atau `--invert-match` : menampilkan baris yang tidak mengandung pola dicari.
- PATTERN: pola yang dicari.
- FILE: nama file teks.

#### Praktikum

Mencari kata root pada file /etc/passwd:

- `grep root /etc/passwd`

Mencari kata dari hasil suatu perintah (ls):

- `ls --help | grep '\-l'`

## Find

#### Teori

Perintah find digunakan untuk mencari file dalam struktur direktori.

Sintaks: `find [PATH] [EXPRESSION]`.

Keterangan:

- PATH: direktori awal pencarian [default current directory].
- EXPRESSION:
  - `-name`: berdasarkan nama file.
  - `-user`: berdasarkan pemilik file.
  - `-perm`: berdasarkan hak akses file.
  - `-type`: berdasarkan tipe file.
  - `-exec`: eksekusi perintah shell.

#### Praktikum

Buat file latih, latihan, latihan-ku di Desktop:

- touch latih, latihan, latihan-ku

Mencari file latih di Desktop:

- `find . -name latih`

Mencari file latih yang berakhiran apapun:

- `find . -name latih*`

## Challenge

#### Ketentuan Challenge

- Challenge no 1-5 harus menggunakan Screenshot.
- Challenge dikumpulkan di Elen.

#### Challenge

1. Jalankan perintah `whoami`, `hostname`, dan `date` secara bersamaan.
2. Tuliskan perintah menampilkan baris 20 - 25 pada file /etc/passwd.
   - Gunakan gabungan dari perintah `head` dan `tail`.
3. Tuliskan perintah menghitung jumlah user yang login
   - Gunakan perintah `who` untuk mengecek user.
4. Dari perintah `who`, tuliskan perintah untuk menampilkan hanya kolom pertama (user).
   - Gunakan perintah `cut`
5. Dari perintah `date`, tuliskan perintah untuk menampilkan hanya bagian jam dan menit.