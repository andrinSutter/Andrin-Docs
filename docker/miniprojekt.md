# MiniProjekt

## Webserver mit Node.js & Docker

### 📝 Projektbeschreibung

Dieses Projekt enthält ein Docker-Image, das auf einem Node.js-Image basiert und eine einfache statische Webseite über Express.js bereitstellt. Die Webseite ist über Port **8080** erreichbar und unterstützt **Volume-Mounts** für Weiterentwicklung und Logging.

***

### 📁 Projektstruktur

.\
├── Dockerfile\
├── server.js\
├── src/\
│ └── index.html (und weitere statische Dateien)\
├── logs/\
│ └── access.log (wird automatisch erstellt)

***

### 🔧 Dockerfile

```dockerfile
FROM node:18
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 8080
CMD [ "node", "server.js" ]
```

### 📄 server.js (Kurzfassung)

* Stellt Dateien aus `src/` statisch zur Verfügung
* Schreibt Zugriffslogs in `logs/access.log` via `morgan`
* Hört auf `http://0.0.0.0:8080`

***

### 🚀 Build & Run

#### 1. Image erstellen:

```bash
docker build -t dockerfile_miniprojekt .
```

#### 2. Container starten mit Volumes:

```bash
docker run --rm --name webserver \
  -p 8080:8080 \
  -v $(pwd)/src:/usr/src/app/src \
  -v $(pwd)/logs:/usr/src/app/logs \
  dockerfile_miniprojekt
```

***

### ✅ Tests zur Funktionsprüfung

| Test                                      | Erwartung                     |
| ----------------------------------------- | ----------------------------- |
| `http://localhost:8080` im Browser öffnen | Webseite wird angezeigt       |
| Änderung an `src/index.html`              | Wird sofort sichtbar          |
| `cat logs/access.log`                     | Zugriff wird geloggt          |
| `docker ps`                               | Container läuft auf Port 8080 |
| Image basiert auf `node:18`               | Ja (siehe Dockerfile)         |

***

### 📦 Abhängigkeiten

* Node.js (Image: `node:18`)
* Express
* Morgan (für Logging)
