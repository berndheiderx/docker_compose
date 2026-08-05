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

## Mögliche Fehlermeldungen

# 

```
docker compose up -d
WARN[0000] /mnt/c/Users/bernd/yaml/mariadb/compose.yml: the attribute `version` is obsolete, it will be ignored, please remove it to avoid potential confusion
permission denied while trying to connect to the docker API at unix:///var/run/docker.sock
```

# Lösung

Was du tun solltest
Entferne die Zeile version: aus deiner compose.yml.

Prüfe, ob Docker läuft:

```
docker version
```

Prüfe die Rechte:
```
groups
```
Wenn docker nicht in der Ausgabe steht, füge deinen Benutzer zur Docker-Gruppe hinzu:

```
sudo usermod -aG docker $USER
newgrp docker
```
Falls du Docker Desktop unter Windows mit WSL nutzt, stelle sicher, dass WSL Integration für deine Ubuntu-Distribution aktiviert ist.

Danach erneut starten
```
docker compose up -d
```






