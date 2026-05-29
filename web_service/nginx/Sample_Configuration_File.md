server {
    listen 80 default_server;       # Only one site on a server can be "default_server"
    # listen [::]:80 default_server;

    server_name web1.nima.local;

    root /var/www/html/web1;

    # Add index.php to list if you are using PHP
    index index.html index.htm index.nginx-debian.html;

    location / {
        try_files $uri $uri/ =404;
    }

    autoindex on;

}

server {
    listen 80;
    server_name SUBDOMAIN.DOMAIN.TLD;   # Change `SUBDOMAIN.DOMAIN.TLD` with  your url; Mine here is mysite.domain.local
    root /PATH_TO_YOUR_STATIC_PAGE;     # Change `/PATH_TO_YOUR_STATIC_PAGE` with yours; Mine is /var/www/html/mysite.html
    autoindex on;

    location / {
        auth_basic "Administrator's Area";
        auth_basic_user_file /PATH_TO_YOUR_.HTPASSWD_FILE;       # Change `/PATH_TO_YOUR_.HTPASWD_FILE` with  your `.htpasswd` file; Mine here is `/etc/nginx/conf.d/mysite.htpasswd`.
        try_files $uri $uri/ =404;
    }
}

# Wordpress With Nginx
server {
    listen 443 ssl;
    server_name wordpress.domain.ir;
    ssl_certificate /etc/letsencrypt/live/mysite.domain.ir/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/mysite.domain.ir/privkey.pem;

    location / {
        proxy_pass http://127.0.0.1:8080;
        proxy_set_header HOST $http_host; #required for docker client's sake
        proxy_set_header X-Real-IP $remote_addr; #pass on real client's ip
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        add_header X-Powered-By "Nima Athari | domain.ir"; #For more info
    }
}
server {
    listen 80;
    server_name wordpress.domain.ir;
    return 301 https://$host$request_uri;
}