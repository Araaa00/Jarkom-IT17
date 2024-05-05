# Jarkom-Modul-2-IT17-2024

##### Praktikum Jaringan Komputer Modul 2 Tahun 2023

### Author
| Nama | NRP |
|---------|---------|
| Mutiara Nurhaliza | 5027221010   |
| Aqila Aqsa | 5027211032   |

#Laporan Resmi

### Topologi


### Config
#### Erangel
```
 auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.72.1.1
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 10.72.2.1
	netmask 255.255.255.0

auto eth3
iface eth3 inet static
	address 10.72.3.1
	netmask 255.255.255.0
```
#### Pocinki 
```
 auto eth0
iface eth0 inet static
	address 10.72.3.2
	netmask 255.255.255.0
	gateway 10.72.3.1
```

#### Serverny 
```
auto eth0
iface eth0 inet static
	address 10.72.1.4
	netmask 255.255.255.0
	gateway 10.72.1.1
```

#### Lipovka 
```
auto eth0
iface eth0 inet static
	address 10.72.1.2
	netmask 255.255.255.0
	gateway 10.72.1.1
```

#### Stalber 
```
auto eth0
iface eth0 inet static
	address 10.72.1.3
	netmask 255.255.255.0
	gateway 10.72.1.1
```
#### Ruins 
```
auto eth0
iface eth0 inet static
	address 10.72.2.2
	netmask 255.255.255.0
	gateway 10.72.2.1
```

#### Apartments 
```
auto eth0
iface eth0 inet static
	address 10.72.2.5
	netmask 255.255.255.0
	gateway 10.72.2.1
```

#### Georgopol 
```
auto eth0
iface eth0 inet static
	address 10.72.2.3
	netmask 255.255.255.0
	gateway 10.72.2.1
```

#### Mylta 
```
auto eth0
iface eth0 inet static
	address 10.72.2.4
	netmask 255.255.255.0
	gateway 10.72.2.1
```

### Inisiasi .bashrc 

#### Erangel
```
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 192.173.0.0/16
echo 'nameserver 192.168.122.1' > /etc/resolv.conf
```
#### Pochinki & Georgopol
```
echo 'nameserver 192.168.122.1' > /etc/resolv.conf
apt-get update
apt-get install bind9 -y      
```
#### Client
```
echo -e '
nameserver 10.72.3.2 
nameserver 10.72.2.3 
nameserver 192.168.122.1
' > /etc/resolv.conf
apt-get update
apt-get install dnsutils -y
apt-get install lynx -y
```

### Soal 1

Membuat jaringan komputer yang akan digunakan sebagai alat komunikasi. Sesuaikan rancangan Topologi dengan rancangan dan pembagian yang berada di link yang telah disediakan, dengan ketentuan nodenya sebagai berikut :
DNS Master akan diberi nama Pochinki, sesuai dengan kota tempat dibuatnya server tersebut
Karena ada kemungkinan musuh akan mencoba menyerang Server Utama, maka buatlah DNS Slave Georgopol yang mengarah ke Pochinki
Markas pusat juga meminta dibuatkan tiga Web Server yaitu Severny, Stalber, dan Lipovka. Sedangkan Mylta akan bertindak sebagai Load Balancer untuk server-server tersebut

Melakukan setup IP dan configurasi yang tertera diatas terlebih dahulu. Kemudian, melakukan testing client Apartments dan Ruins

#### Script

```
ping google.com -c 5
```
#### Output

<img scr="img/1.1">
<img scr="img/1.2">

### Soal 2

Karena para pasukan membutuhkan koordinasi untuk mengambil airdrop, maka buatlah sebuah domain yang mengarah ke Stalber dengan alamat airdrop.xxxx.com dengan alias www.airdrop.xxxx.com dimana xxxx merupakan kode kelompok. Contoh : airdrop.it01.com

#### Script




