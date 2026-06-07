# Despliegue — MiPlaza (CodeIgniter 3 + MySQL)

Esta aplicación **no puede correr completa en Vercel**, porque Vercel no ejecuta PHP con MySQL de forma nativa. Hay dos rutas:

## Opción A — Demo estático del frontend (Vercel) ✅

La carpeta [`demo/`](./demo) contiene el frontend público exportado a HTML estático (sin PHP). Se puede desplegar tal cual en Vercel como sitio estático. **Limitación:** el panel de administración y el catálogo dinámico no funcionan (necesitan el backend).

## Opción B — App completa en un hosting con PHP + MySQL

Plataformas recomendadas (todas con plan gratuito o de bajo costo):

| Plataforma | Notas |
|------------|-------|
| **Railway** | Soporta PHP + base MySQL administrada. Buen flujo desde GitHub. |
| **Render** | Web service PHP + base PostgreSQL/MySQL externa. |
| **InfinityFree** | Hosting PHP/MySQL gratuito clásico (cPanel, ideal para CodeIgniter). |
| **000webhost / Hostinger** | Alternativas con soporte PHP+MySQL. |

### Pasos generales

1. Sube el proyecto al hosting (Git o FTP).
2. Crea una base de datos MySQL e **importa** `system/database/miplaza.sql`.
3. Configura las credenciales en `application/config/database.php`:
   - `hostname`, `username`, `password`, `database`
4. Ajusta `base_url` en `application/config/config.php` a tu dominio.
5. Apunta el dominio a `index.php` (front controller).

### ⚠️ Variables / datos que NO deben subirse al repo

- Credenciales reales de la base de datos (usuario/contraseña del hosting).
- Cualquier archivo `.env` con secretos.

> Actualmente `database.php` usa los valores por defecto de desarrollo (`root` / sin contraseña / `miplaza`). En producción, reemplázalos por las credenciales de tu hosting **sin** subirlas al repositorio público.
