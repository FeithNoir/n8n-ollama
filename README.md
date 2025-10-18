# ⚙️ n8n + Ollama on Render

Este proyecto permite desplegar **n8n** y **Ollama** en [Render.com](https://render.com) usando contenedores Docker con almacenamiento persistente.

---

## 🧩 Estructura

| Servicio | Puerto | Descripción |
|-----------|---------|-------------|
| `n8n` | 5678 | Automatizador visual tipo Node-RED |
| `ollama` | 11434 | API local de modelos LLM (Llama, Mistral, etc.) |

---

## 🚀 Despliegue en Render

1. Crea una cuenta en [Render.com](https://render.com).
2. Sube este proyecto a GitHub o GitLab.
3. En Render Dashboard → **New + → Blueprint**.
4. Selecciona este repositorio (Render detectará el archivo `render.yaml`).
5. Configura tus variables de entorno cuando Render lo solicite:
   - `N8N_BASIC_AUTH_USER`
   - `N8N_BASIC_AUTH_PASSWORD`
   - `N8N_ENCRYPTION_KEY`
6. Espera a que Render cree ambos servicios (`n8n` y `ollama`).

✅ Una vez desplegado:
- Accede a `https://n8n.onrender.com`
- Ollama responderá desde `https://ollama.onrender.com`

---

## 🧠 Uso local (opcional)

Si quieres probarlo antes:

```bash
cp .env.example .env
docker compose up -d
````

Luego abre:

* `http://localhost:5678` (n8n)
* `http://localhost:11434` (Ollama)

---

## 💾 Persistencia

Render mantiene datos entre reinicios gracias a los discos definidos en `render.yaml`:

* `/home/node/.n8n` → flujos y credenciales.
* `/root/.ollama` → modelos descargados.

---

## 🧰 Tecnologías

* **n8n:** Automatización de workflows.
* **Ollama:** Modelos de lenguaje locales.
* **Docker Compose / Render Blueprint:** Orquestación simple y moderna.

---

## 🧑‍💻 Autor

Proyecto base generado por FeithNoir