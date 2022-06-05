# Baby-Monitor /-Phone

![babycam1](https://user-images.githubusercontent.com/61902639/172040013-4f7f03c0-b5ca-4cde-9fe8-233e38690191.jpeg)

![babycam4](https://user-images.githubusercontent.com/61902639/172040026-34df7361-f9d2-4e2c-9d98-550734a83264.jpeg)


## Hardware

- Raspi 3B
- Raspberry Pi Kamera Modul mit Automatik Infrarot-Sperrfilter https://www.amazon.de/gp/product/B07XTBQ1BN/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1
![babycam3](https://user-images.githubusercontent.com/61902639/172040022-5e536fb9-5341-4648-8a2e-def1946ea3d8.jpeg)

- USB Mikrofon https://www.amazon.de/gp/product/B091SVZM7T/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1 
![babycam2](https://user-images.githubusercontent.com/61902639/172040018-53a7c1e9-f228-4810-a68c-1bc372b0dc0a.jpeg)

- Schwanenhals https://www.amazon.de/gp/product/B09BJ8NCSS/ref=ppx_yo_dt_b_asin_title_o09_s00?ie=UTF8&th=1
- Raspi Case


## Installation

### Raspi

burn image on sd card (e.g with raspberry pi imager) → use Raspberry Pi OS Lite (32-bit)

add a "ssh" file to the image-folder (standard credentials are pi:raspberry)

insert ssd card, ethernet cable and power up the raspberry

check the ip address from your router

open a shell (e.g. powershell)

> ssh pi@ip.add.re.ss (e.g. ssh pi@192.168.1.3)

enter password

Do updates:

> sudo apt-get update -y

> sudo apt-get dist-upgrade -y


### RPi-Cam-Web-Interface

see: https://elinux.org/RPi-Cam-Web-Interface

> sudo raspi-config

> 3 Interface Options

> P1 Camera (→ enable and reboot)

> sudo apt-get install git

> git clone https://github.com/silvanmelchior/RPi_Cam_Web_Interface.git

> cd RPi_Cam_Web_Interface

> ./install.sh

### Icecast 2

see: https://wiki.ubuntuusers.de/Icecast2/
        
> sudo apt-get install icecast2

choose your configuration


### Darkice

see: https://wiki.ubuntuusers.de/Darkice/ 
        
> sudo apt-get install darkice

> sudo nano /etc/darkice.cfg

insert lines from file darkice.cfg (→ this repo!)

> crontab -e

> @reboot sleep 30 && /bin/darkice -c /etc/darkice.cfg


## TODO

- Cablemanagement

- Better Mount for the PiCam
