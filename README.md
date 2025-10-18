# ⚙️ n8n + Ollama on Render

Este proyecto permite desplegar **n8n** y **Ollama** en [Render.com](https://render.com) usando contenedores Docker con almacenamiento persistente.

---

## 🧩 Estructura

| Servicio | Puerto | Descripción |
|-----------|---------|-------------|
| `n8n` | 5678 | Automatizador visual tipo Node-RED |
| `ollama` | 11434 | API local de modelos LLM (Llama, Mistral, etc.) |

---

## 🧠 Uso local

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

---

## 🧑‍💻 Autor

Proyecto base generado por FeithNoir