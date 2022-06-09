Tugas 2

- Topology Mininet 2 Host dan 2 Switch

![ss update](./ss-top1.png)

1. Jalankan mininet tanpa controller menggunakan custom topo yang sudah dibuat.

```
sudo mn --controller=none --custom custom_topo_2sw2h.py --topo mytopo --mac --arp
```
![ss update](./ss-15.png)

2. Buat flow agar h1 dapat terhubung dengan h2. Uji koneksi agar h1 dengan h2.

![ss update](./ss-16.png)

-  Topology Mininet 3 Switch (loop) dengan 6 Host dengan Penerapan STP (spanning tree protocol)

![ss update](./ss-top2.png)

1. Jalankan program Ryu STP yang berada pada folder ryu.

```
ryu-manager ryu/ryu/app/simple_switch_stp_13.py
```
![ss update](./ss-17.png)

2. Jalankan mininet dengan controller=remote menggunakan custom topo yang sudah dibuat.

```
sudo mn --controller=remote --custom topoku_3sw6h.py --topo mytop
o --mac
```
![ss update](./ss-18.png)

3. Pada ryu untuk menjadikan switch menjadi baik, proses identifikasi switch learning satu sama lain pada portnya yang terkoneksi. Hal pertama program akan BLOKING LISTENING untuk mengenali jaringan. Setelah itu ketika sudah mengetahui STP nya akan memblok salah satu yang tidak penting.

![ss update](./ss-19.png)

4. Dump untuk mengetahui jaringan

```
dpctl dump-flows -O openflow13
```
![ss update](./ss-20.png)

5. Terakhir mencoba untuk ping pada h5 to h3. Time di awal akan besar dan selanjutnya akan kecil karena sudah mengetahui jaringannya dan sudah ada di table flow nya.

![ss update](./ss-21.png)

![ss update](./ss-23.png)

6. Pada ryu menunjukan paket-paket yang sedang berjalan

![ss update](./ss-22.png)

