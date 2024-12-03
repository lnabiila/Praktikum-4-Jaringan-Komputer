| Name           | NRP        | Kelas     |
| ---            | ---        | ----------|
| Hilmi Fawwaz Sa'ad | 5025221103 | Jaringan Komputer (A) |
| Lathiifah Nabiila Bakhtiar | 5025221130 | Jaringan Komputer (A) |

<br>

<b> Letakkan link excel hasil perhitungan di sini </b>
<br>
<b> _Place the excel calculation results link here_ </b>
```
https://docs.google.com/spreadsheets/d/1flh4N3O6QEj0E_FWLTq0pyBXpEb2GYZGlLYGmebu3Bo/edit?usp=sharing
```

Dokumentasi lebih lengkap bisa di cek pada [A13_Praktikum4](https://drive.google.com/drive/folders/1oZJS1YLJMxigDAhcLq59TiFGn-kS0Fgb)

# Laporan Praktikum Modul 4 Non Terraform

## Prefix IP
Letakkan prefix IP yang digunakan di bawah:

_Put IP prefix used below:_
```
10.14.x.x
```

## Topology

- GNS3

  ![Screenshot 2024-11-18 175217](https://github.com/user-attachments/assets/adb26d40-a363-4102-84ac-e12c070cee0e)

- CPT

  ![fix-zoom](https://github.com/user-attachments/assets/2eeae188-5900-4cb2-9ce5-202d031bec69)


<br>

## Routing

- Routing table

  ![image](https://github.com/user-attachments/assets/502968b8-85b9-4f44-90a2-7658916dfbde)

- Route visualization in topology

  ![Screenshot 2024-11-18 195939](https://github.com/user-attachments/assets/d68e4497-1902-4c9e-9d33-6e52e96188d0)

<br>

## VLSM

### Tree

- Tree image

  ![image](https://github.com/user-attachments/assets/2b0e3756-3c74-4ced-a245-d229c4b7cf4e)

  - Link
    ```
    https://miro.com/app/board/uXjVLFYyWY4=/?share_link_id=83331511816
    ```

- IP distribution table

  ![image](https://github.com/user-attachments/assets/3eb739af-17b3-4486-8de7-65b7d40f42a9)

### Subnetting (If you use GNS3)

Configuration to every router, client, and server for subnetting.

- Kamachi:

  ```
  auto eth0
  iface eth0 inet dhcp
  up iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.14.0.0/20
  
  auto eth1
  iface eth1 inet static
  	address 10.14.0.1
  	netmask 255.255.255.252
  auto eth2
  iface eth2 inet static
  	address 10.14.0.5
  	netmask 255.255.255.252
  auto eth3
  iface eth3 inet static
  	address 10.14.0.13
  	netmask 255.255.255.252
  auto eth4
  iface eth4 inet static
  	address 10.14.0.33
  	netmask 255.255.255.252
  auto eth5
  iface eth5 inet static
  	address 10.14.0.37
  	netmask 255.255.255.252
  ```

- Fiamma:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.2
  	netmask 255.255.255.252
  	gateway 10.14.0.1
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.2.1
  	netmask 255.255.254.0
  ```

- GoldenDawn:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.6
  	netmask 255.255.255.252
  	gateway 10.14.0.5
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.8.1
  	netmask 255.255.248.0
  
  auto eth2
  iface eth2 inet static
  	address 10.14.0.9
  	netmask 255.255.255.252
  ```

- Necessarius:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.14
  	netmask 255.255.255.252
  	gateway 10.14.0.13
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.0.17
  	netmask 255.255.255.252
  
  auto eth2
  iface eth2 inet static
  	address 10.14.0.29
  	netmask 255.255.255.252
  ```

- Alice:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.34
  	netmask 255.255.255.252
  	gateway 10.14.0.33
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.6.1
  	netmask 255.255.254.0
  ```

- Kihara:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.38
  	netmask 255.255.255.252
  	gateway 10.14.0.37
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.0.41
  	netmask 255.255.255.252
  
  auto eth2
  iface eth2 inet static
  	address 10.14.0.45
  	netmask 255.255.255.252
  ```

- Vento:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.2.2
  	netmask 255.255.254.0
  	gateway 10.14.2.1
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.0.65
  	netmask 255.255.255.224
  ```

- Terra:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.66
  	netmask 255.255.255.224
  	gateway 10.14.0.65
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf

  ```

- Acqua:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.2.3
  	netmask 255.255.254.0
  	gateway 10.14.2.1
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Aiwass:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.8.2
  	netmask 255.255.248.0
  	gateway 10.14.8.1
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Aleister:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.12.89
  	netmask 255.255.248.0
  	gateway 10.14.8.1
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Mathers:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.10
  	netmask 255.255.255.252
  	gateway 10.14.0.9
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Coronzon:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.18
  	netmask 255.255.255.252
  	gateway 10.14.0.17
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.0.21
  	netmask 255.255.255.252
  
  auto eth2
  iface eth2 inet static
  	address 10.14.0.25
  	netmask 255.255.255.252
  ```

- Elizard:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.22
  	netmask 255.255.255.252
  	gateway 10.14.0.21
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Index:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.26
  	netmask 255.255.255.252
  	gateway 10.14.0.25
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.0.49
  	netmask 255.255.255.240
  ```

- Magnus:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.50
  	netmask 255.255.255.240
  	gateway 10.14.0.49
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Gremlin:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.30
  	netmask 255.255.255.252
  	gateway 10.14.0.29
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.4.1
  	netmask 255.255.254.0
  ```

- Thor:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.4.2
  	netmask 255.255.254.0
  	gateway 10.14.4.1
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Othinus:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.5.188
  	netmask 255.255.254.0
  	gateway 10.14.4.1
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- LastOrder:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.6.2
  	netmask 255.255.254.0
  	gateway 10.14.6.1
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.0.129
  	netmask 255.255.255.128
  ```

- Leivinia:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.130
  	netmask 255.255.255.128
  	gateway 10.14.0.129
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Fuze:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.6.3
  	netmask 255.255.254.0
  	gateway 10.14.6.1
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Accel:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.42
  	netmask 255.255.255.252
  	gateway 10.14.0.41
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.1.1
  	netmask 255.255.255.128
  ```

- Railgun:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.1.2
  	netmask 255.255.255.128
  	gateway 10.14.1.1
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  
  auto eth1
  iface eth1 inet static
  	address 10.14.0.97
  	netmask 255.255.255.224
  ```

- MeltDowner:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.98
  	netmask 255.255.255.224
  	gateway 10.14.0.97
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- MentalOut:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.123
  	netmask 255.255.255.224
  	gateway 10.14.0.97
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- DarkMatter:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.1.3
  	netmask 255.255.255.128
  	gateway 10.14.1.1
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

- Noukan:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.0.46
  	netmask 255.255.255.252
  	gateway 10.14.0.45
  	up echo nameserver 192.168.122.1 > /etc/resolv.conf
  ```

### Routing

Configuration to every router for routing.

- Kamachi:

  ```
  post-up route add -net 10.14.2.0 netmask 255.255.254.0 gw 10.14.0.2
  post-up route add -net 10.14.8.0 netmask 255.255.248.0 gw 10.14.0.6
  post-up route add -net 10.14.0.8 netmask 255.255.255.252 gw 10.14.0.6
  post-up route add -net 10.14.0.16 netmask 255.255.255.252 gw 10.14.0.14
  post-up route add -net 10.14.0.28 netmask 255.255.255.252 gw 10.14.0.14
  post-up route add -net 10.14.6.0 netmask 255.255.254.0 gw 10.14.0.34
  post-up route add -net 10.14.0.40 netmask 255.255.255.252 gw 10.14.0.38
  post-up route add -net 10.14.0.44 netmask 255.255.255.252 gw 10.14.0.38
  post-up route add -net 10.14.0.64 netmask 255.255.255.224 gw 10.14.0.2
  post-up route add -net 10.14.0.20 netmask 255.255.255.252 gw 10.14.0.14
  post-up route add -net 10.14.0.24 netmask 255.255.255.252 gw 10.14.0.14
  post-up route add -net 10.14.0.48 netmask 255.255.255.240 gw 10.14.0.14
  post-up route add -net 10.14.4.0 netmask 255.255.254.0 gw 10.14.0.14
  post-up route add -net 10.14.0.128 netmask 255.255.255.128 gw 10.14.0.34
  post-up route add -net 10.14.1.0 netmask 255.255.255.128 gw 10.14.0.38
  post-up route add -net 10.14.0.96 netmask 255.255.255.224 gw 10.14.0.38
  ```

- Fiamma:

  ```
  post-up route add -net 10.14.0.64 netmask 255.255.255.224 gw 10.14.2.2
  ```

- GoldenDawn:

  ```
  Tidak ada
  ```

- Necessarius:

  ```
  post-up route add -net 10.14.0.20 netmask 255.255.255.252 gw 10.14.0.18
  post-up route add -net 10.14.0.24 netmask 255.255.255.252 gw 10.14.0.18
  post-up route add -net 10.14.0.48 netmask 255.255.255.240 gw 10.14.0.18
  post-up route add -net 10.14.4.0 netmask 255.255.254.0 gw 10.14.0.30
  ```

- Alice:

  ```
  post-up route add -net 10.14.0.128 netmask 255.255.255.128 gw 10.14.6.2
  ```

- Kihara:

  ```
  post-up route add -net 10.14.1.0 netmask 255.255.255.128 gw 10.14.0.42
  post-up route add -net 10.14.0.96 netmask 255.255.255.224 gw 10.14.0.42
  ```

- Vento:

  ```
  Tidak ada
  ```

- Coronzon:

  ```
  post-up route add -net 10.14.0.48 netmask 255.255.255.240 gw 10.14.0.26
  ```

- Index:

  ```
  Tidak ada
  ```

- Gremlin:

  ```
  Tidak ada
  ```

- LastOrder:

  ```
  Tidak ada
  ```

- Accel:

  ```
  post-up route add -net 10.14.0.96 netmask 255.255.255.224 gw 10.14.1.2
  ```

- Railgun:

  ```
  Tidak ada
  ```

### Testing

- Client - client

  ![image](https://github.com/user-attachments/assets/cb5f48c0-6adc-4ab0-ac8d-b5ef3d2c7607)
  ![image](https://github.com/user-attachments/assets/def57ec1-baf4-48a0-ab72-ff61de23cf2d)

- Client - Server

  ![image](https://github.com/user-attachments/assets/2dcfbd8d-2795-4e37-b7d0-1cc90069f0bc)

- Client - Router

  ![image](https://github.com/user-attachments/assets/51a2019c-9430-429a-a559-0be8d8d43b01)
  ![image](https://github.com/user-attachments/assets/194681fa-c10b-47cf-bfa2-986653a1d126)
  ![image](https://github.com/user-attachments/assets/8d3f8fe2-4cf3-4c64-8294-7281c7c2c2fa)
  
- Server - Server

  ![image](https://github.com/user-attachments/assets/2ad13a9b-01c9-4eb1-b035-1257c2bf55a5)

- Server - Router

  ![image](https://github.com/user-attachments/assets/f76d7703-dd21-4677-a00c-98d9d3551293)
  ![image](https://github.com/user-attachments/assets/5d73be46-ac68-469c-a14d-9c011c456038)
  ![image](https://github.com/user-attachments/assets/a64e6582-2412-45f6-a108-61b1677128cf)

- Router - Router

  ![image](https://github.com/user-attachments/assets/f1a1a8c9-ac4b-4c69-b308-1ce3785c8cef)
  ![image](https://github.com/user-attachments/assets/59efd2d0-c901-4315-98bb-b8823a4cc1b2)

<br>

## CIDR

### Tree

- Tree image

  <img width="4888" alt="Tree" src="https://github.com/user-attachments/assets/788d0617-8242-41ce-9793-530bd0ea72a2">


- IP distribution table

  ![image](https://github.com/user-attachments/assets/96a35ed3-aaaa-445a-bedb-6c32193ac920)


### Subnet Merging Iteration

- Iteration 1

  ![image](https://github.com/user-attachments/assets/f33db28d-2114-4b42-869a-6855a019195d)

- Iteration 2

  ![image](https://github.com/user-attachments/assets/f870e133-b7fb-4be3-9698-4f222e98c53d)

- Iteration 3

  ![image](https://github.com/user-attachments/assets/b2d38096-98be-46dc-9e22-999dae61d9f7)

- Iteration 4

  ![image](https://github.com/user-attachments/assets/5a5fa7e9-6ba9-443b-b676-ede6b5ec7be4)

- Iteration 5

  ![image](https://github.com/user-attachments/assets/30014050-2b52-4d8b-8a47-f463e1cbf285)

- Iteration 6

  ![image](https://github.com/user-attachments/assets/ed261a99-8f50-46cf-8351-042d7a66df6a)

- Iteration 7

  ![image](https://github.com/user-attachments/assets/93f93bc1-8aa1-4887-aad6-8580a0b1b69f)

- Iteration 8

  ![image](https://github.com/user-attachments/assets/ea7fd7d9-ce5a-470e-bb69-512b3a1ec953)

### Subnetting (If you use CPT)

  ![image](https://github.com/user-attachments/assets/1c37db9c-93e0-482c-81d4-5a3e5b243a33)

  ![image](https://github.com/user-attachments/assets/3953d44d-5ddc-4396-a624-7741d29c4e1d)

### Routing

Configuration to every router for routing.

- Kamachi:

  ```
    Network 10.14.32.0
    Mask 255.255.254.0
    Next Hop 10.14.36.2
		
    Network 10.14.34.0
    Mask 255.255.255.224
    Next Hop 10.14.36.2
		
    Network 10.14.0.0
    Mask 255.255.248.0
    Next Hop 10.14.16.2

    Network 10.14.8.0
    Mask 255.255.248.0
    Next Hop 10.14.16.2
		
    Network 10.14.70.64
    Mask 255.255.255.252
    Next Hop 10.14.72.2

    Network 10.14.68.0
    Mask 255.255.255.252
    Next Hop 10.14.72.2

    Network 10.14.70.32
    Mask 255.255.255.252
    Next Hop 10.14.72.2
		
    Network 10.14.70.16
    Mask 255.255.255.252
    Next Hop 10.14.72.2

    Network 10.14.70.0
    Mask 255.255.255.240
    Next Hop 10.14.72.2

    Network 10.14.64.0
    Mask 255.255.254.0
    Next Hop 10.14.72.2
		
    Network 10.14.80.0
    Mask 255.255.254.0
    Next Hop 10.14.84.2
		
    Network 10.14.82.0
    Mask 255.255.255.128
    Next Hop 10.14.84.2

    Network 10.14.90.0
    Mask 255.255.255.252
    Next Hop 10.14.92.2
		
    Network 10.14.89.0
    Mask 255.255.255.252
    Next Hop 10.14.92.2

    Network 10.14.88.0
    Mask 255.255.255.128
    Next Hop 10.14.92.2
	
    Network 10.14.88.128
    Mask 255.255.255.224
    Next Hop 10.14.92.2
  ```

- Fiamma:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0
    Next Hop 10.14.36.1

    Network 10.14.34.0
    Mask 255.255.255.224
    Next Hop 10.14.32.3
  ```

- GoldenDawn:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0
    Next Hop 10.14.16.1
  ```

- Necessarius:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0
    Next Hop 10.14.72.1

    Network 10.14.64.0
    Mask 255.255.255.252
    Next Hop 10.14.68.2

    Network 10.14.70.32
    Mask 255.255.255.252
    Next Hop 10.14.70.66
		
    Network 10.14.70.16
    Mask 255.255.255.252
    Next Hop 10.14.70.66
	
    Network 10.14.70.0
    Mask 255.255.255.240
    Next Hop 10.14.70.66
  ```

- Alice:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0
    Next Hop 10.14.84.1

    Network 10.14.82.0
    Mask 255.255.255.128
    Next Hop 10.14.80.3
  ```

- Kihara:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0
    Next Hop 10.14.92.1

    Network 10.14.88.0
    Mask 255.255.255.128
    Next Hop 10.14.89.2

    Network 10.14.88.128
    Mask 255.255.255.224
    Next Hop 10.14.89.2
  ```

- Vento:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0
    Next Hop 10.14.32.1
  ```

- Coronzon:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0	
    Next Hop 10.14.70.65

    Network 10.14.70.0
    Mask 255.255.255.240
    Next Hop 10.14.70.18
  ```

- Index:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0
    Next Hop 10.14.70.17
  ```

- Gremlin:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0
    Next Hop 10.14.68.1
  ```

- LastOrder:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0
    Next Hop 10.14.80.1
  ```

- Accel:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0
    Next Hop 10.14.89.1

    Network 10.14.88.128
    Mask 255.255.255.224
    Next Hop 10.14.88.3
  ```

- Railgun:

  ```
    Network 0.0.0.0
    Mask 0.0.0.0
    Next Hop 10.14.88.1
  ```

### Testing

- Client - client

  ![image](https://github.com/user-attachments/assets/7416b3aa-95d7-4159-a528-ae33aa4f5a7d)

- Client - Server

  ![image](https://github.com/user-attachments/assets/29a18ed5-52d6-4ddd-b763-1e74cd7cd891)

- Client - Router

  ![image](https://github.com/user-attachments/assets/0ea010a7-87a3-4c76-9216-bcdae6da0527)

- Server - Server

  ![image](https://github.com/user-attachments/assets/5f2e4589-90ad-4036-a342-463412ab3649)

- Server - Router

  ![image](https://github.com/user-attachments/assets/5ff0dca8-0836-4610-a94c-fae62ff924cf)

- Router - Router

  ![image](https://github.com/user-attachments/assets/d7e8efa9-1dd3-4557-8858-dc763baddc55)

<br>
  
## Problems

<br>

## Revisions (if any)
