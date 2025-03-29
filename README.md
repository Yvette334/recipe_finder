 Recipe Exploree
 
A web app to discover recipes worldwide using TheMealDB API. 

## Features
 **Search** recipes by name, ingredient, or region  
 **Save favorites** (works offline)  
 **Detailed view** with cooking instructions  
 **Responsive** design for all devices  
 **Load balanced** deployment  

## How to Use
1. Search for recipes like "pasta" or "chicken"
2. Click any recipe to see details
3. Heart icon saves favorites
4. Access favorites from the sidebar

   ## Server Deployment Guide

### Prerequisites
- Ubuntu 20.04/22.04 servers (Web01, Web02, Lb01)
- SSH access to all servers
- Git installed on all servers

### Step 1: Deploy to Web01
```bash
# Connect to Web01
ssh username@web01_ip
ssh username@web02_ip

# Update system and install Nginx
sudo apt update && sudo apt upgrade -y
sudo apt install nginx git -y

# Clone repository
sudo git clone https://github.com/yourusername/recipe-explorer.git /var/www/recipes
sudo chown -R www-data:www-data /var/www/recipes

# Configure Nginx
sudo nano /etc/nginx/sites-available/recipes

## Installation
```bash
https://github.com/Yvette334/recipe_finder.git

# Open in browser
open web01_ip address
