# Víctor Gallardo — Kinesiólogo Integral
**Landing page profesional** | [victorkine-web.pages.dev](https://victorkine-web.pages.dev) → dominio final: `spaequipos.cl`

Stack: **Astro 5** · Deploy: **Cloudflare Pages** · Repo: `Danorf/victorkine-web`

---

## ✅ Estado actual

| Sección | Contenido | Estado |
|---|---|---|
| Nav | WhatsApp, Instagram, links internos | ✅ |
| Hero | Foto Víctor (fondo transparente), CTAs, stats | ✅ |
| Sobre mí | Bio, U. de Chile, highlights | ✅ |
| Experiencia | Valle Nevado, Carolina Varela, práctica privada | ✅ |
| Servicios | 8 servicios + banner Ondas de Choque con imagen | ✅ |
| Dónde atiendo | KinesicWork + particular, horarios, comunas | ✅ |
| Contacto | WhatsApp, email, Instagram, preview chat WA | ✅ |
| Footer | Datos completos, redes, horarios | ✅ |
| WhatsApp flotante | Botón fijo bottom-right | ✅ |
| SEO básico | Title, meta description, OG tags | ✅ |
| Deploy Cloudflare Pages | Build automático desde GitHub | ✅ |

---

## 🔲 TO-DO — Próximos pasos

### 🔴 Prioritario

- [ ] **Conectar dominio `spaequipos.cl`** → ver sección DNS más abajo
- [ ] **Agregar foto real de Víctor en sección "Sobre mí"** (actualmente oculta en mobile, visible desktop)
- [ ] **Reemplazar imágenes de servicios restantes** con fotos reales de equipos (presoterapia, TENS, etc.)

### 🟡 Mejoras de contenido

- [ ] **Testimonios / reseñas de pacientes** — agregar sección con 3-4 testimonios reales
- [ ] **Galería de equipos** — fotos de los equipos de última generación que usa Víctor
- [ ] **Meta OG image** — imagen 1200×630px para compartir en redes (WhatsApp, Facebook)
- [ ] **Google Analytics / Cloudflare Analytics** — medir visitas y conversiones
- [ ] **favicon.ico** real — reemplazar el SVG genérico por ícono de la marca

### 🟢 Optimizaciones técnicas

- [ ] **Convertir imágenes a WebP** — reducir tamaño de `victor-gallardo.png` y `ondas-de-choque.png`
- [ ] **robots.txt y sitemap.xml** — Astro los genera automáticamente con el integration `@astrojs/sitemap`
- [ ] **Google Search Console** — registrar el sitio una vez el dominio esté conectado
- [ ] **Schema markup (JSON-LD)** — datos estructurados para médico/profesional de salud (mejora SEO local)

### 🔵 Funcionalidades futuras (opcionales)

- [ ] **Formulario de contacto** con Cloudflare Forms o Formspree (alternativa al WA)
- [ ] **Blog / artículos** — contenido educativo sobre kinesiología (SEO a largo plazo)
- [ ] **Sistema de agendamiento** — integrar Calendly o similar para reservas directas
- [ ] **Página de detalle por servicio** — landing específica para Ondas de Choque, Presoterapia, etc.

---

## 🌐 Conectar dominio `spaequipos.cl` — Guía DNS

El dominio `.cl` está registrado en **NIC.cl**. Para que `spaequipos.cl` apunte a Cloudflare Pages hay que hacer **uno de estos dos caminos**:

### Opción A — Cambiar Nameservers en NIC.cl (recomendado)
> Esto transfiere el control DNS completo del dominio a Cloudflare. Es la opción más robusta.

1. **En Cloudflare Dashboard:**
   - Ve a [dash.cloudflare.com](https://dash.cloudflare.com) → **"Add a site"**
   - Escribe `spaequipos.cl` → selecciona plan **Free**
   - Cloudflare escaneará los DNS actuales y los importará
   - Al final te dará **2 nameservers** (ej: `ava.ns.cloudflare.com` y `cole.ns.cloudflare.com`)

2. **En NIC.cl** ([nic.cl](https://www.nic.cl)):
   - Inicia sesión → busca `spaequipos.cl`
   - Sección **"Servidores de nombres"** → reemplaza los actuales por los 2 de Cloudflare
   - Guarda los cambios

3. **Espera propagación:** 24-48 horas (normalmente menos de 2 horas)

4. **En Cloudflare Pages:**
   - Ve al proyecto `victorkine-web` → **Custom domains** → **"Set up a custom domain"**
   - Escribe `spaequipos.cl` y también `www.spaequipos.cl`
   - Cloudflare crea los registros DNS automáticamente

### Opción B — Solo agregar registros CNAME en el DNS actual (cPanel)
> Útil si el cPanel gestiona otros servicios (email, etc.) que no quieres mover.
> ⚠️ Limitación: algunos dominios `.cl` bloquean CNAME en el apex (raíz). Puede no funcionar para `spaequipos.cl` sin `www`.

1. En tu panel DNS de cPanel, agrega:
   - Tipo `CNAME` | Nombre `www` | Valor `victorkine-web.pages.dev`
2. Para el dominio raíz (`spaequipos.cl` sin www) necesitas un registro ANAME/ALIAS — no todos los paneles lo soportan. Si no aparece, usa la Opción A.

---

## 🛠️ Desarrollo local

```bash
# Instalar dependencias
npm install

# Servidor de desarrollo (http://localhost:4321)
npm run dev

# Build de producción
npm run build
```

## 📦 Deploy

El deploy es automático: cada `git push` a `main` lanza un nuevo build en Cloudflare Pages.

```bash
git add -A
git commit -m "descripción del cambio"
git push
```

## 📁 Estructura del proyecto

```
/
├── public/
│   ├── victor-gallardo.png      # Foto Víctor (fondo transparente)
│   ├── ondas-de-choque.png      # Banner servicio ondas de choque
│   └── espolon-calcaneo.png     # Ilustración espolón calcáneo (reserva)
├── src/
│   ├── components/
│   │   ├── Nav.astro
│   │   ├── Hero.astro
│   │   ├── About.astro
│   │   ├── Experience.astro
│   │   ├── Services.astro
│   │   ├── Locations.astro
│   │   ├── Contact.astro
│   │   └── Footer.astro
│   ├── layouts/
│   │   └── Layout.astro         # Layout base + CSS global
│   └── pages/
│       └── index.astro          # Página principal
└── astro.config.mjs
```

## 📞 Datos de contacto del profesional

| Campo | Valor |
|---|---|
| Nombre | Víctor Gallardo P. |
| WhatsApp | +56 9 8186 2444 |
| Email | victor.gallardo@spaequipos.cl |
| Instagram | @victorkine_integral |
| KinesicWork | Av. Larraín 6642, Of. 214 — La Reina |
| KinesicWork URL | kinesicwork.cl |
| Comunas | Las Condes · La Reina · Vitacura · Providencia · Ñuñoa |
