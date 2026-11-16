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
| 4 | Menentukan jumlah node/host jaringan berdasarkan kebutuhan pengguna | ✅ |
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


### 4. Mengumpulkan Informasi Instalasi dan Konfigurasi Jaringan

Setelah sistem operasi yang digunakan berhasil diidentifikasi, langkah berikutnya adalah mengumpulkan informasi yang diperlukan agar instalasi dan konfigurasi jaringan dapat dilakukan dengan benar.

#### Informasi kunci

- **Protokol jaringan:** tentukan protokol yang digunakan, terutama TCP/IP sebagai standar jaringan yang paling umum.
- **Metode pengalamatan IP:** tentukan apakah perangkat menggunakan IP statis atau DHCP.
- **Subnet mask:** tentukan batas jaringan dan host pada suatu segmen jaringan.
- **Default gateway:** tentukan alamat perangkat yang meneruskan lalu lintas ke jaringan lain.
- **DNS server:** catat DNS primer dan sekunder untuk menerjemahkan nama domain menjadi alamat IP.

#### Proses konfigurasi pada Windows

1. Buka **Control Panel**.
2. Pilih **Network and Sharing Center**.
3. Pilih **Change adapter settings**.
4. Klik kanan pada interface Ethernet atau Wi-Fi, kemudian pilih **Properties**.
5. Pilih **Internet Protocol Version 4 (TCP/IPv4)**, lalu klik **Properties**.
6. Pilih salah satu metode:
   - **Obtain an IP address automatically** untuk menggunakan DHCP.
   - **Use the following IP address** untuk mengisi IP secara manual.
7. Isi IP address, subnet mask, default gateway, dan DNS server.
8. Simpan konfigurasi, kemudian lakukan pengujian konektivitas.

#### Proses konfigurasi pada Linux Debian/Ubuntu

Konfigurasi dapat dilakukan melalui GUI atau CLI.

Melalui GUI:

1. Buka **Settings**.
2. Pilih **Network**.
3. Pilih interface jaringan.
4. Masukkan konfigurasi IP, subnet mask/prefix, gateway, dan DNS.

Melalui CLI:

- Pada sistem lama, konfigurasi dapat berada di `/etc/network/interfaces`.
- Pada Ubuntu versi baru, konfigurasi umumnya menggunakan **Netplan**.
- Contoh parameter konfigurasi statis:

```text
Interface : eth0
IP Address: 192.168.1.10
Netmask   : 255.255.255.0
Gateway   : 192.168.1.1
DNS       : 8.8.8.8, 8.8.4.4
```

Contoh konfigurasi sederhana pada sistem yang menggunakan format interfaces:

```text
auto eth0
iface eth0 inet static
    address 192.168.1.10
    netmask 255.255.255.0
    gateway 192.168.1.1
    dns-nameservers 8.8.8.8 8.8.4.4
```

> Nama interface dan metode penerapan dapat berbeda tergantung distribusi serta versi Linux.

#### Proses konfigurasi pada macOS

1. Buka **System Settings**.
2. Pilih **Network**.
3. Pilih interface Ethernet atau Wi-Fi.
4. Klik **Details**.
5. Atur IP address, subnet mask, gateway, dan DNS.
6. Pilih DHCP jika alamat IP akan diperoleh otomatis.
7. Simpan pengaturan dan uji konektivitas.

#### Checklist sebelum konfigurasi

| Informasi | Nilai |
|---|---|
| Sistem operasi dan versi | - |
| Interface jaringan | - |
| IP address | - |
| Subnet mask/prefix | - |
| Default gateway | - |
| DNS primer | - |
| DNS sekunder | - |
| Metode pengalamatan | DHCP/Statis |
| Hasil pengujian koneksi | - |


### 5. Menentukan Jumlah Node/Host Jaringan

Sebelum mengalokasikan alamat IP, tentukan terlebih dahulu kebutuhan riil jaringan. **Node** adalah setiap perangkat yang terhubung ke jaringan dan membutuhkan alamat IP, seperti:

- komputer desktop;
- laptop dan smartphone;
- printer;
- server;
- router dan switch;
- perangkat IoT.

Perencanaan tidak hanya menghitung perangkat yang tersedia saat ini, tetapi juga memperkirakan pertumbuhan perangkat pada masa mendatang.

#### Tahapan perencanaan

1. **Inventarisasi perangkat saat ini**  
   Lakukan audit terhadap seluruh perangkat yang akan terhubung. Catat jenis dan jumlah perangkat, misalnya PC, laptop, server, smartphone, printer, dan perangkat IoT.

2. **Proyeksi pertumbuhan**  
   Perkirakan pertumbuhan jumlah perangkat untuk jangka waktu tertentu, misalnya 1–3 tahun. Sediakan margin keamanan sekitar **20–30%** dari kebutuhan saat ini dan proyeksi masa depan untuk mengantisipasi perangkat tambahan atau perluasan jaringan.

3. **Identifikasi kebutuhan khusus**  
   Pisahkan perangkat yang membutuhkan alamat IP statis, seperti server, router, switch terkelola, printer jaringan, access point, dan perangkat lain yang harus mudah diakses.

#### Contoh perhitungan

Misalnya sebuah jaringan memiliki:

| Jenis perangkat | Jumlah |
|---|---:|
| Komputer dan laptop | 40 |
| Printer jaringan | 4 |
| Server | 3 |
| Perangkat jaringan | 5 |
| Perangkat IoT | 8 |
| **Total saat ini** | **60** |

Jika digunakan margin keamanan 25%:

```text
Cadangan = 25% x 60 = 15 node
Kebutuhan minimum = 60 + 15 = 75 alamat IP
```

Jaringan sebaiknya dirancang untuk menampung sedikitnya **75 host**.

#### Hubungan dengan subnetting

Setelah jumlah node diketahui, pilih skema pengalamatan yang sesuai. Pada IPv4, kebutuhan host dapat dipenuhi dengan memilih prefix subnet yang tepat.

Rumus jumlah host yang dapat digunakan:

```text
Jumlah host usable = 2^h - 2
```

Keterangan:

- `h` adalah jumlah bit host.
- Pengurangan 2 digunakan untuk alamat network dan broadcast.

Contoh:

| Prefix | Total alamat | Host usable |
|---|---:|---:|
| /30 | 4 | 2 |
| /29 | 8 | 6 |
| /28 | 16 | 14 |
| /27 | 32 | 30 |
| /26 | 64 | 62 |
| /25 | 128 | 126 |
| /24 | 256 | 254 |

Untuk kebutuhan 75 host, subnet **/25** menyediakan 126 host usable sehingga masih memiliki ruang pertumbuhan.

Subnetting membantu:

- mengoptimalkan penggunaan alamat IP;
- membagi jaringan menjadi segmen yang lebih terkelola;
- meningkatkan keamanan melalui pemisahan segmen;
- mengurangi broadcast yang tidak diperlukan;
- meningkatkan kinerja jaringan.

## Referensi

- Materi pelatihan pada LMS Digital Talent Scholarship/Komdigi.
- Dokumentasi resmi Windows Networking.
- Dokumentasi resmi Ubuntu Server dan Netplan.
- Dokumentasi resmi Apple macOS User Guide.
- Dokumentasi Nmap dan Wireshark.

---

Catatan ini akan diperbarui seiring materi pelatihan dipelajari.
