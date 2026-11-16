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

### 7. NAT dan VLAN pada Jaringan /24

#### NAT

**NAT (Network Address Translation)** menerjemahkan alamat IP private menjadi alamat IP public ketika perangkat mengakses internet.

Analogi sederhananya, perangkat di dalam kantor memiliki alamat internal, sedangkan router bertindak sebagai petugas yang menggunakan satu alamat kantor saat berkomunikasi ke luar.

Contoh:

```text
PC Pegawai : 192.168.10.10
Gateway    : 192.168.10.1
IP Public Router: 203.0.113.5
```

Ketika PC mengakses internet, router mengubah sumber paket:

```text
Sebelum NAT : 192.168.10.10:52001
Sesudah NAT : 203.0.113.5:40001
```

Router menyimpan tabel penerjemahan sehingga balasan dari internet dapat dikirim kembali ke komputer yang benar.

NAT berfungsi untuk:

- memungkinkan banyak perangkat private berbagi satu IP public;
- menghemat penggunaan IP public;
- menyembunyikan struktur alamat internal;
- meneruskan balasan internet ke perangkat yang sesuai.

NAT biasanya diterapkan pada router atau firewall di batas antara jaringan internal dan internet.

#### VLAN

**VLAN (Virtual Local Area Network)** membagi satu jaringan fisik menjadi beberapa jaringan logis. Satu switch dapat digunakan untuk beberapa kelompok jaringan yang terpisah.

Contoh pembagian:

| VLAN | Fungsi | Network /24 | Gateway |
|---:|---|---|---|
| 10 | Pegawai | 192.168.10.0/24 | 192.168.10.1 |
| 20 | Tamu | 192.168.20.0/24 | 192.168.20.1 |

Dengan netmask `255.255.255.0`:

- perangkat VLAN 10 menggunakan alamat `192.168.10.x`;
- perangkat VLAN 20 menggunakan alamat `192.168.20.x`;
- masing-masing VLAN memiliki hingga 254 host usable;
- kedua VLAN merupakan jaringan yang berbeda.

Contoh perangkat:

```text
PC Andi       : 192.168.10.10/24, VLAN 10
Printer kantor: 192.168.10.20/24, VLAN 10
Laptop tamu   : 192.168.20.10/24, VLAN 20
```

PC Andi dan printer berada pada VLAN yang sama sehingga dapat berkomunikasi melalui switch. Laptop tamu berada pada VLAN berbeda dan tidak dapat langsung mengakses perangkat VLAN 10.

#### Komunikasi antar-VLAN

Agar VLAN 10 dan VLAN 20 dapat saling berkomunikasi, diperlukan **inter-VLAN routing** menggunakan router atau Layer 3 Switch.

Alurnya:

```text
PC VLAN 10
192.168.10.10
     |
Gateway VLAN 10
192.168.10.1
     |
Router/Layer 3 Switch
     |
Gateway VLAN 20
192.168.20.1
     |
Perangkat VLAN 20
192.168.20.10
```

Administrator dapat membuat aturan akses, misalnya:

- VLAN Pegawai boleh mengakses server internal.
- VLAN Tamu hanya boleh mengakses internet.
- VLAN Tamu tidak boleh mengakses komputer atau printer pegawai.

#### Access port dan trunk port

- **Access port:** port switch yang terhubung ke satu perangkat biasa dan satu VLAN, misalnya PC pada VLAN 10.
- **Trunk port:** port yang membawa beberapa VLAN sekaligus antara switch, router, atau access point. Frame biasanya diberi penanda VLAN menggunakan standar 802.1Q.

#### Perbedaan NAT dan VLAN

| Aspek | NAT | VLAN |
|---|---|---|
| Fungsi | Menerjemahkan IP private ke IP public | Memisahkan jaringan secara logis |
| Digunakan pada | Router/firewall | Switch |
| Fokus | Akses internet | Segmentasi jaringan internal |
| Contoh | 192.168.10.10 menjadi IP public router | Memisahkan jaringan pegawai dan tamu |

#### Contoh gabungan

```text
VLAN 10 Pegawai ─┐
192.168.10.0/24  ├─ Router/Firewall ─ NAT ─ Internet
VLAN 20 Tamu ────┘
192.168.20.0/24
```

VLAN mengatur pemisahan jaringan di dalam kantor, sedangkan NAT menerjemahkan alamat ketika perangkat keluar menuju internet.

### 8. Memberi Alamat Jaringan pada Node atau Perangkat

Setelah subnet ditentukan, setiap perangkat perlu mendapatkan konfigurasi jaringan. Informasi yang biasanya diberikan kepada perangkat adalah:

- IP address;
- subnet mask atau prefix;
- default gateway;
- DNS server.

Ada dua metode utama pengalamatan jaringan.

#### Pengalamatan dinamis dengan DHCP

**DHCP (Dynamic Host Configuration Protocol)** memberikan konfigurasi jaringan secara otomatis kepada perangkat.

Alurnya:

```text
Perangkat terhubung
        |
        v
Meminta konfigurasi DHCP
        |
        v
Server DHCP memberikan IP, netmask, gateway, dan DNS
```

Contoh konfigurasi yang diterima laptop:

```text
IP address : 192.168.1.51
Netmask    : 255.255.255.0 (/24)
Gateway    : 192.168.1.1
DNS        : 192.168.1.1 atau 8.8.8.8
```

Kelebihan DHCP:

- konfigurasi otomatis;
- mudah dikelola;
- mengurangi kesalahan pengetikan;
- mengurangi risiko konflik IP;
- cocok untuk laptop, smartphone, dan perangkat pengguna yang sering berpindah jaringan.

Server DHCP biasanya berada pada router, firewall, atau server khusus. Administrator menentukan **DHCP pool**, yaitu rentang alamat yang boleh dibagikan.

#### Pengalamatan statis

Pada pengalamatan statis, IP dikonfigurasi secara manual dan tidak berubah secara otomatis.

Contoh konfigurasi server:

```text
IP address : 192.168.1.10
Netmask    : 255.255.255.0 (/24)
Gateway    : 192.168.1.1
DNS        : 192.168.1.1
```

IP statis cocok untuk perangkat yang harus selalu ditemukan pada alamat yang sama, seperti:

- router dan switch terkelola;
- server;
- printer jaringan;
- access point;
- kamera IP;
- perangkat IoT tertentu.

Kekurangannya, administrator harus mencatat dan mengatur alamat secara manual. Jika dua perangkat menggunakan alamat yang sama, akan terjadi konflik IP.

#### Contoh pembagian alamat pada jaringan /24

Misalnya jaringan kantor:

```text
Network : 192.168.1.0/24
Range   : 192.168.1.1–192.168.1.254
Gateway : 192.168.1.1
Broadcast: 192.168.1.255
```

Pembagian alamat dapat dibuat seperti berikut:

| Rentang | Peruntukan |
|---|---|
| 192.168.1.1 | Gateway/router |
| 192.168.1.2–192.168.1.20 | Switch, access point, server |
| 192.168.1.21–192.168.1.50 | Printer, kamera, dan perangkat statis |
| 192.168.1.51–192.168.1.200 | DHCP untuk komputer dan perangkat pengguna |
| 192.168.1.201–192.168.1.254 | Cadangan atau perangkat tambahan |

Dengan pembagian ini, alamat statis tidak bercampur dengan pool DHCP.

#### DHCP reservation

Selain IP statis manual, administrator dapat menggunakan **DHCP reservation**. Pada metode ini, perangkat tetap memperoleh alamat melalui DHCP, tetapi server selalu memberikan IP yang sama berdasarkan MAC address perangkat.

Contoh:

```text
MAC printer : AA:BB:CC:11:22:33
IP reservation: 192.168.1.25
```

DHCP reservation menggabungkan kemudahan pengelolaan DHCP dengan alamat yang konsisten.

#### Perbandingan DHCP dan IP statis

| Aspek | DHCP | IP statis |
|---|---|---|
| Cara konfigurasi | Otomatis | Manual |
| Perubahan alamat | Dapat berubah | Tetap |
| Risiko salah konfigurasi | Lebih rendah | Lebih tinggi |
| Cocok untuk | Laptop dan smartphone | Server, router, printer |
| Dokumentasi | Pool dan lease | Setiap perangkat |
| Pengelolaan | Terpusat | Perangkat per perangkat |

#### Dokumentasi alokasi IP

Setiap IP statis sebaiknya dicatat:

| Nama perangkat | Jenis | IP address | Prefix | Gateway | Metode | Keterangan |
|---|---|---|---|---|---|---|
| R1 | Router | 192.168.1.1 | /24 | - | Statis | Gateway kantor |
| SRV-01 | Server | 192.168.1.10 | /24 | 192.168.1.1 | Statis | Server aplikasi |
| PRN-01 | Printer | 192.168.1.25 | /24 | 192.168.1.1 | Reservation | Printer lantai 1 |
| PC-001 | Komputer | 192.168.1.51 | /24 | 192.168.1.1 | DHCP | Pengguna |

> Jangan memberikan alamat network, broadcast, atau alamat yang sudah digunakan perangkat lain kepada host baru.

### 9. Membuat Dokumentasi Pengalamatan Jaringan

Dokumentasi pengalamatan jaringan adalah catatan terstruktur mengenai seluruh IP address, subnet, perangkat, dan aturan konfigurasi jaringan.

Dokumen ini sebaiknya menjadi **single source of truth**, yaitu sumber informasi utama yang digunakan ketika melakukan pemeliharaan, troubleshooting, audit, atau penambahan perangkat.

#### Komponen dokumentasi

Dokumentasi jaringan sebaiknya memuat:

1. **Informasi dasar**
   - judul dokumentasi;
   - nama proyek atau organisasi;
   - tanggal pembuatan;
   - versi dokumen;
   - nama penyusun atau penanggung jawab.

2. **Diagram topologi**
   - koneksi internet;
   - router atau firewall;
   - switch;
   - server;
   - access point;
   - VLAN atau subnet;
   - lokasi perangkat.

3. **Tabel ringkasan subnet**
   - network address dan prefix;
   - tujuan penggunaan;
   - rentang host;
   - gateway;
   - broadcast address;
   - VLAN jika ada.

4. **Tabel alokasi IP statis**
   - IP address;
   - hostname;
   - MAC address;
   - jenis perangkat;
   - lokasi;
   - keterangan.

5. **Informasi DHCP**
   - alamat server DHCP;
   - DHCP pool;
   - lease time;
   - gateway;
   - DNS;
   - daftar reservation jika digunakan.

6. **Change log**
   - tanggal perubahan;
   - uraian perubahan;
   - perangkat atau subnet yang terdampak;
   - pelaksana;
   - pihak yang menyetujui.

#### Contoh ringkasan subnet

| ID Subnet | Tujuan | Rentang host | Gateway | Broadcast | VLAN |
|---|---|---|---|---|---:|
| 192.168.10.0/24 | Jaringan pegawai | 192.168.10.1–192.168.10.254 | 192.168.10.1 | 192.168.10.255 | 10 |
| 192.168.20.0/24 | Jaringan tamu | 192.168.20.1–192.168.20.254 | 192.168.20.1 | 192.168.20.255 | 20 |

#### Contoh alokasi IP statis

| IP address | Hostname | MAC address | Perangkat | Lokasi | Keterangan |
|---|---|---|---|---|---|
| 192.168.10.1 | R1 | AA:BB:CC:00:00:01 | Router | Ruang server | Gateway utama |
| 192.168.10.2 | SW-LT1 | AA:BB:CC:00:00:02 | Switch | Lantai 1 | Switch akses |
| 192.168.10.10 | SRV-FILE | AA:BB:CC:00:00:10 | Server | Ruang server | Penyimpanan file |
| 192.168.10.20 | PRN-LT1 | AA:BB:CC:00:00:20 | Printer | Lantai 1 | Printer jaringan |

#### Contoh informasi DHCP

```text
Server DHCP : 192.168.10.1
DHCP pool   : 192.168.10.100–192.168.10.200
Lease time  : 24 jam
Gateway     : 192.168.10.1
DNS primer  : 192.168.10.1
DNS sekunder: 8.8.8.8
```

Rentang IP statis dan DHCP perlu dipisahkan agar server DHCP tidak membagikan alamat yang sudah digunakan secara manual.

#### Contoh change log

| Tanggal | Perubahan | Pelaksana | Persetujuan |
|---|---|---|---|
| 2026-11-16 | Menambahkan printer jaringan dengan IP 192.168.10.21 | Tim jaringan | Koordinator TI |
| 2026-11-17 | Mengubah DHCP pool menjadi 192.168.10.100–192.168.10.200 | Tim jaringan | Koordinator TI |

#### Praktik dokumentasi yang baik

- Gunakan format penamaan perangkat yang konsisten.
- Catat tanggal dan versi setiap perubahan.
- Jangan menghapus riwayat perubahan.
- Simpan diagram dan tabel pada lokasi yang dapat diakses tim terkait.
- Perbarui dokumentasi segera setelah konfigurasi berubah.
- Lindungi informasi sensitif, seperti kredensial, secret key, dan konfigurasi keamanan.
- Lakukan pencadangan dokumen secara berkala.

### 10. Menetapkan Kebutuhan Detail Perangkat Jaringan

Pemilihan perangkat jaringan harus didasarkan pada kebutuhan pengguna, beban lalu lintas, kondisi lokasi, anggaran, dan rencana pertumbuhan. Perangkat yang dipilih tidak boleh terlalu kecil sehingga cepat penuh, tetapi juga tidak boleh berlebihan sehingga memboroskan anggaran.

Analisis dilakukan dengan membandingkan:

- kebutuhan jaringan saat ini;
- proyeksi kebutuhan 3–5 tahun mendatang;
- kapasitas perangkat yang tersedia;
- kebutuhan kecepatan dan keamanan;
- kemungkinan perluasan jaringan.

#### 1. Memotret kebutuhan saat ini

Lakukan inventarisasi terhadap:

- jumlah komputer, laptop, printer, server, kamera, dan perangkat IoT;
- jumlah port switch yang sedang digunakan;
- jenis aktivitas pengguna;
- kapasitas internet saat ini;
- kecepatan switch dan interface jaringan;
- kondisi kabel dan perangkat lama;
- area yang sudah dan belum terjangkau Wi-Fi.

Jenis lalu lintas juga perlu diperhatikan. Aktivitas seperti email dan browsing biasanya lebih ringan daripada konferensi video HD, transfer file besar, penggunaan cloud, atau akses server secara bersamaan.

#### 2. Memproyeksikan kebutuhan masa depan

Gunakan prinsip **future proofing**, yaitu memilih perangkat yang masih mampu melayani pertumbuhan jaringan.

Perencanaan dapat dilakukan untuk 3–5 tahun ke depan dengan memperhatikan:

- pertambahan jumlah pegawai;
- penambahan komputer dan perangkat IoT;
- peningkatan penggunaan video conference;
- kebutuhan transfer file yang semakin besar;
- kemungkinan penambahan ruangan atau lantai.

Sediakan cadangan kapasitas sekitar 20–30%. Cadangan ini dapat diterapkan pada jumlah port, kapasitas bandwidth, kapasitas PoE, serta kemampuan perangkat.

Contoh:

```text
Perangkat saat ini : 20
Cadangan 30%       : 6
Kebutuhan minimum  : 26 perangkat
```

Walaupun kebutuhan minimum 26 port, switch 24 port tidak cukup. Pilihan yang lebih aman adalah switch 48 port, terutama jika masih harus menyediakan port untuk uplink, access point, printer, kamera, dan perangkat tambahan.

#### 3. Kecepatan perangkat

Periksa apakah kecepatan perangkat lama sesuai dengan kebutuhan.

Contoh:

| Kondisi | Evaluasi |
|---|---|
| Switch 100 Mbps | Dapat menjadi bottleneck untuk transfer file dan video |
| Switch Gigabit 1000 Mbps | Lebih sesuai untuk jaringan kantor modern |
| Internet 100 Mbps | Perangkat internal sebaiknya tetap mendukung Gigabit |
| Uplink antar-switch 1 Gbps | Perlu diperiksa terhadap jumlah pengguna dan beban trafik |

Jika komputer baru mendukung Gigabit tetapi switch hanya 100 Mbps, komunikasi tetap dibatasi oleh kemampuan switch.

> Kecepatan internet dan kecepatan jaringan lokal berbeda. Internet 100 Mbps tidak berarti switch internal harus dibatasi 100 Mbps.

#### 4. Jangkauan Wi-Fi

Jika terdapat ruangan yang tidak mendapatkan sinyal Wi-Fi dengan baik, lakukan survei lokasi dan pertimbangkan penambahan Access Point.

Penempatan AP sebaiknya:

- berada di lokasi yang relatif tengah terhadap area layanan;
- tidak terhalang dinding tebal atau benda logam;
- tidak ditempatkan terlalu dekat dengan sumber interferensi;
- mempertimbangkan jumlah pengguna dan kepadatan perangkat;
- menggunakan beberapa AP dengan perencanaan kanal yang baik jika area luas.

Penambahan AP bukan hanya soal memperbesar daya pancar. Jumlah pengguna, kapasitas AP, posisi pemasangan, interferensi, dan koneksi kabel ke AP juga perlu diperhitungkan.

#### 5. Topologi yang tidak efisien

Masalah jaringan dapat disebabkan oleh susunan perangkat, bukan hanya spesifikasi perangkat.

Contoh masalah:

- semua perangkat terhubung ke satu switch yang sudah penuh;
- ruangan jauh menggunakan kabel terlalu panjang atau tidak tertata;
- terlalu banyak perangkat menggunakan satu jalur uplink;
- tidak ada switch akses di area yang membutuhkan banyak port.

Solusi yang dapat dipertimbangkan:

- menambahkan switch akses di ruangan atau lantai yang jauh;
- menghubungkan switch tambahan ke switch utama melalui uplink;
- menata perangkat berdasarkan lantai, divisi, atau VLAN;
- membuat diagram topologi agar jalur jaringan mudah dipahami.

#### 6. Perangkat keamanan

Jaringan sebaiknya memiliki perangkat dan kebijakan keamanan yang memadai, seperti:

- **firewall** untuk menyaring lalu lintas dan melindungi jaringan dari koneksi yang tidak diizinkan;
- **router** dengan fitur keamanan dan NAT;
- **VLAN** untuk memisahkan jaringan pegawai, tamu, server, dan perangkat IoT;
- **CCTV IP** untuk pemantauan area;
- **access control** untuk membatasi akses ke perangkat dan ruang jaringan;
- pencadangan konfigurasi perangkat secara berkala.

Firewall dapat dianalogikan sebagai satpam di gerbang kantor. Firewall memeriksa lalu lintas yang masuk dan keluar berdasarkan aturan yang telah ditetapkan.

#### 7. Cara menyusun rekomendasi perangkat

Gunakan tiga langkah berikut:

1. **Identifikasi kebutuhan**  
   Tuliskan perangkat yang diperlukan, misalnya switch, router, firewall, access point, kabel, UPS, atau kamera IP.

2. **Tentukan jumlah dan spesifikasi**  
   Tentukan jumlah unit, jumlah port, kecepatan, kapasitas PoE, dukungan VLAN, uplink, dan fitur keamanan.

3. **Berikan alasan teknis**  
   Jelaskan hubungan perangkat dengan kebutuhan jaringan.

Contoh rekomendasi:

| Perangkat | Jumlah | Spesifikasi minimum | Alasan |
|---|---:|---|---|
| Switch | 1 | 48 port Gigabit, VLAN, 2 uplink | Menampung 26 perangkat dan menyediakan cadangan pertumbuhan |
| Access Point | 2 | Wi-Fi modern, mendukung banyak pengguna | Memperluas jangkauan lantai 1 dan 2 |
| Firewall | 1 | NAT, filtering, VPN, logging | Melindungi jaringan dan mengatur akses internet |
| UPS | 1 | Kapasitas sesuai beban router/switch | Menjaga perangkat aktif saat listrik padam |
| Kabel jaringan | Sesuai survei | Cat6 atau sesuai kebutuhan | Mendukung koneksi Gigabit dan instalasi yang rapi |

Pemilihan akhir tetap harus mempertimbangkan kompatibilitas, garansi, dukungan teknis, konsumsi daya, biaya pemeliharaan, serta anggaran.

### 11. Menetapkan Kapasitas Jaringan Saat Ini dan Masa yang Akan Datang

**Capacity planning** adalah proses menentukan seberapa besar kapasitas jaringan dan perangkat yang diperlukan agar layanan tetap berjalan baik saat ini maupun ketika jumlah pengguna dan perangkat bertambah.

Analogi sederhananya: jaringan seperti sistem pipa air. Data adalah air, bandwidth adalah ukuran pipa, sedangkan perangkat jaringan adalah pompa dan pembagi jalurnya. Jika pipa terlalu kecil atau pompa tidak kuat, aliran akan tersendat saat banyak keran digunakan bersamaan.

#### 1. Menghitung beban jaringan saat ini

Jangan hanya menghitung jumlah pegawai. Jaringan melayani perangkat, sehingga satu orang dapat memiliki beberapa perangkat:

- laptop atau komputer;
- smartphone;
- tablet;
- printer;
- kamera IP;
- perangkat IoT.

Contoh:

```text
50 pegawai x rata-rata 2–3 perangkat = 100–150 perangkat
```

Kelompokkan juga profil pengguna. Pengguna administrasi yang melakukan email dan pengolahan dokumen biasanya membutuhkan kapasitas berbeda dari pengguna multimedia yang mengunggah video berukuran besar atau melakukan konferensi video.

#### 2. Mengantisipasi pertumbuhan

Rencanakan kebutuhan untuk 3–5 tahun ke depan. Pertimbangkan:

- pertambahan pegawai;
- penambahan komputer dan perangkat IoT;
- peningkatan penggunaan cloud dan video conference;
- pertumbuhan ukuran file;
- penambahan ruangan atau lantai.

Gunakan cadangan kapasitas. Sebagai contoh, jika kebutuhan puncak saat ini adalah 500 Mbps dan disediakan buffer 50%:

```text
Kapasitas minimum = 500 Mbps + (50% x 500 Mbps)
                  = 750 Mbps
```

Karena perangkat umumnya tersedia dalam kelas tertentu, pilih perangkat yang mendukung minimal 1 Gbps.

> Angka pertumbuhan dan buffer adalah asumsi perencanaan. Untuk jaringan produksi, validasi dengan data monitoring, survei trafik, dan kebutuhan organisasi.

#### 3. Menentukan perangkat dan kapasitasnya

| Perangkat | Kapasitas yang diperhatikan | Contoh pertimbangan |
|---|---|---|
| Switch | Jumlah port, kecepatan, PoE, uplink, VLAN | 24 atau 48 port Gigabit |
| Router/firewall | Throughput, jumlah koneksi, NAT, VPN, fitur keamanan | Mampu menangani bandwidth internet dan koneksi bersamaan |
| Access Point | Jumlah klien, cakupan, kapasitas radio, standar Wi-Fi | Wi-Fi 6 untuk lingkungan dengan banyak perangkat |
| Kabel jaringan | Kategori, panjang, kualitas instalasi | Cat6 untuk koneksi Gigabit |
| UPS | Daya dan durasi cadangan | Melindungi router, switch, dan perangkat penting |
| Rack | Ukuran, ventilasi, dan manajemen kabel | Rack 12U untuk perangkat jaringan kecil |

#### 4. Contoh perhitungan kebutuhan switch

Jika tersedia 15 komputer, jangan memilih switch 8 port. Gunakan switch minimal 24 port agar masih tersedia ruang untuk:

- uplink;
- access point;
- printer;
- kamera IP;
- perangkat tambahan;
- pertumbuhan pengguna.

Contoh proyeksi:

```text
Perangkat saat ini       : 15
Cadangan pertumbuhan 30% : 5 (dibulatkan ke atas)
Kebutuhan perencanaan    : 20 port
```

Switch 24 port menjadi pilihan yang lebih sesuai. Jika kebutuhan sudah mencapai sekitar 26 port atau terdapat rencana ekspansi lebih besar, pertimbangkan switch 48 port.

#### 5. Kecepatan perangkat

Periksa kesesuaian kecepatan setiap komponen:

- switch 100 Mbps dapat menjadi bottleneck untuk transfer file dan video;
- switch Gigabit mendukung koneksi lokal hingga 1000 Mbps;
- perangkat internal sebaiknya tetap mendukung Gigabit meskipun internet saat ini hanya 100 Mbps;
- uplink antar-switch harus diperiksa agar tidak menjadi titik kemacetan.

Kecepatan internet dan kecepatan jaringan lokal adalah hal yang berbeda. Koneksi internet 100 Mbps tidak berarti jaringan internal harus menggunakan switch 100 Mbps.

#### 6. Jangkauan Wi-Fi dan topologi

Jika terdapat area yang tidak terjangkau Wi-Fi, lakukan survei lokasi sebelum menambah Access Point. Perhatikan dinding, benda logam, interferensi, kepadatan pengguna, posisi AP, dan koneksi kabel menuju AP.

Jika seluruh perangkat terhubung ke satu switch yang sudah penuh atau ruangan baru berada jauh dari switch utama, pertimbangkan:

- menambahkan switch akses di ruangan tersebut;
- menghubungkannya melalui uplink ke switch utama;
- menata perangkat berdasarkan lantai, divisi, atau VLAN;
- membuat diagram topologi dan label kabel.

#### 7. Menyusun daftar rekomendasi

Gunakan langkah berikut:

1. Identifikasi jenis perangkat yang diperlukan.
2. Tentukan jumlah dan spesifikasi minimumnya.
3. Tentukan lokasi pemasangan.
4. Jelaskan alasan teknis setiap perangkat.
5. Periksa kompatibilitas, garansi, dukungan teknis, konsumsi daya, biaya pemeliharaan, dan anggaran.

Contoh daftar kebutuhan:

| No. | Perangkat | Spesifikasi/kapasitas | Jumlah | Lokasi |
|---:|---|---|---:|---|
| 1 | Switch | 24-port Gigabit, VLAN, uplink | 2 unit | Ruang server dan administrasi |
| 2 | Router/firewall | Throughput sesuai bandwidth, NAT, VPN | 1 unit | Ruang server |
| 3 | Access Point | Wi-Fi 6, mendukung banyak klien | 3 unit | Ruang rapat, pantry, ruang depan |
| 4 | Kabel UTP | Cat6 | ±500 meter | Seluruh area kantor |
| 5 | Rack | 12U, ventilasi dan manajemen kabel | 1 unit | Ruang server |
| 6 | UPS | 1500 VA atau sesuai hasil perhitungan beban | 1 unit | Ruang server |

### 12. Menetapkan Kebutuhan Keamanan dan Manajemen Jaringan

Kecepatan jaringan harus diimbangi dengan keamanan dan kemudahan pengelolaan. Jaringan kantor dapat dianalogikan sebagai gedung: kapasitas adalah lebar lorong, keamanan adalah satpam dan kunci, sedangkan manajemen adalah ruang kendali yang membantu administrator memantau kondisi gedung.

#### 1. Spesifikasi keamanan

Saat memilih router, firewall, atau switch, periksa fitur keamanan berikut:

- **Firewall bawaan:** menyaring lalu lintas masuk dan keluar berdasarkan aturan. Istilah yang umum ditemukan antara lain SPI Firewall, access control, dan content filtering.
- **VPN:** menyediakan koneksi terenkripsi bagi pengguna atau kantor cabang yang mengakses jaringan dari lokasi lain.
- **Port security:** membatasi perangkat yang boleh terhubung pada port switch, misalnya berdasarkan MAC address atau jumlah MAC address.
- **VLAN dan access control:** memisahkan jaringan pegawai, tamu, server, dan perangkat IoT serta mengatur siapa yang boleh mengaksesnya.
- **Logging dan alert:** mencatat kejadian penting dan memberi peringatan ketika terdapat aktivitas yang tidak biasa.
- **Pembaruan firmware:** memastikan perangkat dapat menerima perbaikan keamanan dari produsennya.

Firewall dapat dianalogikan sebagai satpam di gerbang kantor. Firewall tidak hanya meneruskan paket, tetapi memeriksa apakah lalu lintas tersebut sesuai dengan aturan yang diizinkan.

#### 2. VPN untuk akses jarak jauh

VPN membuat koneksi aman antara pengguna atau jaringan remote dengan jaringan kantor. Data yang melewati jaringan publik dikirim melalui tunnel terenkripsi.

Contoh penggunaan:

- pegawai mengakses server kantor dari rumah;
- kantor cabang terhubung ke kantor pusat;
- administrator melakukan pemeliharaan perangkat dari lokasi lain.

VPN harus dilengkapi autentikasi yang kuat, pembatasan hak akses, dan pencatatan aktivitas. Jangan memberikan akses penuh ke seluruh jaringan jika pengguna hanya membutuhkan satu aplikasi atau server.

#### 3. Port security pada switch

Port security membantu mencegah perangkat asing terhubung sembarangan ke jaringan kabel.

Contoh kebijakan:

- satu port hanya boleh digunakan oleh satu perangkat;
- alamat MAC perangkat dicatat atau dipelajari secara otomatis;
- port dinonaktifkan atau diberi peringatan jika muncul perangkat yang tidak dikenal;
- port yang tidak digunakan dipindahkan ke VLAN yang tidak memiliki akses atau dinonaktifkan.

Port security bukan pengganti autentikasi pengguna, tetapi merupakan lapisan perlindungan tambahan.

#### 4. Perangkat managed dan unmanaged

| Jenis perangkat | Karakteristik | Cocok untuk |
|---|---|---|
| Unmanaged | Plug-and-play, tidak memiliki konfigurasi dan monitoring yang lengkap | Jaringan sangat kecil dan sederhana |
| Smart managed | Memiliki Web-GUI serta fitur dasar VLAN, monitoring, dan QoS | Kantor kecil hingga menengah |
| Managed | Dapat dikonfigurasi melalui Web-GUI atau CLI dan memiliki fitur monitoring lengkap | Jaringan profesional dan kompleks |

Switch unmanaged seperti terminal listrik: perangkat dapat langsung digunakan, tetapi administrator tidak dapat melihat atau mengatur banyak hal. Switch managed menyediakan ruang kendali untuk memantau port, VLAN, trafik, error, dan kondisi perangkat.

#### 5. Fitur manajemen yang perlu diperhatikan

Perangkat managed sebaiknya menyediakan:

- **Web-GUI** untuk konfigurasi melalui tampilan grafis;
- **CLI** untuk konfigurasi lanjutan dan otomasi;
- **monitoring trafik** untuk mengetahui sumber penggunaan bandwidth;
- **VLAN** untuk segmentasi jaringan;
- **QoS** untuk memprioritaskan layanan penting seperti video conference atau VoIP;
- **SNMP atau telemetry** untuk pemantauan terpusat;
- **backup dan restore konfigurasi**;
- **NTP dan syslog** untuk menyamakan waktu serta menyimpan log;
- **role-based access** agar setiap administrator memperoleh hak akses sesuai tugas.

#### 6. Cloud management

Cloud management memungkinkan administrator memantau dan mengelola perangkat melalui portal atau aplikasi cloud. Fitur ini bermanfaat ketika:

- perangkat berada di lokasi yang jauh;
- organisasi memiliki banyak cabang;
- administrator membutuhkan monitoring terpusat;
- konfigurasi dan notifikasi perlu dikelola dari satu dashboard.

Namun, cloud management juga perlu dievaluasi dari sisi ketergantungan internet, biaya langganan, lokasi penyimpanan data, keamanan akun, dan kemampuan perangkat untuk tetap berjalan ketika koneksi cloud terputus.

#### 7. Pendekatan Zero Trust

Zero Trust berarti tidak langsung mempercayai perangkat atau pengguna hanya karena berada di dalam jaringan kantor. Setiap akses perlu diverifikasi dan dibatasi sesuai kebutuhan.

Prinsip sederhananya:

1. verifikasi identitas pengguna dan perangkat;
2. berikan hak akses minimum;
3. pisahkan jaringan berdasarkan fungsi;
4. pantau aktivitas dan simpan log;
5. evaluasi akses secara berkala.

Contoh penerapan:

- VLAN tamu hanya boleh mengakses internet;
- VLAN pegawai boleh mengakses aplikasi internal tertentu;
- VLAN IoT tidak boleh mengakses komputer pegawai;
- administrator menggunakan akun pribadi dengan hak akses yang tercatat;
- akses VPN menggunakan autentikasi multifaktor jika tersedia.

#### 8. Checklist pemilihan keamanan dan manajemen

| Kebutuhan | Pertanyaan pemeriksaan |
|---|---|
| Firewall | Apakah perangkat dapat menyaring koneksi dan mencatat log? |
| VPN | Apakah mendukung akses remote yang terenkripsi? |
| Port security | Apakah port switch dapat membatasi perangkat asing? |
| Segmentasi | Apakah mendukung VLAN dan aturan antar-segmen? |
| Monitoring | Apakah trafik, error, dan penggunaan port dapat dipantau? |
| Konfigurasi | Apakah tersedia Web-GUI, CLI, backup, dan restore? |
| Pembaruan | Apakah firmware masih didukung produsen? |
| Akses administrator | Apakah tersedia akun, role, dan autentikasi yang aman? |
| Cloud management | Apakah manfaatnya sebanding dengan biaya dan ketergantungannya? |

Perangkat yang sedikit lebih mahal tetapi memiliki keamanan dan manajemen yang baik dapat memberikan nilai lebih besar daripada perangkat cepat yang tidak dapat dipantau atau dikendalikan.

### 13. Memilih Perangkat Wi-Fi Berdasarkan Kebutuhan Teknis

Pemilihan perangkat Wi-Fi tidak cukup berdasarkan klaim kecepatan tertinggi pada kotak produk. Perhatikan standar Wi-Fi, frekuensi, jumlah pengguna, fitur keamanan, kemampuan manajemen, dan kondisi lokasi pemasangan.

#### 1. Standar Wi-Fi

Pilih perangkat yang mendukung standar yang sesuai dengan kebutuhan. Contohnya:

- **802.11ac atau Wi-Fi 5:** masih banyak digunakan dan umumnya bekerja pada frekuensi 5 GHz.
- **802.11ax atau Wi-Fi 6:** lebih efisien pada lingkungan padat dan mampu melayani banyak perangkat dengan lebih baik.
- **Wi-Fi 6E atau Wi-Fi 7:** dapat menawarkan kapasitas dan fitur yang lebih tinggi, tetapi perlu dipastikan perangkat klien serta anggaran juga mendukung.

Standar terbaru tidak otomatis membuat semua perangkat lama menjadi lebih cepat. Kecepatan aktual dipengaruhi oleh kemampuan access point, perangkat klien, lebar kanal, jarak, interferensi, dan kualitas instalasi.

#### 2. Frekuensi 2,4 GHz dan 5 GHz

Perangkat dual-band dapat menggunakan dua pita frekuensi:

| Frekuensi | Kelebihan | Kekurangan | Contoh penggunaan |
|---|---|---|---|
| 2,4 GHz | Jangkauan lebih luas dan lebih baik menembus hambatan | Lebih banyak interferensi dan kecepatan biasanya lebih rendah | Ruangan yang lebih jauh, perangkat IoT |
| 5 GHz | Kecepatan lebih tinggi dan kanal lebih banyak | Jangkauan lebih pendek dan lebih mudah terhalang dinding | Laptop, video conference, transfer file |

Pemilihan frekuensi dapat dianalogikan seperti memilih jalan. Frekuensi 2,4 GHz adalah jalan yang lebih jauh jangkauannya, tetapi lebih ramai. Frekuensi 5 GHz adalah jalan yang lebih cepat dan lebih lengang, tetapi memiliki jangkauan lebih terbatas.

#### 3. Kapasitas pengguna dan MU-MIMO

Hitung jumlah perangkat yang akan terhubung secara bersamaan, bukan hanya jumlah pegawai. Perhatikan:

- jumlah klien aktif;
- jenis aktivitas, seperti browsing, video conference, atau transfer file;
- kapasitas radio access point;
- jumlah access point dalam satu area;
- kemungkinan pertumbuhan pengguna.

Teknologi **MU-MIMO** memungkinkan access point berkomunikasi dengan beberapa perangkat secara bersamaan. Fitur ini membantu efisiensi pada lingkungan dengan banyak klien, tetapi kinerja tetap bergantung pada dukungan perangkat klien dan kondisi radio.

#### 4. Keamanan Wi-Fi

Untuk jaringan kantor, gunakan fitur keamanan modern:

- **WPA3** jika didukung perangkat klien;
- guest network untuk tamu;
- pemisahan jaringan menggunakan VLAN;
- kata sandi yang kuat dan berbeda dari kata sandi administrator;
- pembaruan firmware;
- autentikasi pengguna untuk lingkungan yang membutuhkan kontrol lebih ketat.

Jangan menggunakan jaringan tamu yang berada pada segmen yang sama dengan server atau komputer pegawai tanpa aturan pembatasan akses.

#### 5. Antena dan gain

Pertimbangkan jenis antena dan nilai gain dalam dBi:

- **Omnidirectional:** menyebarkan sinyal ke banyak arah dan umum digunakan di dalam ruangan.
- **Directional:** memusatkan sinyal ke arah tertentu, cocok untuk menghubungkan area atau gedung tertentu.
- **Sectoral:** mencakup sektor atau sudut tertentu dan sering digunakan pada area yang lebih luas.

Antena dengan gain lebih tinggi tidak selalu lebih baik. Gain yang tinggi dapat membuat pola pancaran lebih sempit, sehingga harus disesuaikan dengan bentuk area dan posisi pemasangan.

#### 6. Contoh pemilihan pada kantor

Misalnya kantor memiliki 60 perangkat aktif yang tersebar di dua lantai:

- gunakan beberapa access point, bukan satu AP dengan daya pancar maksimum;
- pilih perangkat dual-band yang mendukung Wi-Fi 6;
- gunakan 5 GHz untuk laptop dan video conference jika jangkauan memadai;
- gunakan 2,4 GHz untuk perangkat yang jauh atau IoT;
- aktifkan WPA3 atau WPA2-AES sesuai kompatibilitas klien;
- sediakan guest network yang terpisah;
- hubungkan AP ke switch Gigabit, dan gunakan PoE jika didukung;
- lakukan survei sinyal setelah pemasangan untuk memeriksa area lemah dan interferensi.

#### 7. Checklist pemilihan access point

| Aspek | Pertanyaan pemeriksaan |
|---|---|
| Standar | Apakah mendukung Wi-Fi 6 atau standar yang sesuai kebutuhan? |
| Frekuensi | Apakah dual-band dan memiliki pengaturan kanal yang baik? |
| Kapasitas | Berapa jumlah klien aktif yang direkomendasikan? |
| Performa | Apakah mendukung MU-MIMO dan efisiensi pada lingkungan padat? |
| Keamanan | Apakah mendukung WPA3, guest network, dan VLAN? |
| Koneksi | Apakah memiliki port Gigabit dan dukungan PoE? |
| Manajemen | Apakah dapat dikelola melalui Web-GUI atau cloud? |
| Antena | Apakah pola pancaran sesuai dengan bentuk ruangan? |
| Pemeliharaan | Apakah firmware dan dukungan produsennya masih tersedia? |

Perangkat yang tepat adalah perangkat yang sesuai dengan kondisi lokasi dan kebutuhan pengguna, bukan semata-mata perangkat dengan angka kecepatan paling besar.

### 14. Memasang Perangkat Sesuai Kebutuhan Teknis

Pemasangan fisik, terutama Access Point, memengaruhi cakupan sinyal, kualitas koneksi, roaming, dan keamanan perangkat. Perangkat dengan spesifikasi tinggi tetap dapat bekerja buruk jika dipasang di lokasi yang tidak tepat.

#### 1. Menentukan posisi Access Point

Tempatkan AP:

- sedekat mungkin dengan posisi tengah area layanan;
- pada posisi yang cukup tinggi, seperti plafon atau bagian atas dinding;
- jauh dari sudut ruangan yang dikelilingi banyak dinding;
- mudah dijangkau untuk pemeliharaan, tetapi tidak mudah diakses oleh orang yang tidak berwenang;
- sesuai dengan hasil survei lokasi dan kebutuhan pengguna.

Posisi sentral dan tinggi membantu mengurangi hambatan serta membuat distribusi sinyal lebih merata.

#### 2. Menghindari hambatan dan sumber interferensi

Hindari menempatkan AP:

- di dalam lemari atau di balik benda logam;
- di belakang peralatan besar;
- di dekat dinding beton atau objek yang menghalangi sinyal;
- di dekat microwave, perangkat Bluetooth padat, atau sumber interferensi radio;
- di sudut ruangan jika area layanan berada di sisi yang berlawanan.

Benda logam, dinding tebal, dan peralatan elektronik dapat melemahkan atau memantulkan sinyal. Jika kualitas sinyal buruk, jangan langsung menaikkan daya pancar; periksa kembali posisi AP, kanal, dan kemungkinan interferensi.

#### 3. Jarak antar-AP dan roaming

Jika beberapa AP dipasang pada area yang berdekatan, sediakan overlap sinyal yang cukup agar perangkat pengguna dapat berpindah AP tanpa kehilangan koneksi. Angka 15–20% dapat digunakan sebagai gambaran awal, tetapi nilai sebenarnya harus divalidasi melalui site survey karena dipengaruhi struktur bangunan, frekuensi, daya pancar, dan jenis perangkat klien.

Untuk roaming yang baik:

- gunakan SSID dan metode keamanan yang konsisten jika jaringan memang dirancang sebagai satu layanan;
- rencanakan kanal agar AP yang berdekatan tidak saling mengganggu;
- kurangi daya pancar jika area cakupan terlalu tumpang tindih;
- gunakan fitur fast roaming jika perangkat dan jaringan mendukungnya;
- lakukan pengujian sambil berpindah lokasi.

Overlap yang terlalu kecil dapat menyebabkan dead spot. Overlap yang terlalu besar atau kanal yang sama dapat meningkatkan interferensi dan membuat klien berpindah AP secara tidak optimal.

#### 4. Sumber daya listrik dengan PoE

**PoE (Power over Ethernet)** mengirimkan daya dan data melalui satu kabel Ethernet. Dengan PoE, AP tidak memerlukan adaptor listrik terpisah di dekat lokasi pemasangan.

Komponen yang perlu diperiksa:

- switch PoE atau injector PoE;
- standar PoE yang didukung;
- kebutuhan daya setiap AP;
- total power budget switch;
- kualitas kabel dan konektor;
- panjang kabel serta jalur instalasi.

Pastikan total kebutuhan daya tidak melebihi power budget switch PoE. Jika AP membutuhkan daya lebih besar daripada kemampuan port atau injector, perangkat dapat gagal menyala atau bekerja tidak stabil.

#### 5. Kerapian dan keselamatan instalasi

- gunakan kabel Cat6 atau kategori yang sesuai kebutuhan;
- beri label pada kedua ujung kabel;
- hindari tekukan tajam dan tarikan berlebihan;
- pisahkan kabel data dari sumber listrik bertegangan tinggi jika memungkinkan;
- gunakan cable tray atau pipa pelindung;
- pastikan bracket dan baut kuat;
- dokumentasikan lokasi AP, nomor port switch, VLAN, dan jalur kabel;
- gunakan UPS untuk perangkat jaringan penting;
- lakukan instalasi listrik dan ketinggian sesuai prosedur keselamatan kerja.

#### 6. Pemeriksaan setelah pemasangan

Setelah AP dipasang, lakukan verifikasi:

1. Pastikan AP memperoleh daya dan alamat IP.
2. Periksa status koneksi pada switch.
3. Uji SSID, autentikasi, dan guest network.
4. Uji koneksi pada 2,4 GHz dan 5 GHz.
5. Ukur kekuatan sinyal di area layanan.
6. Periksa throughput dan latency pada beberapa lokasi.
7. Uji roaming dengan berpindah antar-ruangan.
8. Pastikan VLAN dan aturan akses berjalan sesuai desain.
9. Periksa log, interferensi, dan perangkat yang terhubung.
10. Simpan hasil pengujian dan perbarui dokumentasi jaringan.

Pemasangan selesai bukan ketika lampu AP menyala, melainkan ketika cakupan, kapasitas, keamanan, dan konektivitasnya telah diuji sesuai kebutuhan.

### 15. Mengonfigurasi Perangkat Nirkabel agar Terhubung ke Jaringan

Setelah perangkat dipasang secara fisik, perangkat perlu dikonfigurasi agar dapat berkomunikasi dengan router, switch, server, dan perangkat pengguna. Konfigurasi harus mengikuti desain IP address, VLAN, keamanan, dan kebutuhan layanan jaringan.

#### 1. Akses antarmuka konfigurasi

Langkah umum:

1. Hubungkan komputer ke AP menggunakan kabel Ethernet atau jaringan konfigurasi awal.
2. Cari alamat IP perangkat melalui label, manual, DHCP lease pada router, atau aplikasi vendor.
3. Buka alamat IP tersebut melalui browser.
4. Masuk menggunakan akun administrator.
5. Segera ganti username atau password default.
6. Ubah alamat manajemen AP sesuai skema jaringan dan catat pada dokumentasi.

Alamat `192.168.1.1` sering digunakan sebagai contoh alamat default, tetapi alamat sebenarnya bergantung pada produsen. Jangan mengasumsikan semua perangkat menggunakan alamat tersebut.

#### 2. Menentukan mode perangkat

| Mode | Fungsi | Kapan digunakan |
|---|---|---|
| Access Point/Bridge | Menyediakan Wi-Fi dan meneruskan koneksi ke jaringan utama | Jika router utama sudah menyediakan DHCP dan NAT |
| Router | Membuat jaringan baru dan melakukan routing/NAT | Jika perangkat menjadi gateway suatu segmen |
| Repeater/Mesh | Memperluas jaringan melalui koneksi nirkabel | Jika kabel Ethernet sulit ditarik, dengan konsekuensi kapasitas tertentu |

Pada jaringan kantor, mode AP/bridge biasanya dipilih jika DHCP, NAT, firewall, dan routing sudah ditangani oleh router atau firewall utama. Hindari mengaktifkan beberapa server DHCP pada satu segmen tanpa desain yang jelas.

#### 3. Mengatur SSID

SSID adalah nama jaringan nirkabel yang terlihat oleh pengguna. Praktik yang disarankan:

- gunakan nama yang mudah dikenali;
- hindari nama yang memuat alamat, password, atau informasi pribadi;
- bedakan SSID pegawai dan tamu jika kebijakan aksesnya berbeda;
- gunakan SSID yang konsisten pada AP yang melayani jaringan yang sama;
- matikan SSID yang tidak diperlukan.

| SSID | Fungsi | VLAN | Akses |
|---|---|---:|---|
| Kantor-Internal | Pegawai | 10 | Internet dan layanan internal |
| Kantor-Tamu | Tamu | 20 | Internet saja |
| Kantor-IoT | Perangkat IoT | 30 | Hanya layanan yang diperlukan |

SSID yang berbeda sebaiknya dipetakan ke VLAN dan aturan firewall yang sesuai. Mengganti nama SSID saja tidak cukup untuk memisahkan jaringan.

#### 4. Mengatur keamanan Wi-Fi

- pilih WPA3 jika seluruh perangkat klien mendukungnya;
- gunakan WPA2-AES sebagai alternatif kompatibilitas;
- gunakan password panjang, unik, dan tidak sama dengan password administrator;
- aktifkan guest network untuk tamu;
- batasi akses antar-VLAN melalui firewall;
- gunakan autentikasi terpusat seperti 802.1X/RADIUS jika diperlukan;
- perbarui firmware dan nonaktifkan administrasi dari internet jika tidak diperlukan.

#### 5. Mengatur frekuensi dan kanal

Konfigurasikan pita 2,4 GHz, 5 GHz, atau keduanya sesuai kebutuhan.

- gunakan kanal yang tidak saling bertabrakan dengan AP di sekitar;
- pada 2,4 GHz, gunakan perencanaan kanal yang tidak tumpang tindih sesuai regulasi dan kondisi lokal;
- gunakan lebar kanal yang tidak terlalu besar jika lingkungan padat;
- pada 5 GHz, perhatikan kanal DFS dan karakteristik jangkauan yang berbeda;
- uji kanal menggunakan site survey atau alat analisis Wi-Fi.

Lebar kanal yang lebih besar dapat meningkatkan kecepatan teoritis, tetapi juga dapat meningkatkan penggunaan spektrum dan interferensi.

#### 6. Mengatur DHCP dan alamat manajemen

Jika router utama menyediakan DHCP, AP dapat dikonfigurasi sebagai DHCP client. Alamat manajemen sebaiknya mudah ditemukan, misalnya melalui DHCP reservation.

Alternatifnya adalah memberi IP manajemen statis:

```text
AP-LT1 : 192.168.10.11/24
Gateway: 192.168.10.1
DNS    : 192.168.10.1
VLAN   : 10
```

Pastikan alamat tidak bertabrakan, berada pada subnet manajemen yang benar, tidak termasuk DHCP pool, serta tercatat dalam dokumentasi.

#### 7. Mengonfigurasi VLAN dan koneksi switch

Jika AP membawa beberapa SSID dengan VLAN berbeda:

- port switch menuju AP biasanya dikonfigurasi sebagai trunk;
- VLAN yang diperlukan harus diizinkan pada trunk;
- VLAN native atau untagged harus ditentukan dengan hati-hati;
- SSID internal dan tamu dipetakan ke VLAN masing-masing;
- router atau Layer 3 Switch menyediakan gateway dan routing antar-VLAN;
- firewall membatasi akses antar-segmen.

Jika AP hanya membawa satu jaringan, port dapat menggunakan mode access sesuai desain. Jangan mengubah port menjadi trunk tanpa memahami konfigurasi VLAN di sisi router atau switch.

#### 8. Memperbarui firmware

Sebelum memperbarui firmware:

1. Catat model dan versi perangkat.
2. Pastikan firmware sesuai model dan wilayah perangkat.
3. Backup konfigurasi.
4. Gunakan sumber listrik yang stabil.
5. Jangan mematikan perangkat selama proses berlangsung.
6. Periksa kembali konfigurasi setelah reboot.

Firmware sering berisi perbaikan keamanan, stabilitas, dan kompatibilitas.

#### 9. Pengujian setelah konfigurasi

Uji dari beberapa perangkat dan lokasi:

- perangkat dapat melihat dan terhubung ke SSID;
- autentikasi berhasil;
- perangkat memperoleh IP dari DHCP;
- perangkat dapat melakukan ping ke gateway;
- DNS dapat menerjemahkan nama domain;
- akses internet berjalan sesuai kebijakan;
- VLAN tamu tidak dapat mengakses jaringan internal;
- throughput dan latency sesuai kebutuhan;
- roaming antar-AP berjalan baik;
- log dan daftar klien menampilkan informasi yang benar.

Contoh urutan pemeriksaan:

```text
Klien Wi-Fi → IP address → gateway → DNS → internet
```

Konfigurasi dinyatakan selesai setelah hasil pengujian dicatat dan konfigurasi akhir dicadangkan.

### 16. Menetapkan Rencana Pengujian Jaringan

Pengujian jaringan bukan sekadar memastikan perangkat dapat terhubung. Pengujian harus dilakukan secara sistematis untuk mengetahui apakah jaringan memenuhi kebutuhan cakupan, kecepatan, keamanan, roaming, dan kestabilan.

#### 1. Menentukan tujuan dan kriteria keberhasilan

Sebelum melakukan pengujian, tetapkan:

- area yang harus mendapatkan layanan;
- jumlah perangkat yang diuji;
- target kekuatan sinyal;
- target throughput dan latency;
- aturan keamanan yang harus dipenuhi;
- durasi dan beban pengujian;
- bukti atau hasil yang harus didokumentasikan.

Contoh kriteria:

| Aspek | Contoh kriteria keberhasilan |
|---|---|
| Coverage | Tidak ada dead spot pada area kerja utama |
| Sinyal | Nilai RSSI memenuhi kebutuhan aplikasi dan lokasi |
| Throughput | Kecepatan sesuai target desain pada lokasi pengujian |
| Latency | Keterlambatan masih sesuai kebutuhan aplikasi |
| Roaming | Perpindahan antar-AP tidak memutus sesi secara signifikan |
| Keamanan | Klien tanpa kredensial tidak dapat masuk |
| Stabilitas | Koneksi tetap berjalan selama pengujian beban |

#### 2. Pengujian jangkauan atau coverage

Coverage testing memastikan sinyal mencapai seluruh area yang telah ditentukan. Gunakan Wi-Fi analyzer atau perangkat lunak heatmap untuk memetakan kekuatan sinyal dalam dBm.

Langkah umum:

1. Buat denah area pengujian.
2. Tentukan titik pengukuran dengan jarak yang konsisten.
3. Ukur RSSI, noise, channel, dan kualitas koneksi.
4. Tandai area dengan sinyal lemah atau dead spot.
5. Ulangi pengukuran setelah posisi AP atau kanal diperbaiki.

Nilai dBm biasanya bernilai negatif. Semakin mendekati nol, sinyal semakin kuat. Jangan menetapkan satu angka universal tanpa memperhatikan jenis aplikasi, noise, kemampuan klien, dan kondisi lokasi.

#### 3. Pengujian kinerja

Ukur throughput, latency, packet loss, dan kestabilan pada beberapa lokasi serta waktu yang berbeda. `iperf3` dapat digunakan untuk mengukur performa antara dua perangkat yang berada dalam jaringan yang sama.

Contoh pada komputer server:

```bash
iperf3 -s
```

Contoh pada komputer klien:

```bash
iperf3 -c 192.168.10.10 -t 30
```

Uji unduh dan unggah secara terpisah jika diperlukan. Bedakan hasil jaringan lokal dengan hasil speed test internet karena speed test internet juga dipengaruhi ISP, server tujuan, dan jalur internet.

Pengujian tambahan:

```bash
ping 192.168.10.1
traceroute example.com
```

#### 4. Pengujian roaming

Jika terdapat beberapa AP, uji kemampuan perangkat berpindah dari satu AP ke AP lain tanpa kehilangan koneksi yang mengganggu.

Langkah pengujian:

1. Hubungkan perangkat klien ke SSID yang benar.
2. Mulai ping atau panggilan video sebagai sesi pengamatan.
3. Bergerak melewati area cakupan AP pertama menuju AP berikutnya.
4. Catat perubahan BSSID, waktu perpindahan, packet loss, dan apakah sesi terputus.
5. Ulangi dengan beberapa perangkat klien.

Hasil roaming dipengaruhi oleh AP, pengaturan kanal, overlap, driver klien, dan keputusan klien dalam berpindah AP.

#### 5. Pengujian keamanan

Pastikan:

- enkripsi WPA3 atau WPA2-AES berjalan sesuai desain;
- password yang salah ditolak;
- SSID tamu tidak dapat mengakses server atau perangkat pegawai;
- VLAN dan firewall menerapkan aturan akses;
- port administrasi tidak terbuka ke internet tanpa alasan;
- firmware dan konfigurasi default yang berisiko sudah diperbarui;
- log mencatat kejadian penting.

Pengujian keamanan harus dilakukan pada jaringan milik sendiri atau jaringan yang telah memperoleh izin. Jangan melakukan pemindaian terhadap jaringan pihak lain.

#### 6. Pengujian stabilitas dan beban

Hubungkan sejumlah perangkat secara bersamaan dan lakukan aktivitas yang menyerupai kondisi nyata, misalnya browsing, video conference, transfer file, dan akses aplikasi internal.

Amati:

- putus koneksi;
- peningkatan latency;
- packet loss;
- penggunaan CPU dan memori perangkat;
- penggunaan kanal dan bandwidth;
- suhu perangkat;
- error pada port atau interface.

Mulai dengan beban kecil, tingkatkan secara bertahap, dan hentikan pengujian jika berisiko mengganggu layanan produksi.

#### 7. Format laporan pengujian

| Waktu | Lokasi | SSID/VLAN | Perangkat klien | RSSI | Throughput | Latency | Hasil | Catatan |
|---|---|---|---|---:|---:|---:|---|---|
| 09:00 | Ruang rapat | Kantor-Internal/10 | Laptop-01 | -55 dBm | 180 Mbps | 8 ms | Lulus | Sinyal stabil |
| 09:15 | Lobby | Kantor-Tamu/20 | Smartphone-01 | -68 dBm | 80 Mbps | 15 ms | Lulus | Perlu pemantauan |

Dokumentasikan alat yang digunakan, versi firmware, konfigurasi saat pengujian, hasil mentah, kesimpulan, dan rekomendasi perbaikan.

#### 8. Siklus pengujian dan perbaikan

Gunakan siklus berikut:

```text
Rencanakan → Uji → Catat hasil → Analisis → Perbaiki → Uji ulang
```

Jaringan dinyatakan siap ketika hasil pengujian memenuhi kriteria yang telah ditetapkan, risiko telah dicatat, dan bukti pengujian tersimpan.

## Referensi

- Materi pelatihan pada LMS Digital Talent Scholarship/Komdigi.
- Dokumentasi resmi Windows Networking.
- Dokumentasi resmi Ubuntu Server dan Netplan.
- Dokumentasi resmi Apple macOS User Guide.
- Dokumentasi Nmap dan Wireshark.

---

Catatan ini akan diperbarui seiring materi pelatihan dipelajari.
