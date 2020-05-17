# Set SSL for mail domain.
The key operation is use cerbot-auto:
`sudo /usr/local/bin/certbot --nginx --agree-tos --redirect --hsts --staple-ocsp --email you@mail.com -d mail.domain.com`

Notes:
```
- --nginx: Use the nginx plugin.
- --apache: Use the Apache plugin.
- --agree-tos: Agree to terms of service.
- --redirect: Force HTTPS by 301 redirect.
- --hsts: Add the Strict-Transport-Security header to every HTTP response. Forcing browser to always use TLS for the domain. Defends against SSL/TLS Stripping.
- --staple-ocsp: Enables OCSP Stapling. A valid OCSP response is stapled to the certificate that the server offers during TLS.
```
