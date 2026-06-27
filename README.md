# EG · Linktree Premium

Página de aterrizaje tipo Linktree premium para **EG — Diseño e Ilustración**.
Construida con **HTML5 semántico + CSS3 nativo** (sin frameworks, sin build).
Lista para subir a **Netlify** o **Cloudflare Pages**.

---

## Estructura del proyecto

```
linktree-eg/
├── index.html          # Página principal (Hero + enlaces)
├── privacidad.html     # Política de Privacidad RGPD básica
├── styles.css          # Hoja de estilos única (comentada, mobile-first)
├── favicon.svg         # Favicon con iniciales EG tipográficas
└── README.md           # Este archivo
```

> **Nota de diseño:** la marca se presenta solo tipográficamente como `EG.`
> con un punto violeta como acento. No se usa el monograma SVG original
> porque a tamaños pequeños podía confundirse con una "Z". Si en el futuro
> quieres volver a usar tu monograma, basta con añadir un `<img>` dentro
> del `<a class="brand">` en `index.html`.

> **Tip:** mantén esta carpeta en la raíz del repositorio. En Netlify/Cloudflare
> el "publish directory" debe apuntar a esta carpeta (`linktree-eg/` o `.` si
> ya estás dentro).

---

## Antes de publicar — personaliza estos datos

Abre `index.html` y reemplaza los siguientes placeholders:

| Placeholder                       | Sustitúyelo por                                    |
| --------------------------------- | -------------------------------------------------- |
| `https://www.behance.net/tu-usuario` | Tu URL de Behance (aún placeholder)             |
| `https://tu-sitio.com/proyectos`  | Tu URL de proyectos destacados (Dribbble, web...)  |
| `https://wa.me/5210000000000`     | Tu número de WhatsApp en formato internacional     |
| ~~`https://www.linkedin.com/...`~~ | ✅ LinkedIn real ya configurado                  |
| ~~`hola@tudominio.com`~~ / ~~`privacidad@tudominio.com`~~ | ✅ Correo real ya configurado      |

### Cambiar el favicon o la marca tipográfica

- **Favicon:** el archivo `favicon.svg` contiene un cuadrado slate con las
  letras "EG" en blanco y un punto violeta en la esquina. Edítalo o
  sustitúyelo por tu propio icono.
- **Marca en el header:** actualmente es solo texto `EG.` con el punto en
  violeta. Para usar tu monograma o logo, edita el `<a class="brand">` en
  `index.html` y añade un `<img>` antes del texto.
- **Foto profesional en el Hero:** el Hero actual usa un *eyebrow* (pill
  con la palabra "Diseñadora e Ilustradora"). Si prefieres una foto, añade
  un `<img class="hero-avatar__img" src="avatar.jpg" alt="EG">` antes del
  `<span class="hero-eyebrow">` y usa la clase `.hero-avatar` ya existente
  en versiones previas del CSS.

---

## Despliegue en Netlify

1. Crea una cuenta en https://netlify.com (puedes entrar con GitHub/Google).
2. Arrastra la carpeta `linktree-eg/` a la zona "Drag and drop your site folder"
   en https://app.netlify.com/drop.
3. Listo. Recibirás una URL tipo `https://tu-sitio.netlify.app`.
4. Para usar tu propio dominio: **Site settings → Domain management → Add custom domain**.

> Alternativa: conecta tu repositorio de Git para despliegues automáticos
> en cada `git push`.

## Despliegue en Cloudflare Pages

1. Entra a https://dash.cloudflare.com → **Workers & Pages → Create → Pages**.
2. **Upload assets** → arrastra el contenido de `linktree-eg/` (o conecta tu repo Git).
3. Framework preset: **None**.
4. Build command: *(vacío)* · Build output directory: `.` (o el nombre de la carpeta).
5. **Deploy**. Recibirás una URL `https://linktree-eg.pages.dev`.
6. Para dominio propio: **Custom domains → Set up a custom domain**.

---

## Características técnicas

- **HTML5 semántico**: `header`, `main`, `section`, `nav`, `footer`, `article`.
- **CSS nativo** con variables (custom properties), Grid/Flex, `clamp()` para
  tipografía fluida y mobile-first responsive.
- **Google Fonts**: Montserrat 700/600 (titulares) + Inter 400/500/600 (cuerpo),
  con soporte completo para español (acentos, eñes, ¿).
- **Accesibilidad (WCAG AA)**:
  - `lang="es"`, skip-link, focus visible con `:focus-visible`.
  - Contraste ≥ 4.5:1 en texto y ≥ 3:1 en elementos grandes.
  - ARIA labels en enlaces externos, `aria-hidden` en iconos decorativos.
  - `prefers-reduced-motion` respetado.
- **SEO básico**: meta description, Open Graph, robots indexables, favicon SVG.
- **Performance**: sin JS pesado (solo 1 línea para el año del footer),
  preconnect a Google Fonts, CSS crítico en línea cero, imágenes con
  dimensiones explícitas.

---

## Personalización rápida (colores)

Todos los colores están definidos como variables CSS al inicio de `styles.css`,
en la sección `:root`:

```css
:root {
  --color-bg: #F4F6F9;          /* Fondo */
  --color-text: #1E293B;        /* Texto principal */
  --color-accent: #7c3aed;      /* Violeta (botón principal) */
  --color-cyan: #0ea5e9;        /* Azul cian (acento secundario) */
  --color-whatsapp: #25D366;
  --color-linkedin: #0A66C2;
  /* … */
}
```

Cambia un valor y se propaga a toda la página.

---

## Licencia

Código entregado para uso personal y comercial de EG.
El logotipo `logo.svg` es propiedad de su autora.
