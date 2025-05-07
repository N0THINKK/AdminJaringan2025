# Rangkuman Materi Email

## 1. Protokol Mail (SMTP, POP3, IMAP, POP3S)

### SMTP (Simple Mail Transfer Protocol)

- Digunakan untuk **mengirim** email dari klien ke server atau antar server.
- Tidak bisa menerima email.
- Port default: 25 (tanpa enkripsi), 587 (TLS), 465 (SSL).

### POP3 (Post Office Protocol v3)

- Digunakan untuk **mengambil** email dari server ke klien.
- Email biasanya di-_download_ lalu dihapus dari server.
- Port default: 110 (non-enkripsi), 995 (SSL → POP3S).
- Cocok untuk penggunaan offline/satu perangkat.

### IMAP (Internet Message Access Protocol)

- Digunakan untuk **mengakses** email yang tersimpan di server.
- Mendukung sinkronisasi antar perangkat.
- Port default: 143 (non-enkripsi), 993 (SSL).
- Cocok untuk penggunaan multi-perangkat dan online.

### POP3S

- Versi aman dari POP3 yang menggunakan SSL.
- Port default: 995.

---

## 2. Informasi Mail Server dalam Sebuah Domain

- Mail server ditentukan oleh **MX Record (Mail Exchange Record)** dalam DNS.
- MX record menunjukkan server mana yang bertugas menerima email untuk domain tertentu.
- MX record memiliki **prioritas** untuk failover (cadangan server jika utama gagal).
- Contoh:
  ```bash
  dig MX example.com
  ```
- MX biasanya menunjuk ke hostname yang terhubung dengan **A record** (alamat IP) atau **CNAME**.

---

## 3. Introduction to Electronic Mail (GeeksforGeeks)

### Pengertian Email

- Email adalah metode pengiriman pesan digital antar pengguna melalui jaringan komputer, terutama internet.

### Komponen Sistem Email

| Komponen                  | Fungsi                                                                    |
| ------------------------- | ------------------------------------------------------------------------- |
| Email Address             | Alamat unik untuk mengirim/menerima email, format: `user@domain.com`.     |
| MUA (Mail User Agent)     | Aplikasi untuk membaca, menulis, mengirim email (contoh: Gmail, Outlook). |
| MTA (Mail Transfer Agent) | Server untuk memproses dan mengirim email antar server.                   |
| MDA (Mail Delivery Agent) | Komponen yang menyimpan email ke inbox penerima.                          |
| Mail Server               | Server tempat email dikirim dan diterima.                                 |

### Alur Pengiriman Email

1. Pengguna menulis email via MUA.
2. Email dikirim ke MTA menggunakan **SMTP**.
3. MTA mencari server penerima via **MX Record**.
4. MDA menyimpan email ke inbox penerima.
5. Penerima mengambil email menggunakan **POP3** atau **IMAP**.

### Kelebihan Email

- Cepat, murah, bisa dilampiri file, global.

### Kekurangan Email

- Rawan spam, virus, masalah keamanan, butuh internet.

### Istilah Umum

- **To / Cc / Bcc**: Alamat penerima utama, salinan, salinan tersembunyi.
- **Inbox / Outbox / Sent / Trash**: Folder pengelola email.
- **Attachment**: File yang dilampirkan.

---
