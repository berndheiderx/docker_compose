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

## Beispiel: MariaDB‑11.5‑Container erstellen

### MariaDB‑Client nutzen
