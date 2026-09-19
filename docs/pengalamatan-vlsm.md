# Skema Pengalamatan VLSM

Blok alamat induk: `192.168.10.0/24`, dibagi menurut kebutuhan setiap zona.

| VLAN | Nama | Host dibutuhkan | Prefix | Alamat jaringan | Alamat broadcast | Rentang host |
|---|---|---|---|---|---|---|
| 40 | Guest-PasienWiFi | 50 | /26 | 192.168.10.0 | 192.168.10.63 | 192.168.10.1 – 192.168.10.62 |
| 30 | Dokter | 25 | /27 | 192.168.10.64 | 192.168.10.95 | 192.168.10.65 – 192.168.10.94 |
| 10 | Admin-Pendaftaran | 10 | /28 | 192.168.10.96 | 192.168.10.111 | 192.168.10.97 – 192.168.10.110 |
| 20 | Medis-RekamMedis | 10 | /28 | 192.168.10.112 | 192.168.10.127 | 192.168.10.113 – 192.168.10.126 |
| 50 | Server | 10 | /28 | 192.168.10.128 | 192.168.10.143 | 192.168.10.129 – 192.168.10.142 |
| 99 | Management | 5 | /29 | 192.168.10.144 | 192.168.10.151 | 192.168.10.145 – 192.168.10.150 |

Catatan:

- Zona tamu mendapat blok terbesar karena jumlah perangkat pasien tidak dapat diprediksi.
- Urutan pembagian dimulai dari kebutuhan terbesar agar sisa alamat tidak terbuang.
- Setiap VLAN memakai alamat host pertama sebagai gerbang pada core switch.
