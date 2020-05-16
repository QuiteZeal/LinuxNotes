# Generating SSL/TLS Certificate and Private Key
Here we will use OpenSSL.
## Creat Files
Normally, we will built a private file, like this:
```
mkdir /etc/ssl/private/
```
## Create New One
```
openssl req -x509 -nodes -keyout /etc/ssl/private/yourname.pem -out /etc/ssl/private/yourname.pem -days 365 -newkey rsa:2048
```
or
```
openssl req -x509 -nodes -keyout /etc/ssl/private/yourname.key -out /etc/ssl/private/yourname.crt -days 365 -newkey rsa:2048
```
**But the second way need `cat` to get`.pem`.**
>
- req – is a command for X.509 Certificate Signing Request (CSR) management.
- x509 – means X.509 certificate data management.
- days – defines a number of days certificate is valid for.
- newkey – specifies certificate key processor.
- rsa:2048 – RSA key processor, will generate a 2048 bit private key.
- keyout – sets the key storage file.
- out – sets the certificate storage file, note that both certificate and key are stored in the same name

## Renew
You can delete old `.crt` and use `Create New Onw`way to create new `.crt`.
Or you can do this:
**If you have no key:**
```
openssl req -new -newkey rsa:2048 -keyout yourname.key -out yourname.csr
```
**If you have a key:**
```
openssl req -new -key yourname.key -out yourname2.csr
```
This will be `.csr`, but it can convert to `.crt`, like this:
```
openssl x509 -req -in yourname.csr -days 365 -signkey yourname.key -out yourname.crt
```
You can set days to 3650 or longer.
