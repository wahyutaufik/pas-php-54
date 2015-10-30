# pas-php-54

Run php5 with pas

Run :
```
$ git clone https://github.com/wahyutaufik/pas-php-54
$ cd pas-php-54
$ pas up
```

Access to container:
```
$ docker exec -ti php54-nginx-0 bash
```

Still bugs on running php.
Fix it by run
```
docker exec -ti php54-nginx-0 service php5-fpm restart
```