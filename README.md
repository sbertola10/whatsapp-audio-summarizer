# 🎙️ WhatsApp Audio Summarizer (Groq + DeepSeek)

Este proyecto es una herramienta de productividad diseñada para resumir audios largos de WhatsApp de forma automática. Utiliza una arquitectura asíncrona para procesar el audio mediante **IA de alto rendimiento**, devolviendo un resumen estructurado directamente al chat.

## ✨ Características

* **Velocidad Extrema:** Transcripción mediante **Groq (Whisper-large-v3-turbo)** utilizando aceleración LPU.
* **Inteligencia de Vanguardia:** Resúmenes generados por **DeepSeek-V3**, optimizados para detectar puntos clave y tareas pendientes.
* **Arquitectura No Bloqueante:** Implementación de *multithreading* en Flask para evitar timeouts en la API de Twilio.
* **Manejo de Mensajes Largos:** Sistema automático de fragmentación (*chunking*) para resúmenes que exceden los 1600 caracteres de la API de Twilio.

---

## 🛠️ Stack Tecnológico

| Componente | Tecnología | Rol |
| :--- | :--- | :--- |
| **Backend** | Python 3.10+ / Flask | Servidor y Webhook |
| **Gateway** | Twilio WhatsApp API | Interfaz de mensajería |
| **Transcripción**| Groq (Whisper) | Audio a Texto (Latencia ultra-baja) |
| **LLM** | DeepSeek-V3 | Procesamiento de lenguaje y resumen |
| **Infraestructura**| Render / Gunicorn | Despliegue y servidor de producción |

---

## 🚀 Instalación y Configuración

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/tu-usuario/whatsapp-audio-summarizer.git](https://github.com/tu-usuario/whatsapp-audio-summarizer.git)
   cd whatsapp-audio-summarizer
   pip install -r requirements.txt
2. Variables de Entorno (Secrets)
Configura las siguientes llaves en tu panel de control de Render/Railway:

TW_SID: Account SID de Twilio.
TW_TOKEN: Auth Token de Twilio.
TW_WHATSAPP: Número del Sandbox (ej: whatsapp:+14155238886).
GROQ_KEY: API Key de Groq Cloud.
DEEPSEEK_KEY: API Key de DeepSeek.

📦 Despliegue en Producción
Este repositorio está optimizado para Render o servicios similares:

Build Command: pip install -r requirements.txt

Start Command: gunicorn app:app

Nota Técnica: El proyecto utiliza la carpeta /tmp/ para el almacenamiento temporal de audios, garantizando compatibilidad con sistemas de archivos de "solo lectura" típicos en entornos cloud.

⚖️ Licencia
Este proyecto está bajo la Licencia MIT. Siéntete libre de usarlo, modificarlo y adaptarlo a tus necesidades.
   
