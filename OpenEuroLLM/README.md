# Ollama mit OpenEuroLLM-German

## Anleitung 
https://ollama.com/jobautomation/OpenEuroLLM-German

### 1. Verzeichnis anlegen (oder unter "C:\Users\USERNAME\yaml\openeurollm")

```
mkdir -p ~/openeurollm
cd ~/openeurollm
```

anschließend entsprechende compose.yaml ablegen

### 2. Container starten

```
docker compose up -d
```

### 3. Modell pullen
```
docker exec -it ollama ollama pull jobautomation/OpenEuroLLM-German
```

### 4. Modell testen
Im Terminal
```
docker exec -it ollama ollama run jobautomation/OpenEuroLLM-German
```

Oder per API von außen (z.B. aus WSL)
```
curl http://127.0.0.1:11434/api/generate \
  -H "Content-Type: application/json" \
  -d '{"model":"jobautomation/OpenEuroLLM-German","prompt":"Hallo, wie geht es dir?","stream":false}'
```
Ollama bindet standardmäßig auf 127.0.0.1:11434, was du über die Umgebungsvariable OLLAMA_HOST ändern kannst, falls du es von anderen Containern erreichen willst.
(Siehe compose_network.yaml)

## compose_network.yaml

Um Ollama aus anderen Containern erreichbar zu machen, musst du OLLAMA_HOST=0.0.0.0:11434 setzen. Damit lauscht Ollama auf allen Netzwerkschnittstellen statt nur auf 127.0.0.1.

Andere Container verbinden sich dann mit
 - http://ollama:11434 (wenn sie im selben Docker-Netzwerk sind),
 - oder http://<host-ip>:11434 (wenn sie über das Host-Netzwerk zugreifen).

Wenn du auf dem Host selbst Ollama nutzt, musst du zusätzlich die Firewall für Port 11434 freigeben, falls aktiv.

