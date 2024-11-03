# Web Server Configuration Checklist

## 1. Web Server (Nginx) Status
```bash
# Check if nginx is running
sudo systemctl status nginx

# Enable nginx to start on boot
sudo systemctl enable nginx

# Test nginx configuration
sudo nginx -t
```

## 2. Port Configuration
```bash
# Verify nginx is listening on 443
sudo ss -tulpn | grep :443
```

## 3. SSL Certificates
- Location: typically `/etc/nginx/ssl/` or `/etc/ssl/`
- Required files:
  - `fullchain.pem` (domain + intermediate certificates)
  - `privkey.pem` (private key)

```nginx
# In nginx.conf or site configuration
server {
    listen 443 ssl;
    server_name yourdomain.com;
    
    ssl_certificate /path/to/fullchain.pem;
    ssl_certificate_key /path/to/privkey.pem;
}
```
*certificates are usually located at /etc/pki/ or /etc/ssl*

## 4. Firewall Configuration
```bash
# For firewalld (Fedora/RHEL)
sudo firewall-cmd --permanent --add-service=https
sudo firewall-cmd --permanent --add-port=443/tcp
sudo firewall-cmd --reload

# For UFW (Ubuntu/Debian)
sudo ufw allow https
sudo ufw allow 443/tcp
```

## 5. Testing
```bash
# Test SSL configuration
openssl s_client -connect yourdomain.com:443 -servername yourdomain.com

# Test port accessibility
nc -zv yourdomain.com 443
```

Remember to restart nginx after configuration changes:
```bash
sudo systemctl restart nginx
```
