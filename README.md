# nginx-setup

# Install Ngnix 

       sudo apt update
       sudo apt install nginx
       
# Configure Nginx

        nano  /etc/nginx/sites-available/<yourdomin.extension>
# Update Congiuration File

    server {
    listen 80;
    server_name <yourdomain name>;

    location / {
        proxy_pass http://localhost:<your running Port>;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}

# Enable Your Site Configuration

     sudo ln -s /etc/nginx/sites-available/<your domain name> /etc/nginx/sites-enabled/

# Test NGINX Configuration

      sudo nginx -t
# Restart NGINX:

     sudo systemctl restart nginx




