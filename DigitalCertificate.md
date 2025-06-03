##Obtaining The Digital Certificate

- access certbot.org and select Apache and Linux(snap)
- terminal codes (while in SSH):
  sudo snap install --classic certbot
  sudo ln -s /snap/bin/certbot /usr/bin/certbot
  sudo certbot certonly --apache
  
