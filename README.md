# Comparador de créditos hipotecarios UVA

Calculadora web para comparar las cuatro líneas vigentes de crédito hipotecario UVA en CABA: **Banco Ciudad** (Línea General y Primera Vivienda) y **Banco Nación** (+Hogares y +Hogares Sector Público).

Permite simular cuota inicial, ingreso requerido, ahorro necesario, total a pagar (en UVA, pesos y dólares) y un escenario nominal proyectado con inflación y devaluación configurables.

## Demo

**[juangperezdev.github.io/comparador-hipotecario-uva](https://juangperezdev.github.io/comparador-hipotecario-uva/)**

## Características

- Comparación lado a lado de las cuatro líneas, agrupadas por banco.
- Cálculo en tiempo real al modificar cualquier campo.
- Validación automática de ingreso, ahorro y, para Primera Vivienda, restricciones de m² y precio por m².
- Total a pagar en términos reales (UVA / pesos de hoy / dólares de hoy).
- Total nominal proyectado con inflación y devaluación del dólar configurables por separado.
- Identificación visual de la línea más conveniente con badge "Calificás".
- Diseño responsive (mobile y desktop).
- Etiquetas Open Graph y Twitter Card para compartir en redes.
- Página 100% estática: un solo archivo HTML, sin build ni servidor.

## Uso local

Abrí `index.html` directamente en cualquier navegador moderno. No requiere instalación, dependencias ni servidor.

## Desplegar online

### GitHub Pages

1. Subí el repo a GitHub.
2. En el repositorio, ir a **Settings → Pages**.
3. En "Source" elegí la rama `main` y carpeta `/ (root)`.
4. La URL pública aparece en la misma sección en pocos minutos.

### Netlify

Arrastrá la carpeta a [app.netlify.com/drop](https://app.netlify.com/drop). Asigna URL pública con HTTPS de forma instantánea.

### Vercel

`vercel deploy` desde la raíz, o conectar el repo desde el dashboard.

### Hosting propio (cPanel / Plesk / FTP)

Subí `index.html` a la carpeta `public_html` (o a un subdirectorio). No requiere PHP ni base de datos.

## Configuración antes de publicar

En el `<head>` de `index.html` hay tres ocurrencias del placeholder `https://TU-DOMINIO.com/` en las etiquetas `canonical` y `og:url`. Reemplazalas por la URL pública real para que el SEO y los previews en redes funcionen bien.

## Cómo actualizar las tasas

Cuando los bancos cambien las tasas, editar dos puntos del `index.html`:

1. **Texto de referencia bajo el título**: buscar el bloque que setea `$('updated').textContent` cerca del final del script.
2. **Tasas efectivas por línea**: dentro de la función `tasaDe(l, poli)` están los porcentajes hardcodeados (9.5, 8.5, 7.5, 6). Actualizar según corresponda.

Para cambiar topes, plazos máximos o porcentajes de financiación, editar el array `lineas` al inicio del script.

## Stack

- HTML, CSS y JavaScript puros, sin dependencias externas.
- Tipografías Fraunces + Archivo cargadas vía Google Fonts (con fallback a Georgia / system fonts).
- Sin tracking, sin analíticas, sin cookies.

## Aviso legal

Esta calculadora es una estimación con fines informativos y no constituye asesoramiento financiero ni una oferta de crédito. Las condiciones, tasas y topes de cada banco cambian sin previo aviso: verificá siempre en los simuladores oficiales antes de tomar una decisión.

## Licencia

MIT. Ver `LICENSE`.
