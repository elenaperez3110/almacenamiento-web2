# almacenamiento-web2
Web estática educativa sobre tipos de almacenamiento de datos
# Almacenamiento web (estático)

Sitio educativo estático sobre **tipos de almacenamiento** (bloque, archivo, objeto, columna), con filtro, tarjetas, tabla comparativa, glosario y un pequeño quiz.

## Estructura
- Archivo principal: `index.html` (en la raíz).
- Estilos: **Tailwind vía CDN** (no requiere build ni herramientas locales).
- No hay dependencias, `package.json` ni comandos.

---

## Cómo desplegar en Vercel (SIN CLI)

### Requisitos
- Cuenta gratuita en [Vercel](https://vercel.com) y acceso al repositorio en GitHub.
- No se necesita instalar nada.

### Pasos
1. Inicia sesión en **Vercel**.
2. Pulsa **Add New…** → **Project**.
3. En la pestaña **Import Git Repository**, conecta tu cuenta de GitHub si es la primera vez.
4. Selecciona el repositorio **`almacenamiento-web`** y pulsa **Import**.
5. Configuración del proyecto:
   - **Framework Preset**: *Other* (o *Static Site*).
   - **Build Command**: *(dejar vacío)*.
   - **Output Directory**: `/` (raíz).
6. Pulsa **Deploy**.

> Vercel detecta que es un **sitio estático** y servirá `index.html` desde la raíz.

### Resultado
- Obtendrás una URL pública del tipo: `https://<nombre>.vercel.app`.
- Cada vez que hagas un **commit en `main`**, Vercel redeploya automáticamente.
- Si creas una **Pull Request**, Vercel genera una **Preview URL** para revisión.

### Opcional: Dominio personalizado
1. En el proyecto de Vercel, ve a **Settings → Domains**.
2. Añade tu dominio y sigue las instrucciones para configurar los registros DNS.
3. Espera a la verificación de Vercel.

---

## Desarrollo básico (solo navegador)
- Edita archivos directamente en GitHub: **Add file → Create new file** o **Editar**.
- Confirma con **Commit changes**. Vercel tomará el cambio y redeployará.
- No se requiere terminal.

---

## Licencia
CC BY 4.0 (puedes cambiarla si lo prefieres).
