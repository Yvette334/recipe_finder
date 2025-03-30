 ## Recipe Exploree
 
A web app to discover recipes worldwide using TheMealDB API.

## Demo video:

## Features
 **Search & Save Favorite** recipes by name, ingredient,letter or region and can save to use later 
 **Detailed view** with cooking instructions  
 **Responsive** design for all devices  
 **Load balanced** deployment
  


## How to Use
1. Search by name like "pasta" or "chicken"
2. Search by ingredients
3. Search by Region
4. Search by letter A-Z
5. Click any recipe to see details
6. Heart icon saves favorites
7. Get random recipe
8. Access favorites from the sidebar

   ## Server Deployment Guide

### Deploying
- Ubuntu  servers (Web01, Web02, Lb01)
- SSH access to all servers
- Git installed on all servers

### Deploy to Web01 & Web02

# Connect to Web01
ssh username@web01_ip
ssh username@web02_ip

# Update system and install Nginx
sudo apt update && sudo apt upgrade -y
sudo apt install nginx git -y

# Add the files in the web servers
cd /var/www/html
sudo vim index.html
sudo vim styles.css
sudo vim script.js
sudo chown -R www-data:www-data /var/www/html

# Configure Nginx
sudo nano /etc/nginx/sites-available/default

### Deploy on Lb01

sudo apt update
sudo apt install haproxy -y
sudo nano /etc/haproxy/haproxy.cfg

## Configure HAProxy
frontend http_front
    bind *:80
    default_backend http_back

backend http_back
    balance roundrobin
    server web01	54.175.105.22:80 check  
    server web02 54.175.110.39:80 check
    
## HAProxy Status
    sudo systemctl status haproxy

## Github

https://github.com/Yvette334/recipe_finder.git 

# Open in browser
open web01_ip address
