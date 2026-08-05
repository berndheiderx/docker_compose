# docker_compose

## WSL2 & Ubuntu unter Windows installieren

powershell

```
wsl --install
(Installiert die aktuell empfohlene Ubuntu-Version)
wsl --install -d <Distribution>
(Installiert die angegebene Distribution und Version)
```
Status prüfen

```
wsl --status
```

## Login Ubuntu in WSL
```
wsl -d Ubuntu
```

## Docker in Ubuntu (unter WSL2) installieren

```
https://daniel.es/blog/how-to-install-docker-in-wsl-without-docker-desktop/
```
```
https://docs.docker.com/engine/install/ubuntu/
```

Prüfen ob Docker läuft

```
sudo systemctl status docker
```

Falls nicht, Docker starten

```
sudo systemctl start docker
```

## WICHTIG!!!: Oft ist ein Neustart des Systems notwendig, damit Container gestartet werden können

## Ausführen von Compose-Dateien

### Navigation Ordner compose.yaml

```
cd /mnt/c/Users/USERNAME/yaml/ORDNERNAME
```

### Ausführen Docker Container

```
docker compose up -d
```
compose (gilt nur wenn eine compose.yaml Datei im Verzeichnis exisitiert) kann z.B. durch einen spezifischen Dateinamen wie compose_mariadb.yaml ersetzt werden

### Status prüfen ###
```
docker compose ps
```

### Logs ansehen ###
```
docker compose logs -f
```

## Docker Stoppen oder Entfernen ##
Stoppen
```
docker compose stop
```

Entfernen
```
docker compose down
```









