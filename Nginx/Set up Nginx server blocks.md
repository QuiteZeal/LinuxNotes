# Set up Nginx server blocks
I recommend using a particular .conf file for every site.
For achieve that, we need add `include` into nginx.conf, such as:
```
include /etc/nginx/sites-enabled/*.conf;
```

## Create Diretory
```
sudo mkdir /etc/nginx/sites-available
sudo mkdir /etc/nginx/sites-enabled
```
You can edit yourname.conf in sites-available, and then link to site-enabled to recycle.
Just like this:
```
sudo ln -s /etc/nginx/sites-available/yourname.conf /etc/nginx/sites-enabled/yourname.conf
```

So that, when you change configure, you just need to edit yourname.conf under `sites-available`, and then restart Nginx.
