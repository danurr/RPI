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
- `cd /home/pi/.homebridge/`

   `sudo nano config.json` //modificare file secondo necessità
- `sudo nano /etc/rc.local`
    - incollare nella riga prima di exit 0 la seguente stringa:
    
      `su -c "screen -dmS homebridge homebridge" -s /bin/sh pi`
      
      `sudo reboot now`  //per verificare che tutto funzioni
- `sudo nano /start` //This command opens nano and allows you to edit the start script. Add the following lines:

    - `sudo forever stopall`
    
      `cd /home/pi/HAP-NodeJS`
      
      `sudo forever start BridgedCore.js`

    Change BridgedCore.js to Core.js if you are using Core.js.

    If you are ONLY using CameraCore.js, change BridgedCore.js to CameraCore.js.

    Add this additional line at the end if you are using CameraCore.js alongside Core/BridgedCore.js:

    `sudo forever start CameraCore.js`

    Once you are done, save the file and exit nano.
