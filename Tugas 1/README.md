Tugas 1

Instalasi AWS EC2

1. Buat Instance pada halaman EC2
2. Pilih OS yang akan di install (Ubuntu Server 22.04 LTS).

![ss os](./ss-3.png)

3. Kemudian pilih tipe instance yang diinginkan. Pada hal ini memuat CPU, memori, penyimpanan, dan kapasitansi jaringan, dan memungkinkan user untuk memilih campuran sumber daya yang sesuai untuk aplikasi (t2.medium). Kemudian akan muncul kotak dialog key pair. Pilih key pair: vockey.

![ss type](./ss-4.png)

4. Selanjutnya pada konfigurasi detail instance, dalam praktek ini tidak perlu diubah isiannya dan langsung klik next page untuk mengatur storage server.

5. Pada storage isi size 30 GiB dengan tipe volume gp3. Ketika instance terbuat akan ditampilkan storage yang sudah diatur.

![ss storage](./ss-7.png)

6. Kemudian pada halaman selanjutnya tambahkan tags (Name and tags: Tugas Akhir) yang nantinya akan menampilkan pada kolom tags seperti berikut.

![ss tag](./ss-2.png)

7. Selanjutnya akan mengkonfigurasi security group pada instance dengan ketentuan (Edit Network settings: allow SSH, allow HTTP, allow HTTPS, allow TCP port 8080, allow TCP port 8081)

![ss sec](./ss-5.png)

![ss sec](./ss-6.png)

8. Terakhir pada halaman Review and Launch, pilih tombol Launch Instances. 
9. Instance telah berhasil dibuat.

![ss detail](./ss-1.png)

Instalasi Mininet, Ryu, dan Flow Manager

1. Sebelum memulai instalasi sebaiknya perlu untuk mengupdate dan upgrade package yang ada pada server.

```
sudo apt -yy update && sudo apt -yy upgrade
```
![ss update](./ss8.png)

2. Unduh repositori Mininet

```
git clone https://github.com/mininet/mininet
cd mininet
git checkout -b mininet-2.3.0 2.3.0 # or whatever version you wish to install
cd ..
```
3. Instal mininet

```
mininet/util/install.sh -nfv
```
Instalasi untuk mininet, user switch dan OpenFlow
4. Unduh Repositori Ryu dan Install Ryu

```
git clone git://github.com/osrg/ryu.git
cd ryu; pip install .
cd
```
5. Unduh Repositori Flowmanager

```
git clone https://github.com/martimy/flowmanager
cd
```

6. Setelah langkah instalasi Flowmanager, sebaiknya lakukan rebooting Linux anda untuk membuat lingkungan operasional Python, Mininet, Ryu dan OpenFlow dapat berjalan dengan baik.

7. Mencoba menggunakan mininet

![ss mn](./ss10.png)
