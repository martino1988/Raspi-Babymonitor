# Baby-Monitor

## Hardware

- Raspi 3B
- Raspberry Pi Kamera Modul mit Automatik Infrarot-Sperrfilter
- USB Mikrofon
- Schwanenhals
- Raspi Case


## Installation

### RPi-Cam-Web-Interface

sudo apt-get update
sudo apt-get dist-upgrade
sudo apt-get install git
git clone https://github.com/silvanmelchior/RPi_Cam_Web_Interface.git
cd RPi_Cam_Web_Interface
./install.sh

### Icecast 2

        
sudo apt-get install icecast2

> choose your configuration


### Darkice

        
sudo apt-get install darkice

sudo nano /etc/darkice.cfg
> siehe darkice.cfg

crontab -e

@reboot sleep 30 && /bin/darkice -c /etc/darkice.cfg



