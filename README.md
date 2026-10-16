# Tabbycat Importer

Herramienta web para importar instituciones, equipos y juezas a torneos de debate en Tabbycat mediante su API.

## 🚀 Uso

1. Abre [la aplicación](https://rgrandia.github.io/tabbyimporter/)
2. Configura tu conexión a Tabbycat (URL de la API, slug del torneo y clave API)
3. Sube tu archivo Excel siguiendo la plantilla
4. Verifica e importa

## 📋 Estructura del Excel

- **INSTITUTIONS**: Nombre, Código, Región
- **TEAMS**: Equipo, Institución, Participantes (x2) con emails y categorías
- **ADJ**: Nombre, Institución, Puntuación, Email

Las categorías de orador deben existir previamente en el torneo (por nombre o slug); las que no existan se omiten con un aviso en el log.

## 🔒 Seguridad

- La aplicación se ejecuta en el navegador y no guarda la clave API (solo la URL y el slug, en `localStorage`).
- Las peticiones a Tabbycat, incluida la clave API, pasan por un proxy propio en Cloudflare Workers (`tabbycat-proxy.rgrandia.workers.dev`), que las reenvía a la instancia de Tabbycat.
- Recomendación: usa una clave API dedicada para la importación y regénérala al terminar.

## 🛠️ Desarrollo

Tecnologías: HTML5, CSS3, JavaScript vanilla, SheetJS (XLSX)

## 📄 Licencia

[MIT](LICENSE).

---
Hecho con ❤️ para la comunidad de debate
Roc Grandia i Mazcuñan
