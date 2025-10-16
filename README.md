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

###  asus-linux.org

## Dual GPU switch , Power Profiles, Aura (luces del teclado)

[Guia para instalacion en Archlinux o CachyOS](https://asus-linux.org/guides/arch-guide/)
- guia de asuctl 
- guia de supergfxctl

### Known Problems

## nVidia Power Management

Crear: 

``` sudo touch /etc/modprobe.d/nvidia.conf 
sudo nvim /etc/modprobe.d/nvidia.conf 
```

Agregar:

```
options nvidia NVreg_PreserveVideoMemoryAllocations=1
options nvidia-drm modeset=1
options nvidia NVreg_DynamicPowerManagement=0x02
options nvidia NVreg_EnableS0ixPowerManagement=1
options nvidia NVreg_S0ixPowerManagementVideoMemoryThreshold=1024 

```
luego correr: 

```
sudo update-initramfs -u

```
Chequear:

```
cat /proc/driver/nvidia/gpus/0000:01:00.0/power

```

Tendrian que tener una salida asi:

<samp>
Runtime D3 status:          Enabled (fine-grained)
Video Memory:               Off

GPU Hardware Support:
 Video Memory Self Refresh: Supported
 Video Memory Off:          Supported

S0ix Power Management:
 Platform Support:          Supported
 Status:                    Enabled

Notebook Dynamic Boost:     Supported
</samp>





