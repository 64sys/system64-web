# Web de System 64 — GitHub Pages

Web estática (un solo `index.html`, sin dependencias ni compilación).

## 1. Antes de subir

Edita estos datos en `index.html` (busca `TODO`):
- `contact@VOTRE-DOMAINE.ch` → tu email real de Zoho
- `+41 00 000 00 00` / `tel:+41000000000` → tu teléfono (o borra ese bloque)

Edita `CNAME` y pon tu dominio, por ejemplo `www.tudominio.ch`.

## 2. Crear el repo y publicar

```bash
cd system64-web
git init
git add .
git commit -m "Web inicial System 64"
git branch -M main
git remote add origin git@github.com:TU_USUARIO/system64-web.git
git push -u origin main
```

En GitHub: **Settings → Pages → Build and deployment**
- Source: *Deploy from a branch*
- Branch: `main` / `(root)` → Save

En 1–2 minutos estará en `https://TU_USUARIO.github.io/system64-web/`.

## 3. Dominio propio (DNS)

En el panel DNS de tu dominio **añade** estos registros.
**No toques MX, SPF (TXT), DKIM ni DMARC de Zoho**: son los del correo.

| Tipo  | Nombre | Valor                   |
|-------|--------|-------------------------|
| A     | @      | 185.199.108.153         |
| A     | @      | 185.199.109.153         |
| A     | @      | 185.199.110.153         |
| A     | @      | 185.199.111.153         |
| CNAME | www    | TU_USUARIO.github.io.   |

Si ya existe algún registro A o CNAME para `@` o `www` (por ejemplo, de un parking
del registrador), bórralo primero.

Luego en **Settings → Pages → Custom domain** escribe `www.tudominio.ch`, espera a que
se valide el DNS y marca **Enforce HTTPS**.

Recomendado: en **Settings (de tu cuenta) → Pages → Verified domains** verifica el dominio
para que nadie más pueda usarlo en GitHub Pages.

## 4. Actualizar la web

Editas `index.html`, haces `git commit` y `git push`: se publica sola.
