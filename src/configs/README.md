# Salinan Konfigurasi

Folder ini menyimpan salinan konfigurasi setiap perangkat dalam bentuk teks,
sehingga perubahannya dapat ditelusuri melalui riwayat commit.

| Berkas | Perangkat |
|---|---|
| `router-klinik.txt` | Router tepi, penghubung ke internet, NAT, OSPF |
| `core-switch-l3.txt` | Core switch lapis tiga, pusat routing antar-VLAN, DHCP relay, ACL |
| `access-switch-1.txt` | Access switch zona pendaftaran dan poliklinik |
| `access-switch-2.txt` | Access switch zona farmasi, laboratorium, manajemen |
| `access-switch-3.txt` | Access switch zona tamu |
| `switch-server.txt` | Switch zona server |
| `server-layanan.txt` | Daftar pengaturan layanan DHCP, DNS, web, dan FTP |

## Status

**Sudah terisi, belum diuji di Packet Tracer.** Konfigurasi disusun mengikuti
alamat pada [`docs/pengalamatan-vlsm.md`](../../docs/pengalamatan-vlsm.md).

Yang **wajib dicocokkan ulang** setelah topologi dibangun, karena tidak dapat
dipastikan tanpa perangkatnya:

1. **Nomor antarmuka.** Berkas memakai penomoran contoh (`GigabitEthernet0/0/1`,
   `GigabitEthernet1/0/2`, `FastEthernet0/2`). Nomor sebenarnya bergantung pada
   modul yang dipasang di Packet Tracer.
2. **`ip routing`** pada Catalyst 3560 — perintah ini hanya berlaku pada model
   berfitur lapis tiga.
3. **`ip dhcp relay information trust-all`** — perintah ini tidak ada pada
   sebagian versi IOS lama; bila ditolak, cukup hapus dan andalkan
   `ip helper-address`.
4. **`GANTI_SANDI_INI`** pada `router-klinik.txt` dan `server-layanan.txt` diganti
   dengan sandi sungguhan. Sandi tidak boleh ikut masuk ke repository publik.

Setelah diuji, perbarui berkas ini dan `docs/konfigurasi.md` dengan hasil
`show running-config` yang sesungguhnya — jangan biarkan salinan dan perangkat
berbeda isi.
