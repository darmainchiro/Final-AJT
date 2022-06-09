Tugas 4

SPF Routing

1. Monitoring RYU untuk mengetahui rute terpendek dengan menggunakan metode dijkstra. Topologi yang digunakan
sebagai berikut.

![ss update](./ss-topo1.png)

2. Jalankan program RYU. Perintah “—observe-links” digunakan untuk mengamati dan mengetahui posisi masing-masing switch terhubung satu sama lain termasuk untuk mendeteksi host-nya.

```
ryu-manager --observe-links dijksta_Ryu_controller.py
```
![ss update](./ss-30.png)

3. Jalankan program topologi

![ss update](./ss-31.png)

4. ping h1 ke h4

![ss update](./ss-32.png)

5. Cek monitoring RYU. Terjadi paket masuk dari host 1 (source) ke tujuan (destination) host 4. dpid merupakan switch yang digunakan. Paket akan mem-broadcast ke semua switch untuk mengetahui jalur mana yang dapat dilalui.

![ss update](./ss-34.png)

Proses akan mendapat hasil tujuannya berada dimana yaitu di switch 4 port 1 yang mana merupakan host 4. Setelah tujuan ditemukan, akan terjadi proses h1 untuk menentukan dengan iterasi sampai kemudian ditemukan jalur terpendek dari path yang sudah ditemukan.

![ss update](./ss-35.png)

6. Jalur yang ditemukan yaitu dari Swith 1 port 1 ke port 2 → Switch 2 port 2 ke port 3 → Switch 4 port 2 ke port 1.

![ss update](./ss-topo2.png)

