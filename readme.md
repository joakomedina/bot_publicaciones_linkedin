# Bot de Publicaciones para LinkedIn

Este proyecto automatiza la generación de contenido para LinkedIn utilizando inteligencia artificial, generando textos, imágenes y un formulario interactivo que permite seleccionar las opciones deseadas antes de publicar.

---

## Descripción del Proyecto

El flujo completo permite:

1. Recibir un tema o mensaje vía Telegram.
2. Generar varias propuestas de textos y imágenes relacionadas con el tema.
3. Mostrar un formulario web donde el usuario puede seleccionar los textos e imágenes que más le gusten.
4. Crear la publicación final lista para LinkedIn.

Está pensado para el sector **retail y lujo**, pero es fácilmente adaptable a otros sectores.

---

## Arquitectura del Proyecto

El proyecto se divide en **tres flujos principales**:

1. **Generación de contenido**
   - Recibe el mensaje de Telegram.
   - Usa OpenAI y Perplexity para generar textos e imágenes.
   - Almacena los resultados en la base de datos PostgreSQL.

2. **Formulario web**
   - Muestra los textos e imágenes generadas.
   - Permite al usuario seleccionar las opciones que desea publicar.
   - Almacena las selecciones en la base de datos.

3. **Generación de la publicación final**
   - Combina los textos e imágenes seleccionadas.
   - Prepara el contenido para LinkedIn.

---

## Configuración de Credenciales

Este proyecto requiere varias credenciales externas. **Nunca incluyas tus claves reales en el repositorio.** Usa variables de entorno o un archivo `credentials.py` excluido de Git.

### 1. Telegram Bot
- Crear un bot con [@BotFather](https://t.me/BotFather).
- Obtener **Token del Bot** y **Chat ID**.


TELEGRAM_TOKEN = "TU_TOKEN"
TELEGRAM_CHAT_ID = "TU_CHAT_ID"

### 2. OpenAI
- Crear cuenta en OpenAI
- Generar API Key.

### 3. Perplexity
- Registrarse en Perplexity AI
- Obtener API Key.

### 4. PostgreSQL
Configurar base de datos PostgreSQL y obtener:
host, puerto, usuario, contraseña y nombre de base de datos.

POSTGRES_HOST = "localhost"
POSTGRES_PORT = 5432
POSTGRES_USER = "usuario"
POSTGRES_PASSWORD = "contraseña"
POSTGRES_DB = "nombre_db"

### 5. LinkedIn
Debes registrarte como empresa para poder conectar a la api de linkedin
Registrar una aplicación en LinkedIn Developer
Obtener Client ID y Client Secret.

### Instalación

Clonar el repositorio:
git clone git@github.com:joakomedina/bot_publicaciones_linkedin.git
cd bot_publicaciones_linkedin

### Uso

Ejecutar los flujos en n8n.

Enviar un mensaje al bot de Telegram con el tema deseado.

Abrir el formulario web desde el enlace recibido por Telegram.

Seleccionar los textos e imágenes deseadas.

Generar la publicación final lista para LinkedIn.

### Consideraciones

- Actualmente se generan 3 opciones de texto y 3 imágenes. Esto puede ajustarse según las necesidades.
- Se recomienda revisar manualmente los contenidos antes de publicar.
- Se pueden añadir flujos adicionales para manejar casos donde no gusten los textos ni las imágenes.

## Licencia

Este proyecto está bajo la [MIT License](LICENSE).
