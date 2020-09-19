# Pi-hole-met-display

In deze repository vind je alle informatie en handleidingen om je Raspberry Pi zero W(H) te configureren om Pi-hole te installeren en gebruiken in combinatie met de waveshare 2.13" e-ink display.  

Productlijst: https://neuralis.ai/?product=pi-hole-kit
  
# Raspberry pi zero W  
Gebruik de raspberry pi imager (https://www.raspberrypi.org/downloads/)  
om raspbian lite te installeren op een SDkaart van minimum 8GB  
Na het inloggen gebruik je het commando  
`raspi-config`
Om je wifi instellingen in te vullen

# Pi-hole  
Automatische installatie:  
`curl -sSL https://install.pi-hole.net | bash`

Handmatige installatie:  
`wget -O basic-install.sh https://install.pi-hole.net`  
`sudo bash basic-install.sh`  

# Display
  
Installeer de requirements voor de display:  
`sudo apt install python-pip`  
`cd ~`  
`wget http://kottke.org/plus/type/silkscreen/download/silkscreen.zip`  
`unzip silkscreen.zip`  
`sudo pip3 install requests`  
  
Download de files om de statistieken te tonen op de display:  
`git clone https://github.com/Neuralis-AI/Pi-hole-met-display.git`  
`cd /home/pi/Pi-hole-met-display/display`  
`sudo chmod +x stats.py`  
`sudo apt-get update`  
`sudo apt-get install python3-pip`  
`sudo apt-get install python3-pil`  
`sudo apt-get install python3-numpy`  
`sudo pip3 install RPi.GPIO`  
  
Zorg dat de statistieken weergeven bij het opstarten:  
`sudo crontab -e`  
Voeg volgende regel toe:  
`@reboot /home/pi/Pi-hole-met-display/display/stats.py`  

Gebruik raspi-config om SPI in te schakelen.
  
Herstart de pi om de informatie op de display te tonen.  

Om Pi-hole zelf te configureren volg je de gids hier: https://www.vice.com/nl/article/ep4bwm/pi-hole-adblock
