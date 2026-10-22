# Publicación automática con Cloudflare Pages

El sitio se genera con Node.js y sus módulos integrados, sin instalar dependencias. El resultado conserva el diseño y todas las rutas de servicios, portafolio, casos y hoja de vida.

## Conexión inicial

1. Entrar en Cloudflare y abrir Workers & Pages.
2. Seleccionar Create application > Pages > Connect to Git.
3. Conectar GitHub y permitir acceso solo al repositorio DanielFlorezT/portafolio.
4. Seleccionar el repositorio y comenzar la configuración.
5. Elegir el nombre del proyecto; ese nombre determinará la dirección disponible en pages.dev.
6. Completar los valores de esta tabla y seleccionar Save and Deploy.

| Campo | Valor |
| --- | --- |
| Production branch | main |
| Framework preset | None |
| Build command | node build-site.mjs |
| Build output directory | dist |
| Root directory | Dejar vacío, raíz del repositorio |

Cada cambio guardado en main generará un nuevo despliegue. Los cambios locales aún deben guardarse en GitHub para que Cloudflare los reciba.

## Después de la primera publicación

Guardar la dirección de producción y configurar la variable SITE_URL con esa dirección completa, por ejemplo https://nombre-elegido.pages.dev, en Production y Preview. Así las etiquetas para buscadores y redes usarán la dirección principal. Sin SITE_URL, el constructor utiliza CF_PAGES_URL cuando está disponible.

También se deben actualizar los enlaces de los README y del PDF al cambiar definitivamente la dirección principal. Los enlaces internos del sitio son relativos y conservan las páginas y el diseño al migrar.

## Archivos principales

- build-site.mjs: contenido y estructura de las páginas.
- styles.css: tipografías, diseño adaptable y paleta clara.
- CV_Daniel_Florez_Thomas.pdf: versión principal descargable.
- DFT_logo.png y DFT_logo.svg: logo sobre fondo transparente.
- Fuentes, licencias y capturas: recursos visuales que se copian al sitio.

## Referencias oficiales

- https://developers.cloudflare.com/pages/get-started/git-integration/
- https://www.cloudflare.com/products/pages/
