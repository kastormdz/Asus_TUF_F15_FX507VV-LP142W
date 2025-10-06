# Asus TUF Gaming F15 Model FX507VV-LP142W

![F15](/images/asus_tuf_f15.jpg)

### Specs

- Procesador: 
Intel® Core™ i7-13620H de 13.ª generación, 2,4 GHz (caché de 24 M, hasta 4,9 GHz, 10 núcleos: 6 núcleos P y 4 núcleos E)
- Gráficos: 
GPU para laptops NVIDIA® GeForce RTX™ 4060, 2420MHz* at 140W (2370MHz Boost Clock+50MHz OC, 115W+25W Dynamic Boost)
- Pantalla: 
15,6", FHD (1920 x 1080) 16:9, IPS, Antideslumbrante, sRGB:100%, Refresh 144Hz, G-Sync, MUX Switch + NVIDIA® Advanced Optimus
- Memoria: 
16GB DDR5 4800 SO-DIMM, Admite memoria de doble canal
- Puertos:
Ports:
1x Thunderbolt 4, 1x USB 3.2 Gen 2 Type-C, 2x USB 3.2 Gen 1 Type-A, 1x HDMI 2.1
- Storage:
1TB PCIe 4.0 NVMe M.2 SSD


### Known Problems

- Brillo:  no se puede controlar el brillo ni con las teclas de hardware, ni usando ninguna utilidad, ni tirando nros al /sys/class/backlight/
 La unica solucion a esto es agregar a la linea de boot del kernel: 
 ```
 acpi_backlight=native
 ```

- Ethernet Controller  up/down

 ```
sudo pacman -S r8168
 ```
```
sudo rmmod r8169
 ```

```
sudo modprobe r8168
 ```
```
sudo echo "blacklist r8169" > /etc/modprobe.d/r8169_blacklist.conf 
 ```










