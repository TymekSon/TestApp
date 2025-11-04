# Docker Demo – .NET API + Vue.js

Prosty przykład pokazujący, jak uruchomić **backend (.NET 8 Web API)** i **frontend (Vue 3 + Vite)** w osobnych kontenerach Docker.

---

## Jak uruchomić?

```bash
git clone <twoje-repo>
cd my-docker-demo
docker-compose up --build

Frontend: http://localhost:8080
API: http://localhost:5000/api/weatherforecast