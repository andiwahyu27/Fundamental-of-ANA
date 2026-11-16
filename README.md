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

### 6. Menentukan Kelas atau Segmen Alamat Jaringan

#### Dasar kelas alamat IPv4

IPv4 terdiri dari 32 bit yang ditulis dalam empat oktet, misalnya `192.168.1.10`. Setiap oktet memiliki nilai 0–255.

Pada konsep **classful addressing**:

| Kelas | Oktet pertama | Default prefix | Subnet mask | Host usable |
|---|---:|---:|---|---:|
| A | 1–126 | /8 | 255.0.0.0 | 2²⁴ − 2 = 16.777.214 |
| B | 128–191 | /16 | 255.255.0.0 | 2¹⁶ − 2 = 65.534 |
| C | 192–223 | /24 | 255.255.255.0 | 2⁸ − 2 = 254 |

Alamat `127.0.0.0/8` digunakan untuk loopback, sedangkan `224.0.0.0` sampai `239.255.255.255` digunakan untuk multicast.

Saat ini, jaringan modern lebih banyak menggunakan **CIDR** dan subnetting daripada pembagian kelas secara kaku.

#### Pengertian prefix

Prefix menunjukkan jumlah bit yang digunakan untuk bagian network.

Contoh:

```text
192.168.1.0/24
```

Artinya:

- 24 bit pertama adalah network bit.
- 8 bit sisanya adalah host bit.
- Subnet mask-nya adalah `255.255.255.0`.
- Jumlah alamat total adalah `2⁸ = 256`.
- Host usable umumnya `256 − 2 = 254`.

Dua alamat yang tidak digunakan untuk host biasa adalah:

- **Network address:** alamat pertama.
- **Broadcast address:** alamat terakhir.

Rumus umum:

```text
Jumlah bit host (h) = 32 - prefix
Jumlah alamat total = 2^h
Jumlah host usable = 2^h - 2
```

Pengecualian khusus berlaku pada beberapa subnet point-to-point, misalnya /31, dan jaringan satu host, misalnya /32.

#### Cara menghitung kebutuhan prefix

1. Tentukan jumlah host yang dibutuhkan.
2. Tambahkan ruang pertumbuhan jika diperlukan.
3. Cari jumlah bit host dengan rumus `2^h - 2 >= kebutuhan host`.
4. Hitung prefix dengan rumus `prefix = 32 - h`.
5. Tentukan subnet mask, network address, broadcast address, dan rentang host.

Contoh kebutuhan **50 host**:

```text
2^5 - 2 = 30      belum cukup
2^6 - 2 = 62      cukup
h = 6
prefix = 32 - 6 = /26
```

Maka subnet yang sesuai adalah `/26` atau `255.255.255.192`.

### Tabel Prefix /30 sampai /24

| Prefix | Subnet mask | Bit host | Total alamat | Host usable | Block size | Contoh penggunaan |
|---:|---|---:|---:|---:|---:|---|
| /30 | 255.255.255.252 | 2 | 4 | 2 | 4 | Link point-to-point |
| /29 | 255.255.255.248 | 3 | 8 | 6 | 8 | Jaringan sangat kecil |
| /28 | 255.255.255.240 | 4 | 16 | 14 | 16 | Lab/perangkat kecil |
| /27 | 255.255.255.224 | 5 | 32 | 30 | 32 | Ruang kerja kecil |
| /26 | 255.255.255.192 | 6 | 64 | 62 | 64 | Hingga 62 perangkat |
| /25 | 255.255.255.128 | 7 | 128 | 126 | 128 | Hingga 126 perangkat |
| /24 | 255.255.255.0 | 8 | 256 | 254 | 256 | Jaringan LAN umum |

#### Penjelasan setiap prefix

- **/30:** memiliki 2 bit host. Total 4 alamat, tetapi hanya 2 alamat usable. Contoh: network `192.168.1.0`, host `.1–.2`, broadcast `.3`.
- **/29:** memiliki 3 bit host. Total 8 alamat dan 6 host usable. Cocok untuk segmen kecil atau beberapa perangkat.
- **/28:** memiliki 4 bit host. Total 16 alamat dan 14 host usable.
- **/27:** memiliki 5 bit host. Total 32 alamat dan 30 host usable.
- **/26:** memiliki 6 bit host. Total 64 alamat dan 62 host usable. Cocok untuk kebutuhan hingga 50 host.
- **/25:** memiliki 7 bit host. Total 128 alamat dan 126 host usable. Cocok untuk kebutuhan hingga 100–120 host.
- **/24:** memiliki 8 bit host. Total 256 alamat dan 254 host usable. Umum digunakan pada jaringan `192.168.x.0/24`.

#### Block size

Block size membantu menentukan batas antar-subnet:

```text
Block size = 256 - nilai subnet mask pada oktet yang berubah
```

Contoh prefix `/26`:

```text
Subnet mask = 255.255.255.192
Block size  = 256 - 192 = 64
```

Maka subnet pada oktet terakhir dimulai dari:

```text
0, 64, 128, 192
```

#### Contoh perhitungan /26

Misalkan alamat yang digunakan adalah `192.168.10.70/26`.

1. Block size = `256 − 192 = 64`.
2. Rentang subnet yang tersedia: 0–63, 64–127, 128–191, 192–255.
3. Angka 70 berada pada rentang 64–127.
4. Network address = `192.168.10.64`.
5. Broadcast address = `192.168.10.127`.
6. Host usable = `192.168.10.65` sampai `192.168.10.126`.
7. Jumlah host usable = 62.

#### Contoh perhitungan /30

Misalkan jaringan point-to-point menggunakan `10.0.0.4/30`.

| Komponen | Alamat |
|---|---|
| Network address | 10.0.0.4 |
| Host usable pertama | 10.0.0.5 |
| Host usable kedua | 10.0.0.6 |
| Broadcast address | 10.0.0.7 |

Subnet ini hanya menyediakan dua alamat host sehingga cocok untuk koneksi langsung antara dua perangkat jaringan.

#### Memilih skema pengalamatan

- **Jaringan kecil:** gunakan satu segmen seperti `192.168.1.0/24`, atau subnet yang lebih kecil agar alamat tidak terbuang.
- **Jaringan menengah:** gunakan beberapa subnet berdasarkan divisi, lantai, fungsi, atau VLAN.
- **Jaringan besar/kompleks:** gunakan CIDR, VLSM, dan perencanaan hierarkis.
- **Jaringan point-to-point:** gunakan /30 atau pertimbangkan /31 jika perangkat dan desain jaringan mendukungnya.

Subnetting dapat menghemat alamat IP, mengurangi broadcast, meningkatkan keamanan, dan mempermudah pengelolaan jaringan.

## Referensi

- Materi pelatihan pada LMS Digital Talent Scholarship/Komdigi.
- Dokumentasi resmi Windows Networking.
- Dokumentasi resmi Ubuntu Server dan Netplan.
- Dokumentasi resmi Apple macOS User Guide.
- Dokumentasi Nmap dan Wireshark.

---

Catatan ini akan diperbarui seiring materi pelatihan dipelajari.
