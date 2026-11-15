# CAPDESIS GitHub Pages (`capdesis.github.io`)

Sitio estático público en GitHub Pages para **CAPDESIS**, cuya raíz redirige a la página de producto y al aviso de privacidad de **Fotos de clase** (`photos_class/`).

Public static GitHub Pages site for **CAPDESIS**. The root page redirects to the **Fotos de clase** product landing page and privacy notice (`photos_class/`).

## Estructura del repositorio / Repository structure

```text
.
├── index.html                  # Redirección raíz hacia photos_class/ / Root redirect to photos_class/
└── photos_class/
    ├── index.html              # Landing estática de Fotos de clase / Product landing page (es-MX)
    ├── privacy.html            # Aviso de privacidad público / Public privacy notice (es-MX)
    ├── icon.png                # Ícono de la aplicación / App icon
    └── shots/                  # Capturas de pantalla / App screenshots
        ├── 01-materias.jpg
        ├── 03-fotos.jpg
        ├── 04-visor.jpg
        └── 05-horario.jpg
```

## Arquitectura estática y CSP / Static design & CSP

- **HTML y CSS puros / Pure HTML & CSS:** las páginas usan únicamente HTML semántico y `<style>` en línea, sin JavaScript, sin compilación y sin dependencias externas (fuentes, analítica ni scripts de terceros).
- **Content Security Policy estricta / Strict CSP:** tanto `photos_class/index.html` como `photos_class/privacy.html` declaran `<meta http-equiv="Content-Security-Policy" ...>` con `default-src 'none'`, `base-uri 'none'` y `form-action 'none'` (permitiendo únicamente `style-src 'unsafe-inline'` y, en `index.html`, `img-src 'self' data:`).
- **Sin backend ni recopilación de datos / No backend or tracking:** el sitio es puramente informativo y refleja el funcionamiento sin servidor de la aplicación.

## Vista previa local / Local preview

Desde la raíz del repositorio, levanta cualquier servidor HTTP estático y abre `http://localhost:8080/photos_class/`:

```bash
python3 -m http.server 8080
```

## Publicación y CI / Publishing & CI

- **GitHub Pages:** se publica directamente desde la rama principal sin paso de compilación (*build step*).
- **CI:** este repositorio no tiene flujos de GitHub Actions configurados (`0` workflows en `.github/workflows/`).

## Soporte / Support

- Reportes e incidencias: [GitHub Issues](https://github.com/CAPDESIS/capdesis.github.io/issues) (no adjuntes fotos, horarios ni datos personales).
