# RPI
- impostare wifi + indirizzo ip fisso con: 
    - `sudo nano /etc/dhcpcd.conf`
      - interface wlan0
      - static ip_address=192.168.0.2/24
      - static routers=192.168.0.1
      - static domain_name_servers=192.168.0.1
- REBOOT
- `ip a` //Per verificare che tutto sia a posto
- `sudo apt update && sudo apt upgrade && sudo apt dist-upgrade`
- `curl -sSL https://raw.githubusercontent.com/danurr/RPI/master/installHB | bash`
- `cd /home/pi/.homebridge/

   sudo nano config.json`
