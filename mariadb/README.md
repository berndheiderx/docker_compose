# MariaDB Docker

## asdf

powershell

```

```


## Zugriff im Container
Wenn dein Container z. B. mariadb heißt:

```
docker exec -it mariadb mariadb -u root
```
Falls dein Root-Passwort leer ist, reicht das oft direkt. Wenn du ein Passwort gesetzt hast:

```
docker exec -it mariadb mariadb -u root -p
```

## Zugriff vom Host / WSL
Wenn du den Port in Compose auf den Host gemappt hast, z. B. 3306:3306, dann kannst du dich von WSL oder vom Windows-Host so verbinden:

```
mariadb -h 127.0.0.1 -P 3306 -u root
```
oder mit Passwort:

```
mariadb -h 127.0.0.1 -P 3306 -u root -p
```
MariaDB empfiehlt für Verbindungen von außen eine TCP-Verbindung; also 127.0.0.1/localhost mit Port, nicht einen Unix-Socket.
