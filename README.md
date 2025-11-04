# Docker Demo – .NET API + Vue.js

Prosty przykład pokazujący, jak uruchomić **backend (.NET 8 Web API)** i **frontend (Vue 3 + Vite)** w osobnych kontenerach Docker.

---

## Jak uruchomić?

```
1. Git bash:
git clone https://github.com/TymekSon/TestApp.git

2. Pobierz docker:
Pobierz instalator z oficjalnej strony: https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe

3. W terminalu:
sprawdź wersję: docker --version

4. W terminalu w folderze projektu:
docker-compose up --build

Frontend: http://localhost:8080
API: http://localhost:5000/api/weatherforecast