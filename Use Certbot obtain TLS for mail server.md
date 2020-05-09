# Use Certbot obtain TLS for mail server
**The key is:**
```
sudo /usr/local/bin/certbot --nginx --agree-tos --redirect --hsts --staple-ocsp --email your-email@name.com -d mail.your-domain.com
```
