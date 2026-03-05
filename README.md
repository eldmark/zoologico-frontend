# Zoológico — Frontend

Interfaz web estática (HTML + CSS + JS) que consume la API REST del backend [patrones-arquitectonicos-y-de-diseno](https://github.com/div468/patrones-arquitectonicos-y-de-diseno). No requiere frameworks ni dependencias — abre directamente en el navegador.

---

## Funcionalidades

- **Registrar animales** con nombre, edad, tipo y hábitat
- **Hint de compatibilidad en tiempo real** — indica si el animal puede vivir en el hábitat seleccionado antes de enviar
- **Animación de la Chain of Responsibility** — visualiza los 5 eslabones de validación uno por uno al registrar
- **Notificación de cadena completada** — resumen de cada validación al registrar exitosamente
- **Listar, ordenar por edad o nombre** y limpiar la grilla de animales
- **Tooltips flotantes** con explicaciones de cada patrón de diseño

---

## Conexión con el backend

El frontend detecta el entorno automáticamente:

| Entorno | URL usada |
|---|---|
| Local (`localhost` / `127.0.0.1`) | `http://localhost:8080/api/animales` |
| Producción (cualquier otro host) | `https://patrones-arquitectonicos-y-de-diseno.onrender.com/api/animales` |

Para sobreescribir la URL, definir en `index.html` antes de cargar `app.js`:

```html
<script>window.ZOO_API_BASE_URL = "https://tu-api.ejemplo.com/api/animales";</script>
```

---

## Ejecutar localmente

### Opción 1 — Abrir directo en el navegador

```bash
# Clonar el repositorio
git clone https://github.com/div468/zoologico-frontend.git
cd zoologico-frontend

# Abrir index.html en el navegador
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

### Opción 2 — Live Server (VS Code)

1. Instalar la extensión **Live Server** en VS Code
2. Abrir la carpeta del proyecto
3. Click derecho en `index.html` → **Open with Live Server**

> El backend debe estar corriendo en `http://localhost:8080` para que el frontend funcione correctamente. Ver instrucciones en el [repo del backend](https://github.com/div468/patrones-arquitectonicos-y-de-diseno).

---

## Estructura del proyecto

```
├── index.html   # Estructura de la UI y badges de patrones
├── style.css    # Estilos, animaciones de la cadena y tooltips
└── app.js       # Lógica: Fetch API, animación chain, hint de compatibilidad
```

---

## Tabla de compatibilidad (validada en cliente y servidor)

| Animal | Hábitats válidos |
|---|---|
| 🦁 León | Sabana, Desierto |
| 🐘 Elefante | Sabana, Selva |
| 🐒 Mono | Selva |
| 🦈 Tiburón | Acuario, Río |
| 🦅 Águila | Montaña |
| 🐊 Cocodrilo | Río, Selva |
