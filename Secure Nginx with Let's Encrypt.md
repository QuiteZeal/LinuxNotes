# Secure Nginx with Let's Encrypt

We will use a little tool to do it.

## Get the certbor-auto

```

sudo curl -O https://dl.eff.org/certbot-auto

```

and mv it to the `/usr/local/bin`

```

sudo mv certbot-auto /usr/local/bin/certbot-auto

```

and then, give it permission to read and execute:

```

sudo chmod 0755 /usr/local/bin/certbot-auto

```

## Install Let's Encrypt

```

sudo /usr/local/bin/certbot-auto --nginx

```

If you use `xxx.conf` as a server block file's configure, the certbot will check it automatically.

### Manual renew

```

sudo /usr/local/bin/certbot-auto renew --dry-run

```
