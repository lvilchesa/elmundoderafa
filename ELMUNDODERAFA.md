# ELMUNDODERAFA.md — Registro de migración de elmundoderafa.cl
**Cliente:** El Mundo de Rafa (juegos inflables, Los Ángeles). Proyecto apoyado por SERCOTEC.  
**Sitio actual:** https://elmundoderafa.cl (Bluehost, cuenta `vilchesc`)  
**Repo:** `D:\DEV\Web\ClaudeCode\GitHub\lvilchesa\elmundoderafa\` → destino **github.com/lvilchesa/elmundoderafa**  
**Documentación del desarrollo** (secciones, galería, tarifas, FormSubmit): `D:\DEV\Web\ClaudeCode\ElMundodeRafa\ElMundodeRafa.md`  
**Última actualización:** 2026-09-25

---

## ▶ Punto de retomada

**Estado:** la copia local es **idéntica al sitio publicado** (comprobado archivo por archivo el 25-sep-2026: `index.html`, `styles.css`, `tarifas.json` y 59 imágenes). Se hizo una limpieza sin cambios visibles y quedó commit local. **Falta crear el repo en GitHub** (lo hace Gonzalo: el token no crea repos) y seguir `PROTOCOLO-MIGRACION-GHPAGES.md`.

**Para editar precios:** solo `assets/data/tarifas.json` (las tarjetas se generan desde ahí).
**Para agregar fotos a la galería:** `assets/img/galeria/galeria_NNN.jpeg` + actualizar `const totalFotos` al final de `index.html`.

## Datos para la migración (fase 0)
- DNS: Bluehost, sin DNSSEC, IP 162.241.216.59 (misma cuenta que el hotel y Syman).
- **Correo:** `contacto@elmundoderafa.cl` es **solo un reenvío** en Bluehost → **jamb33@gmail.com y yoanaroa@gmail.com** (dos destinos). Pasa a Cloudflare Email Routing. **Las dos casillas tienen que hacer clic en la verificación de Cloudflare.** Hay que confirmar si una regla acepta dos destinos; si no, un Email Worker.
- **Formulario de cotización:** FormSubmit → `contacto@elmundoderafa.cl`. Sigue funcionando en GitHub Pages (es un servicio externo), **siempre que el reenvío de `contacto@` exista**: Email Routing tiene que quedar activo antes de cancelar Bluehost.
- DMARC `p=none`; sin SPF propio.

## Historial

### Limpieza previa a la migración (2026-09-25)
Sin cambios visibles (comparado con capturas antes/después; solo difiere la carga del mapa de Google):
- Logo `logo-png.png` de 1024 px / 1,3 MB → 400 px / 226 KB (se muestra a 100–150 px).
- Ícono de pestaña `assets/img/favicon.png` (antes daba 404).
- `alt` del logo de la portada corregido (decía "Proyecto apoyado por SERCOTEC").
- 12 fotos de la galería recomprimidas sin cambiar tamaño: 6,6 MB → 3,9 MB. Total del sitio: 17 → 13 MB.
- Quitadas 3 imágenes sin uso (`logo.jpeg`, `qr-instagram.jpeg`, `qrig.jpeg`; siguen en `ElMundodeRafa/`). `.gitignore` para `desktop.ini`.
