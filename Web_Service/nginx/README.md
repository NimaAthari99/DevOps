**Sample Nginx File Config:**
```bash
server {
    listen 80 default_server;       # Only one site on a server can be "default_server"
    listen [::]:80 default_server;  # Only one site on a server can be "default_server"
    server_name store.nima.local;
    # Add index.php to list if you are using PHP
```

### **Basic Location Block**
```bash
    location / {
        root /var/www/html/store;
        index index.html;
    }
    error_page 404 /404.html;
    location = /404.html {
        internal;
    }
    error_page 500 502 503 504 /50x.html;
    location = /50x.html {
        internal;
    }
```

### **Specific Path Location**
```bash
    location /images/ {
        root /var/www/media;
    }
```
### **Exact Match Location**
```bash
    location = /favicon.ico {
        log_not_found off;
        access_log off;
        autoindex on;      
    }
```
### **Redirect with try_files**
```bash
    location / {
        try_files $uri $uri/ /index.html;
    }
```
### **Proxy Pass to Backend Server**
```bash
    location /api/ {
        proxy_pass http://backend_server;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
```
### **Location with Basic Authentication**
```bash
    location /admin/ {
        auth_basic "Restricted Content";
        auth_basic_user_file /etc/nginx/.htpasswd;
    }
}
```

**Description:**
  - `server { ... }`: The server block defines a virtual server. It contains directives and nested blocks that configure how Nginx handles requests for a specific domain or IP address.
  - `listen 80;`: This directive tells Nginx to listen on port 80, which is the default port for HTTP traffic. You can change this to another port number if needed.
  - `server_name example.com www.example.com;`: This directive specifies the domain names that this server block will respond to. Requests for example.com and www.example.com will be handled by this server block.
  - `location / { ... }`: The location block defines how requests for specific URIs (Uniform Resource Identifiers) are processed.
  - `location / { ... }`: This location block matches all URIs that start with / (i.e., it matches all requests).
  - `root /var/www/html;`: This directive specifies the root directory for the location block. Nginx will look for files in this directory when processing requests.
  - `index index.html index.htm;`: This directive defines the index files that Nginx will look for when a directory is requested. If a user requests http://example.com/, Nginx will try to serve index.html or index.htm from the root directory.
  - `error_page 404 /404.html;`: This directive specifies a custom error page for 404 Not Found errors. When a requested resource is not found, Nginx will serve the /404.html file.
  - `location = /404.html { ... }`: This location block matches the exact URI /404.html.
  - `internal;`: This directive makes the location internal, meaning it cannot be directly requested by a client. It's used only for serving the error page.
  - `error_page 500 502 503 504 /50x.html;`: This directive specifies a custom error page for server errors (500, 502, 503, 504). When one of these errors occurs, Nginx will serve the /50x.html file.
  - `location = /50x.html { ... }`This location block matches the exact URI /50x.html.
  - `internal;`: This directive makes the location internal, meaning it cannot be directly requested by a client. It's used only for serving the error page.
  - `root /var/www/default;`: This directive specifies the root directory for the server block. Nginx will look for files in this directory when processing requests.
  - `listen 443 ssl default_server;`: This directive tells Nginx to listen on port 443 for HTTPS traffic and to designate this server block as the default server for HTTPS.
  - `ssl_certificate /etc/nginx/ssl/default.crt;`: This specifies the path to the SSL certificate.
  - `ssl_certificate_key /etc/nginx/ssl/default.key;`: This specifies the path to the SSL certificate key.
  
[**Basic Location Block**](#basic-location-block)
  - `location / { ... }`: This matches all URIs that start with / (i.e., it matches all requests).
  - `root /var/www/html;`: Specifies the root directory for this location block.
  - `index index.html index.htm;`: Specifies the index files to look for when a directory is requested.

  [**Specific Path Location**](#specific-path-location)
  - `location /images/ { ... }`: This matches URIs that start with `/images/`.
  - `root /var/www/media;`: Specifies the root directory for this location block. Requests to `/images/` will be served from `/var/www/media/images/`.

[**Exact Match Location**](#exact-match-location)
  - `location = /favicon.ico { ... }`: This matches exactly the URI /favicon.ico.
  - `log_not_found off;`: Disables logging of not found errors for this location.
  - `access_log off;`: Disables access logging for this location.

[**Redirect with try_files**](#redirect-with-try_files)
  - `location / { ... }`: This matches all URIs that start with /.
  - `try_files $uri $uri/ /index.html;`: This directive tries to serve the requested URI as a file, then as a directory. If neither exists, it serves `/index.html`.

[**Proxy Pass to Backend Server**](#proxy-pass-to-backend-server)
  - `location /api/ { ... }`: This matches URIs that start with /api/.
  - `proxy_pass http://backend_server;`: Forwards requests to the backend server (replace backend_server with the actual backend server address).
  - `proxy_set_header ...;`: Sets headers to pass along with the proxied request.
  - `proxy_set_header Host $host;`: Sets the Host header in the proxied request to the value of the original Host header.
  - `proxy_set_header X-Real-IP $remote_addr;`: Passes the client's IP address to the backend server.
  - `proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;`: Adds the client's IP address to the X-Forwarded-For header.
  - `proxy_set_header X-Forwarded-Proto $scheme;`: Passes the original request scheme (http or https) to the backend server.

[**Location with Basic Authentication**](#location-with-basic-authentication)
  - `location /admin/ { ... }`: This matches URIs that start with /admin/.
  - `auth_basic "Restricted Content";`: Enables basic authentication with the specified realm name.
  - `auth_basic_user_file /etc/nginx/.htpasswd;`: Specifies the password file for basic authentication.

