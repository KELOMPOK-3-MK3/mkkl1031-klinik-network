# Konfigurasi Perangkat

Salinan konfigurasi setiap perangkat jaringan. Perubahan wajib disalin ke sini
agar dapat ditelusuri melalui riwayat commit.

Status: **kerangka** — konfigurasi diisi setelah topologi dibangun (minggu ke-4).

## Ringkasan Perangkat

| Perangkat | Model pada simulasi | Peran |
|---|---|---|
| Router-Klinik | ISR4331 | Penghubung ke internet, ikut dalam routing dinamis |
| Core-Switch-L3 | Catalyst 3560 | Pusat inter-VLAN routing dan routing dinamis |
| SW-Access-1 | Catalyst 2960 | Zona pendaftaran dan medis |
| SW-Access-2 | Catalyst 2960 | Zona dokter dan manajemen |
| SW-Access-3 | Catalyst 2960 | Zona tamu |
| SW-Server | Catalyst 2960 | Zona server layanan |
| Server-Layanan | Server-PT | Pengalamatan otomatis, penamaan, portal web, berkas |

## Router-Klinik

```
enable
configure terminal
 hostname Router-Klinik
 !
 ! TODO(minggu 5): alamat IP antarmuka ke core switch
 ! TODO(minggu 5): NAT ke luar
 ! TODO(minggu 5): routing dinamis
end
write memory
```

## Core-Switch-L3

```
enable
configure terminal
 hostname Core-Switch-L3
 !
 ! TODO(minggu 4): buat VLAN 10, 20, 30, 40, 50, dan 99
 ! TODO(minggu 4): atur port trunk menuju access switch
 ! TODO(minggu 5): antarmuka virtual per VLAN (inter-VLAN routing)
 ! TODO(minggu 5): routing dinamis
 ! TODO(minggu 5): penerusan permintaan alamat otomatis ke server
 ! TODO(minggu 7): aturan pembatasan akses VLAN tamu
end
write memory
```

## Access Switch

```
enable
configure terminal
 hostname SW-Access-1
 !
 ! TODO(minggu 4): atur VLAN pada port akses
 ! TODO(minggu 4): atur port trunk menuju core switch
end
write memory
```

## Server Layanan

| Layanan | Pengaturan | Status |
|---|---|---|
| DHCP | Satu kumpulan alamat per VLAN, gerbang per VLAN | Belum dikonfigurasi |
| DNS | Catatan nama untuk host internal | Belum dikonfigurasi |
| Web | Halaman portal internal klinik | Belum dikonfigurasi |
| FTP | Akun khusus pencadangan rekam medis | Belum dikonfigurasi |

## Catatan

Nomor antarmuka pada simulasi ditentukan setelah topologi selesai digambar.
Konfigurasi lengkap beserta nomor antarmuka disalin ke folder `src/configs/`
pada repository setelah diuji.
