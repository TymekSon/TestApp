# Docker Demo – .NET API + Vue.js

Prosty przykład pokazujący, jak uruchomić **backend (.NET 8 Web API)** i **frontend (Vue 3 + Vite)** w osobnych kontenerach Docker.

---

## Jak uruchomić?

```
Git bash:
git clone https://github.com/TymekSon/TestApp.git

W terminalu w folderze projektu:
docker-compose up --build

Frontend: http://localhost:8080
API: http://localhost:5000/api/weatherforecast