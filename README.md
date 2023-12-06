# Kelompok IT10 #

## Anggota: ##
1. Caroline Permatasari Pramestita Gondo Kusumo (5027211048)
2. Vira Datry Maulydina (5027211050)

## Topologi VLSM ##
Dibawah ini adalah topologi pada cpt untk Vlsm
<img width="703" alt="topologi vslm" src="https://github.com/viradatry/Jarkom-Modul-4-IT10-2023/assets/113564685/e1b066f6-94c6-4f28-9b36-e61bbd50bf8d">

## Tree VLSM ##
Dibawah ini adalah tree pada vlsm dari pembagian `IP` yang sudah kita hitung pada list sheet
![tree vlsm](https://github.com/viradatry/Jarkom-Modul-4-IT10-2023/assets/113564685/57ffd6cd-0c60-44aa-a79b-19614eace495)

## Rute VLSM ##
Dibawah ini adalah cara kerja rute VLSM yang di sesuain dengan topologi yang sudah saya buat
![image](https://github.com/viradatry/Jarkom-Modul-4-IT10-2023/assets/113564685/23032a1e-cd37-4385-8c00-100940199111)

## Pembagian IP VLSM ##
Sebelum kita melakukan setup pada node cpt, terlebih dahulu kita menghitung pembagian IP seperti gambar dibawah ini
![image](https://github.com/viradatry/Jarkom-Modul-4-IT10-2023/assets/113564685/a52481dd-fe34-40bd-9337-586ad36f4284)

## Testing VLSM ##
Setelah melakukan setup IP pada semua node langkah selanjutnya yaitu :

1. melakukan testing pada `RiegelCanyon` - `Aura` jika testing yang dilakukan berhasil dia akan mendapatkan output seperti gambar dibawah ini `Successful`

<img width="599" alt="RiegelCanyon - Aura" src="https://github.com/viradatry/Jarkom-Modul-4-IT10-2023/assets/113564685/2992f32c-f61a-4d6c-89e9-0bdd8b77145d">

2. melakukan testing pada `GranzChannel` - `Turk Region` jika testing yang dilakukan berhasil dia akan mendapatkan output seperti gambar dibawah ini `Successful`
<img width="603" alt="GranzChannel - Turk Region" src="https://github.com/viradatry/Jarkom-Modul-4-IT10-2023/assets/113564685/3c92b8d5-67fc-4ba1-9365-172e0ab93690">

3. melakukan testing pada `Sein` - `Richter` jika testing yang dilakukan berhasil dia akan mendapatkan output seperti gambar dibawah ini `Successful`
<img width="599" alt="Sein - Richter" src="https://github.com/viradatry/Jarkom-Modul-4-IT10-2023/assets/113564685/606f5497-ecc7-4471-8cbe-98b7483ea213">

## Topologi CIDR ##

<a href="https://ibb.co/LxFL3bP"><img src="https://i.ibb.co/3p3DnGs/Topologi.jpg" alt="Topologi" border="0"></a>

## Rute CIDR ##

<a href="https://ibb.co/6YJqnKG"><img src="https://i.ibb.co/gyFcj0Q/Rute.jpg" alt="Rute" border="0"></a>

## Tree CIDR ##

<a href="https://ibb.co/wYYj2md"><img src="https://i.ibb.co/KmmS8v5/Tree.png" alt="Tree" border="0"></a>

## Pembagian IP CIDR ## 

<a href="https://ibb.co/jZ6bq0c"><img src="https://i.ibb.co/FqxmcZS/Pembagian-IP.jpg" alt="Pembagian-IP" border="0"></a>

## Konfigurasi CIDR ##
Eisen
```
# Eisen
auto lo
iface lo inet loopback

# A1 Eisen-Switch0-Stark 
auto eth3
iface eth3 inet static
    address 192.238.80.1
    netmask 255.255.255.252

# A2 Eisen-Switch1-Richter-Revolte
auto eth1
iface eth1 inet static
    address 192.238.32.1
    netmask 255.255.255.248

# A3 Eisen-Aura
auto eth0
iface eth0 inet static
    address 192.238.128.2
    netmask 255.255.255.252
    gateway 192.238.128.1

# A14 Eisen - Linie 
auto eth2 
iface eth2 inet static
    address 192.238.10.1 
    netmask 255.255.255.252

# A19 Eisen - Lugner 
auto eth4
iface eth4 inet static
    address 192.238.72.1
    netmask 255.255.255.252
```

Aura
```
auto lo
iface lo inet loopback

# A3 Aura-Eisen
auto eth2 
iface eth2 inet static
    address 192.238.128.1
    netmask 255.255.255.252

# A4 Aura-Denken
auto eth1 
iface eth1 inet static
    address 192.238.1.1
    netmask 255.255.255.252

# A6 Aura-Frieren
auto eth3
iface eth3 inet static
    address 192.240.128.2
    netmask 255.255.255.252
```

Denken
```
auto lo
iface lo inet loopback

# A4 Denken-Aura
auto eth0
iface eth0 inet static
    address 192.238.1.2
    netmask 255.255.255.252
    gateway 192.238.1.1

# A5 Denken-Switch2-RoyalCapital-WilleRegioN
auto eth1
iface eth1 inet static
    address 192.239.0.1
    netmask 255.255.255.0
```

Frieren 
```
auto lo
iface lo inet loopback

# A6 Aura-Frieren
auto eth0 
iface eth0 inet static
    address 192.240.128.3
    netmask 255.255.255.252
    gateway 192.240.128.2

# A7 Frieren-Switch3-Lake
auto eth2
iface eth2 inet static
    address 192.240.64.1
    netmask 255.255.225.224

# A8 Frieren-Flame  
auto eth1
iface eth1 inet static
    address 192.240.32.1
    netmask 255.255.255.252
```

Flamme 
```
auto lo
iface lo inet loopback

# A8 Frieren-Flame
auto eth0 
iface eth0 inet static
    address 192.240.32.2
    netmask 255.255.255.252
    gateway 192.240.32.1

# A9 Flame-Fern 
auto eth3
iface eth3 inet static
    address 192.240.8.1
    netmask 255.255.255.252

# A11 Flamme-Switch5-RohrRoad
auto eth2
iface eth2 inet static
    address 192.240.16.17
    netmask 255.255.252.0

# A12 Flamme-Himmel
auto eth1 
iface eth1 inet static
    address 192.240.20.9
    netmask 255.255.255.252
```

Fern
```
auto lo
iface lo inet loopback

# A9 Flame-Fern
auto eth0
iface eth0 inet static
    address 192.240.8.2
    netmask 255.255.255.252
    gateway 192.240.8.1

# A10 Fern-Switch4-LaubHills-AppetitRegion
auto eth1
iface eth1 inet static
    address 192.240.0.1
    netmask 255.255.248.0
```

Himmel 
```
auto lo
iface lo inet loopback

# A12 Flamme-Himmel
auto eth0
iface eth0 inet static
    address 192.240.20.10
    netmask 255.255.255.252
    gateway 192.240.20.9

# A13 Himmel-Switch6-SchwerMountains
auto eth1
iface eth1 inet static
    address 192.240.20.1
    netmask 255.255.255.248
```

Linie 
```
auto lo
iface lo inet loopback

# A14 Eisen - Linie
auto eth0
iface eth0 inet static
    address 192.238.10.2
    netmask 255.255.255.252
    gateway 192.238.16.1

# A15 Linie - Lawine 
auto eth1
iface eth1 inet static
    address 192.238.10.1
    netmask 255.255.255.252

# A21 Linie-Switch11-GranzChannel
auto eth2
iface eth2 inet static
    address 192.238.8.1
    netmask 255.255.254.0
```

Lawine 
```
auto lo
iface lo inet loopback

# A15 Linie - Lawine
auto eth0
iface eth0 inet static
    address 192.238.10.2
    netmask 255.255.255.252
    gateway 192.238.10.1

# A16 Lawine-Switch7-BredtRegion-Heiter
auto eth1
iface eth1 inet static
    address 192.238.4.1
    netmask 255.255.255.192
```

Heiter 
```
auto lo
iface lo inet loopback

# A16 Lawine-Switch7-BredtRegion-Heiter
auto eth0
iface eth0 inet static
    address 192.238.4.3
    netmask 255.255.255.192
    gateway 192.238.4.1

# A17 Heiter-Switch8-Sein-RiegelCanyon
auto eth1
iface eth1 inet static
    address 192.238.0.1
    netmask 255.255.252.0
```

Lugner 
```
auto lo
iface lo inet loopback

# A18 Eisen - Lugner
auto eth0
iface eth0 inet static
    address 192.238.72.2
    netmask 255.255.255.252 
    gateway 192.238.72.1

# A19 Lugner-Switch9-GrobeForest
auto eth1
iface eth1 inet static
    address 192.238.68.1
    netmask 255.255.255.0

# A20 Lugner-Switch10-TurkRegion
auto eth2 
iface eth2 inet static
    address 192.238.64.1
    netmask 255.255.252.0
```

Stark 
```
auto eth0
iface eth0 inet static
    address 192.238.80.2
    netmask 255.255.255.252
    gateway 192.238.80.1
```

Richter 
```
auto eth0
iface eth0 inet static
    address 192.238.32.2
    netmask 255.255.255.248
    gateway 192.238.32.1
```

Revolte 
```
auto eth0
iface eth0 inet static
    address 192.238.32.3 
    netmask 255.255.255.248
    gateway 192.238.32.1
```

RoyalCapital 
```
auto eth0
iface eth0 inet static
    address 192.239.0.2
    netmask 255.255.255.0
    gateway 192.239.0.1
```

WillieRegion
```
auto eth0
iface eth0 inet static
    address 192.239.0.3
    netmask 255.255.255.0
    gateway 192.239.0.1
```

LakeKoridor
```
auto eth0
iface eth0 inet static
    address 192.240.64.2
    netmask 255.255.225.224
    gateway 192.240.64.1
```

LaubHills
```
auto eth0
iface eth0 inet static
    address 192.240.0.2
    netmask 255.255.248.0
    gateway 192.240.0.1
```

AppetitRegion
```
auto eth0
iface eth0 inet static
    address 192.240.0.3
    netmask 255.255.248.0
    gateway 192.240.0.1
```

RohrRoad
```
auto eth0
iface eth0 inet static
    address 192.240.16.18
    netmask 255.255.252.0
    gateway 192.240.16.17
```

SchwerMountains
```
auto eth0
iface eth0 inet static
    address 192.240.20.2
    netmask 255.255.255.248
    gateway 192.240.20.1
```

BredtRegion
```
auto eth0
iface eth0 inet static
    address 192.238.4.2
    netmask 255.255.255.192
    gateway 192.238.4.1
```

Sein
```
auto eth0
iface eth0 inet static
    address 192.238.0.2
    netmask 255.255.252.0
    gateway 192.238.0.1
```

RiegelCanyon
```
auto eth0
iface eth0 inet static
    address 192.238.0.3
    netmask 255.255.252.0
    gateway 192.238.0.1
```

GrobeForest
```
auto eth0
iface eth0 inet static
    address 192.238.68.2
    netmask 255.255.255.0
    gateway 192.238.68.1
```

TurkRegion
```
auto eth0
iface eth0 inet static
    address 192.238.64.2
    netmask 255.255.252.0
    gateway 192.238.64.1
```

GranzChannel
```
auto eth0
iface eth0 inet static
    address 192.238.8.2
    netmask 255.255.254.0
    gateway 192.238.8.1
```

## Routing ## 

Denken 
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.238.1.1
```

Lugner
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.238.128.2
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.238.32.1
```

Linie
```
route add -net 192.238.4.0 netmask 255.255.255.192 gw 192.238.10.2
route add -net 192.238.0.0 netmask 255.255.252.0 gw 192.238.10.2
```

Lawine 
```
route add -net 192.238.0.0 netmask 255.255.252.0 gw 192.238.4.3
```

Heiter
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.238.10.2
```

Himmel
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.240.32.2
```

Flamme 
```
route add -net 192.240.0.0 netmask 255.255.248.0 gw 192.240.8.2
route add -net 192.240.20.0 netmask 255.255.255.248 gw 192.240.20.10
```

Fern
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.240.32.2
```

Frieren 
```
route add -net 192.240.8.0 netmask 255.255.255.252 gw 192.240.32.2
route add -net 192.240.0.0 netmask 255.255.248.0 gw 192.240.32.2
route add -net 192.240.16.0 netmask 255.255.252.0 gw 192.240.32.2
route add -net 192.240.20.8 netmask 255.255.255.252 gw 192.240.32.2
route add -net 192.240.20.0 netmask 255.255.255.248 gw 192.240.32.2
```

Eisen 
```
route add -net 192.238.64.0 netmask 255.255.252.0 gw 192.238.72.2
route add -net 192.238.68.0 netmask 255.255.255.0 gw 192.238.72.2
route add -net 192.238.8.0 netmask 255.255.254.0 gw 192.238.16.2
route add -net 192.238.10.0 netmask 255.255.255.252 gw 192.238.16.2
route add -net 192.238.4.0 netmask 255.255.255.192 gw 192.238.16.2
route add -net 192.238.0.0 netmask 255.255.252.0 gw 192.238.16.2
```

Aura
```
# Frieren
route add -net 192.240.64.0 netmask 255.255.255.224 gw 192.240.128.3
route add -net 192.240.32.0 netmask 255.255.255.252 gw 192.240.128.3
route add -net 192.240.8.0 netmask 255.255.255.252 gw 192.240.128.3
route add -net 192.240.0.0 netmask 255.255.248.0 gw 192.240.128.3
route add -net 192.240.16.0 netmask 255.255.252.0 gw 192.240.128.3
route add -net 192.240.20.8 netmask 255.255.255.252 gw 192.240.128.3
route add -net 192.240.20.0 netmask 255.255.255.248 gw 192.240.128.3

# Denken
route add -net 192.239.0.0 netmask 255.255.255.0 gw 192.238.1.2

# Eisen
route add -net 192.238.80.0 netmask 255.255.255.252 gw 192.238.128.2
route add -net 192.238.72.0 netmask 255.255.255.252 gw 192.238.128.2
route add -net 192.238.64.0 netmask 255.255.252.0 gw 192.238.128.2
route add -net 192.238.68.0 netmask 255.255.255.0 gw 192.238.128.2
route add -net 192.238.16.0 netmask 255.255.255.252 gw 192.238.128.2
route add -net 192.238.8.0 netmask 255.255.254.0 gw 192.238.128.2
route add -net 192.238.10.0 netmask 255.255.255.252 gw 192.238.128.2
route add -net 192.238.4.0 netmask 255.255.255.192 gw 192.238.128.2
route add -net 192.238.0.0 netmask 255.255.252.0 gw 192.238.128.2
route add -net 192.238.32.0 netmask 255.255.255.248 gw 192.238.128.2
```

## Testing 

<a href="https://ibb.co/pK7sW5v"><img src="https://i.ibb.co/n1GV3ts/Whats-App-Image-2023-12-06-at-21-23-25.jpg" alt="Whats-App-Image-2023-12-06-at-21-23-25" border="0"></a>

<a href="https://ibb.co/wwfnLWT"><img src="https://i.ibb.co/qWvHnsz/Whats-App-Image-2023-12-06-at-21-23-41.jpg" alt="Whats-App-Image-2023-12-06-at-21-23-41" border="0"></a>
