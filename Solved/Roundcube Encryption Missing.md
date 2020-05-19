# Problem: Roundcube Encryption Missing
I want to use a password plugin in the Roundcube webmail, and meantime I use a virtual mailbox.
So the solution is to add `yourpath/roundcube/plugins/password/config.inc.php`

## Connect to the local MySQL
The format is:
```
$config['password_db_dsn'] = 'mysql://user:passwd@127.0.0.1/database';
```


## Solve the "Encryption Missing"
```
$config['password_query'] = "UPDATE mailbox SET password=CONCAT('{PLAIN-MD5}', MD5(%p)),modified=NOW() WHERE username=%u LIMIT 1";
```
