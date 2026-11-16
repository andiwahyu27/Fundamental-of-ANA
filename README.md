# Fundamental of Associate Network Administrator - Nasional

Catatan pembelajaran pelatihan **Fundamental of Associate Network Administrator - Nasional**.

## Tujuan Pembelajaran

- Memahami konsep dasar jaringan komputer.
- Mengidentifikasi sistem operasi dan perangkat jaringan.
- Merancang pengalamatan IPv4 dan subnetting.
- Mengonfigurasi jaringan pada Windows, Linux, dan macOS.
- Memahami perangkat serta protokol jaringan.
- Menguji konektivitas dan melakukan troubleshooting.
- Mendokumentasikan hasil konfigurasi jaringan.

## Daftar Materi

| No. | Materi | Status |
|---:|---|:---:|
| 1 | Merancang pengalamatan jaringan | ⏳ |
| 2 | Mengidentifikasi sistem operasi yang berjalan di jaringan | ✅ |
| 3 | Mengumpulkan informasi instalasi dan konfigurasi jaringan pada sistem operasi | ✅ |
| 4 | Menentukan jumlah node/host jaringan berdasarkan kebutuhan pengguna | ⏳ |
| 5 | Menentukan perangkat jaringan yang sesuai | ⏳ |
| 6 | Menentukan protokol jaringan | ⏳ |
| 7 | Mengonfigurasi jaringan | ⏳ |
| 8 | Menguji konektivitas jaringan | ⏳ |
| 9 | Melakukan troubleshooting jaringan | ⏳ |
| 10 | Mendokumentasikan konfigurasi jaringan | ⏳ |

## Catatan Materi

### 1. Identifikasi Sistem Operasi pada Jaringan

Sistem operasi mengelola sumber daya perangkat keras dan perangkat lunak. Dalam jaringan, sistem operasi menyediakan layanan serta antarmuka agar perangkat dapat berkomunikasi.

Identifikasi sistem operasi penting untuk:

- memastikan kompatibilitas protokol;
- memahami fitur keamanan seperti firewall;
- memperkirakan kebutuhan sumber daya;
- menentukan metode konfigurasi yang tepat.

#### Metode pasif

Metode pasif dilakukan dengan mengamati lalu lintas jaringan tanpa berinteraksi langsung dengan perangkat target.

Contoh:

- analisis paket menggunakan Wireshark;
- pengamatan pola lalu lintas, ukuran jendela TCP, dan TTL;
- fingerprinting HTTP melalui header layanan web.

#### Metode aktif

Metode aktif dilakukan dengan mengirimkan paket tertentu ke perangkat target dan menganalisis responsnya.

Contoh:

- Nmap untuk mendeteksi sistem operasi;
- pemindaian port;
- analisis layanan yang terbuka, seperti TCP 3389 yang sering digunakan RDP pada Windows.

> Pemindaian aktif hanya boleh dilakukan pada jaringan atau perangkat yang telah memperoleh izin.

### 2. Informasi yang Dibutuhkan untuk Konfigurasi

Sebelum melakukan konfigurasi, kumpulkan:

- sistem operasi dan versinya;
- nama serta jenis interface jaringan;
- IP address;
- subnet mask atau prefix;
- default gateway;
- DNS server;
- metode pengalamatan DHCP atau statis;
- VLAN atau segmen jaringan;
- kebutuhan akses jaringan lokal dan internet.

### 3. Konfigurasi pada Sistem Operasi

#### Windows

Langkah umum melalui GUI:

1. Buka **Control Panel**.
2. Pilih **Network and Sharing Center**.
3. Pilih **Change adapter settings**.
4. Klik kanan Ethernet atau Wi-Fi → **Properties**.
5. Pilih **Internet Protocol Version 4 (TCP/IPv4)**.
6. Atur IP address, subnet mask, gateway, dan DNS.

Perintah pemeriksaan:

```powershell
ipconfig
ipconfig /all
ping 8.8.8.8
tracert example.com
nslookup example.com
```

#### Linux Debian/Ubuntu

Konfigurasi dapat dilakukan melalui GUI atau CLI. Versi modern Ubuntu umumnya menggunakan Netplan.

Contoh parameter alamat statis:

```text
IP Address : 192.168.1.10
Prefix     : /24
Gateway    : 192.168.1.1
DNS        : 8.8.8.8
```

Perintah pemeriksaan:

```bash
ip addr
ip route
ping -c 4 8.8.8.8
traceroute example.com
dig example.com
```

#### macOS

Langkah umum:

1. Buka **System Settings**.
2. Pilih **Network**.
3. Pilih interface Ethernet atau Wi-Fi.
4. Buka **Details**.
5. Atur TCP/IP dan DNS.

Perintah pemeriksaan:

```bash
ifconfig
netstat -rn
ping -c 4 8.8.8.8
traceroute example.com
nslookup example.com
```

## Praktik yang Disarankan

- Membuat topologi sederhana menggunakan Cisco Packet Tracer.
- Mengonfigurasi jaringan dengan DHCP.
- Mengonfigurasi alamat IP statis.
- Menguji konektivitas menggunakan ping.
- Mengamati jalur paket menggunakan traceroute/tracert.
- Menganalisis paket dasar dengan Wireshark.
- Membuat tabel dokumentasi perangkat dan alamat IP.
- Membandingkan konfigurasi Windows, Linux, dan macOS.

## Perintah Jaringan Penting

| Kebutuhan | Windows | Linux/macOS |
|---|---|---|
| Melihat alamat IP | `ipconfig` | `ip addr` / `ifconfig` |
| Melihat rute | `route print` | `ip route` / `netstat -rn` |
| Menguji koneksi | `ping` | `ping` |
| Melihat jalur paket | `tracert` | `traceroute` |
| Menguji DNS | `nslookup` | `dig` / `nslookup` |
| Melihat koneksi aktif | `netstat -ano` | `ss` / `netstat` |

## Format Dokumentasi Konfigurasi

| Perangkat | Sistem Operasi | Interface | IP Address | Prefix/Mask | Gateway | DNS | Metode |
|---|---|---|---|---|---|---|---|
| PC-01 | Windows | Ethernet | - | - | - | - | DHCP/Statis |
| Server-01 | Ubuntu | ens33 | - | - | - | - | DHCP/Statis |

## Referensi

- Materi pelatihan pada LMS Digital Talent Scholarship/Komdigi.
- Dokumentasi resmi Windows Networking.
- Dokumentasi resmi Ubuntu Server dan Netplan.
- Dokumentasi resmi Apple macOS User Guide.
- Dokumentasi Nmap dan Wireshark.

---

Catatan ini akan diperbarui seiring materi pelatihan dipelajari.
