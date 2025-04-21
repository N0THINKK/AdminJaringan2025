# Konfigurasi Bind9

## 1. Install Bind9

![alt text](image-1.png)

##

## 2. Setting Konfigurasi (untuk domain `kelompok7.com`) pada file-file berikut

### Pada `/etc/bind/named.conf`

![alt text](image-2.jpg)

---

### Pada `/etc/bind/named.conf.options`

![alt text](image-3.jpg)

---

### Pada `/etc/bind/named.conf.external-zones`

![alt text](image-4.jpg)

**Fungsi:**  
Mendefinisikan zona DNS untuk domain `com` dan zona reverse DNS.

---

### Pada `/etc/bind/kelompok7.com`

![alt text](image-5.jpg)

---

### Pada `/etc/bind/1.200.168.192.db`

![alt text](image-6.jpg)

**Fungsi:**  
Menerjemahkan alamat IP menjadi nama domain (reverse lookup).

---

## 3. Setting Resolver agar Menggunakan DNS Server Debian Student

![alt text](image-7.jpg)

## 4. Hasil

![alt text](image-8.jpg)
![alt text](image-9.jpg)

---

## 5. Setting Iptables

![alt text](image-10.jpg)

**Penjelasan:**

- Izinkan koneksi masuk ke port **53** (DNS) via:
  - TCP (`-p tcp`)
  - UDP (`-p udp`)  
    Port 53 dipakai oleh DNS, dan biasanya pakai UDP, tapi juga bisa pakai TCP untuk transfer data besar (misalnya zone transfer).

**Artinya:**  
Server ini bisa menerima permintaan DNS.

- **NAT**: Mengatur IP masquerading untuk trafik keluar lewat interface `enp0s8`.  
  Artinya: Semua trafik dari LAN (yang diforward) akan disamarkan menggunakan IP publik `enp0s8`.

**Hasil:**

![alt text](image-11.jpg)
