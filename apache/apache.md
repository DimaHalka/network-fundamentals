# Tried on Ununtu 24.04

'''
sudo apt install apache2 -y
sudo systemctl status apache2
sudo systemctl restart apache2

sudo sed -i 's/^\s*Listen\s\+80$/Listen 10000/' /etc/apache2/ports.conf
# i - in-place, s - substitute, regexp/substitution string/

curl -I http://192.168.64.2:80/
curl -I http://192.168.64.2:10000/

/var/www/html/index.html
'''
