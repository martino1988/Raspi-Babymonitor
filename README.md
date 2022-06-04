# Baby-Monitor

## Hardware

- Raspi 3B
- Raspberry Pi Kamera Modul mit Automatik Infrarot-Sperrfilter https://www.amazon.de/gp/product/B07XTBQ1BN/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1
- USB Mikrofon https://www.amazon.de/gp/product/B091SVZM7T/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1 
- Schwanenhals https://www.amazon.de/gp/product/B09BJ8NCSS/ref=ppx_yo_dt_b_asin_title_o09_s00?ie=UTF8&th=1
- Raspi Case


## Installation

### RPi-Cam-Web-Interface

https://elinux.org/RPi-Cam-Web-Interface

> sudo apt-get update -y

> sudo apt-get dist-upgrade -y

> sudo apt-get install git

> git clone https://github.com/silvanmelchior/RPi_Cam_Web_Interface.git

> cd RPi_Cam_Web_Interface

> ./install.sh

### Icecast 2

        
> sudo apt-get install icecast2

choose your configuration


### Darkice

        
> sudo apt-get install darkice

> sudo nano /etc/darkice.cfg

goto darkice.cfg

> crontab -e

> @reboot sleep 30 && /bin/darkice -c /etc/darkice.cfg



