# Raspberry Pi - Babymonitor/-phone


| Front | Side |
|-------|------|
|![babycam1](https://user-images.githubusercontent.com/61902639/172040572-5bb46e1d-3c01-4d3f-98ee-c4551884002e.jpeg)|![babycam1-1](https://user-images.githubusercontent.com/61902639/172040577-d43f8e8b-5ef7-4340-8689-dc6cfc5b4335.jpeg)|



| Camview | Streamserver |
|-------|------|
|![Bildschirmfoto vom 2022-06-05 09-46-42](https://user-images.githubusercontent.com/61902639/172041158-917c207b-0e07-4759-bf35-0cacbb34e6d7.png)|![Bildschirmfoto vom 2022-06-05 09-55-22(2)](https://user-images.githubusercontent.com/61902639/172042326-8f92bdaa-fdae-462f-ae0c-592cbfa634f9.png)|


## Hardware

- Raspi 3B
- Raspberry Pi Kamera Modul mit Automatik Infrarot-Sperrfilter https://www.amazon.de/gp/product/B07XTBQ1BN/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1
![babycam3](https://user-images.githubusercontent.com/61902639/172040283-d765b65c-48cf-4e38-ba95-5d5d8fbfec75.jpeg)

- USB Mikrofon https://www.amazon.de/gp/product/B091SVZM7T/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1 
![babycam2](https://user-images.githubusercontent.com/61902639/172040271-503b0f4b-3235-48ce-8709-869b71f000a2.jpeg)

- Schwanenhals https://www.amazon.de/gp/product/B09BJ8NCSS/ref=ppx_yo_dt_b_asin_title_o09_s00?ie=UTF8&th=1
- Raspi Case


## Installation

### Raspi

burn image on sd card (e.g with raspberry pi imager) → use Raspberry Pi OS Lite (32-bit)

add a "ssh" file to the image-folder (standard credentials are pi:raspberry)

insert SSd Card, Ethernet-Cable, PiCam, Mic and power up the Raspi

check the ip address from your router

open a shell (e.g. powershell)

```bash
ssh pi@ip.add.re.ss (e.g. ssh pi@192.168.1.3)
```

enter password

Do updates:

```bash
sudo apt-get update && sudo apt-get dist-upgrade -y
```

### RPi-Cam-Web-Interface

see: https://elinux.org/RPi-Cam-Web-Interface

```bash
sudo raspi-config
```

> 3 Interface Options

> P1 Camera (→ enable and reboot)

```bash
sudo apt-get install git

git clone https://github.com/silvanmelchior/RPi_Cam_Web_Interface.git

cd RPi_Cam_Web_Interface

./install.sh
```

### Icecast 2

see: https://wiki.ubuntuusers.de/Icecast2/

```bash
sudo apt-get install icecast2
```
        
choose your configuration


### Darkice

see: https://wiki.ubuntuusers.de/Darkice/ 

```bash
sudo apt-get install darkice

sudo nano /etc/darkice.cfg
```

insert lines from file darkice.cfg (→ this repo!)

Darkice doesn't start at boot like icecast, so create a cronjob:

```bash
crontab -e
```

instert at bottom:

``` bash
@reboot sleep 30 && /bin/darkice -c /etc/darkice.cfg
```

### Latency

see: https://icecast.org/docs/icecast-2.4.1/config-file.html#limits

By default, the audio stream has an 8 to 10 second delay (caused by several components). To reduce this to a maximum of 2 - 3 seconds, you can reduce the burst size on the icecast server:

open icecast config file:

```bash
sudo nano /etc/icecast2/icecast.xml
```

```xml
        <limits>
                ...
                <!--<burst-size>65536</burst-size>-->
                <burst-size>16</burst-size>
        </limits>
```


## TODO

- Cablemanagement

- Better Mount for the PiCam
