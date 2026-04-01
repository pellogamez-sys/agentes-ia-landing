# Landing Page: Agentes de IA - Indusconsulting

## 🚀 Desplegar en Netlify

### Opción 1: Deploy manual (drag & drop)

1. Ve a https://app.netlify.com/drop
2. Arrastra la carpeta `landing-agentes-ia` completa
3. Netlify te dará una URL temporal (ej: https://xyz123.netlify.app)
4. Configura dominio personalizado después

---

### Opción 2: Deploy via CLI (desde este servidor)

```bash
# Configurar token en Doppler primero
doppler secrets set NETLIFY_AUTH_TOKEN="tu_token_de_netlify"

# Login (solo primera vez)
netlify login

# Crear nuevo sitio
netlify sites:create --name agentes-ia-indusconsulting

# Deploy
netlify deploy --prod --dir=landing-agentes-ia

# Configurar dominio personalizado
netlify domains:add agentes.indusconsulting.es
```

---

### Opción 3: Git + Netlify (automático)

1. Subir a repositorio GitHub
2. Conectar Netlify al repo
3. Auto-deploy en cada push

```bash
cd /data/.openclaw/workspace/landing-agentes-ia
git init
git add .
git commit -m "Landing Agentes IA"
git remote add origin https://github.com/tu-usuario/agentes-ia-landing.git
git push -u origin main
```

---

## 🔧 Personalización

### Cambiar precios
Editar `index.html`, sección `service-price`:
```html
<span class="price-setup">$1,500</span>
<span class="price-monthly">+ $500/mes</span>
```

### Cambiar URLs
- Calendly: Buscar `calendly.com/indusconsulting`
- Email: Buscar `consultoria@indusconsulting.es`
- Web: Buscar `indusconsulting.es`

### Añadir tracking
Añadir antes de `</head>`:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>

<!-- Meta Pixel -->
<script>
  !function(f,b,e,v,n,t,s)
  {if(f.fbq)return;n=f.fbq=function(){n.callMethod?
  n.callMethod.apply(n,arguments):n.queue.push(arguments)};
  if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
  n.queue=[];t=b.createElement(e);t.async=!0;
  t.src=v;s=b.getElementsByTagName(e)[0];
  s.parentNode.insertBefore(t,s)}(window, document,'script',
  'https://connect.facebook.net/en_US/fbevents.js');
  fbq('init', 'TU_PIXEL_ID');
  fbq('track', 'PageView');
</script>
```

---

## 📊 Estructura de archivos

```
landing-agentes-ia/
├── index.html          # Página principal
├── styles.css          # Estilos
├── netlify.toml        # Configuración Netlify
└── README.md           # Este archivo
```

---

## 🎨 Secciones de la landing

1. **Header** - Logo + navegación
2. **Hero** - Propuesta de valor + CTA
3. **Problema/Solución** - Antes vs después
4. **Servicios** - 3 paquetes con precios
5. **Caso de éxito** - Tu propio caso real
6. **Cómo funciona** - 4 pasos
7. **Precios** - Tabla detallada
8. **CTA Final** - Contacto
9. **Footer** - Links

---

## 📱 Responsive

- Desktop: 3 columnas en servicios
- Tablet: 1-2 columnas
- Mobile: 1 columna, navegación oculta

---

## ✅ Checklist antes de publicar

- [ ] Cambiar URLs (Calendly, email, web)
- [ ] Verificar precios
- [ ] Añadir Google Analytics (opcional)
- [ ] Añadir Meta Pixel (opcional)
- [ ] Configurar dominio personalizado
- [ ] Configurar SSL (automático en Netlify)
- [ ] Probar en móvil
- [ ] Probar todos los links

---

## 🔗 Dominios sugeridos

- `agentes.indusconsulting.es` (subdominio)
- `ia.indusconsulting.es` (subdominio)
- `www.indusconsulting.es/agentes-ia` (ruta)

---

**Estado:** ✅ Landing lista para desplegar
**Tiempo estimado de deploy:** 5-10 minutos
