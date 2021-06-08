# NGINX
Contains configuration or commands for Nginx web server.

## Installing NGINX
```zsh
# install nginx with apt
sudo apt install nginx
```

## Modifying NGINX welcome page
```zsh
# change the working dir
cd /var/www/html
# make a backup of nginx welcome page
sudo cp index.nginx-debian.html index.nginx-debian.html.0
# modifying the nginx welcome page
sudo vim index.nginx-debian.html
```

## NGINX Operation
```zsh
# stopping nginx
sudo systemctl stop nginx
# starting nginx
sudo systemctl start nginx
# restarting nginx
sudo systemctl restart nginx
# reloading nginx
sudo service nginx reload
# verifying or testing nginx configuration
sudo nginx -t
```

## Securing NGINX
1. Hiding NGINX version number
> we would want to hide the NGINX version number because, it is really important for the attacker to know the version number of NGINX in order to do some exploit.
```zsh
# changing the working dir to nginx dir
cd /etc/nginx
# making a backup of nginx.conf
sudo cp nginx.conf nginx.conf.0
# modifying nginx.conf to hide nginx version number
sudo vim nginx.conf
# then un-comment server_tokens off
# reload nginx
sudo service nginx reload
```
2. Making a custom error page
> by default error in NGINX web server tells a lot of information to the public, this could be beneficial for the attacker, so we make a custom file to change the default error page. see [error redirect line](error_redirect_line.txt).
```zsh
# 1. modify the default sites-available in nginx dir
sudo vim /etc/nginx/sites-available/default
# 2. add these lines that are provided above in the server directive
# 3. make your error file named 404.html in /usr/share/nginx/html/
sudo vim /usr/share/nginx/html/404.html
# 4. reload nginx
sudo service nginx reload
```

## Note
> Don't leave the default welcome page, technology that is powering the web server should not be shown, as it can tell the attacker to find the vulnerabilities for your server.  
You can test your SSL config using ssllabs.com