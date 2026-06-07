# Sitio Web Negocio — MiPlaza

Sitio web para el supermercado **MiPlaza**: una página institucional con catálogo de productos, sección "Nosotros", ubicación y un **panel de administración** para gestionar las tarjetas/productos del catálogo.

Construido con **CodeIgniter 3** (PHP) y **MySQL**.

## 🖥️ Demo

- **Demo estático del frontend público** (sin backend): ver carpeta [`demo/`](./demo) — incluye la página de inicio y la sección "Nosotros" exportadas a HTML estático, desplegables en Vercel.
- **App completa:** requiere un hosting con PHP + MySQL. Ver [`DEPLOY.md`](./DEPLOY.md).

## ¿Qué hace?

- **Frontend público:** página de inicio con catálogo de categorías (carnes, bebidas, abarrotes, higiene, etc.), sección "Nosotros" y enlaces a redes sociales.
- **Panel admin:** login de administrador y formulario para agregar/editar tarjetas de producto (`addcard`).
- Diseño responsivo con **Bootstrap 5**.

## 🛠️ Stack

| Capa | Tecnología |
|------|------------|
| Backend | PHP 7+ / **CodeIgniter 3.1.13** (patrón MVC) |
| Base de datos | **MySQL** (base `miplaza`, dump en `system/database/miplaza.sql`) |
| Frontend | HTML5, CSS3, **Bootstrap 5**, JavaScript + jQuery |

## 📁 Estructura (CodeIgniter)

```
application/
  controllers/   Bienvenido.php (público), Admin.php (panel)
  views/         inicio.php, nosotros.php, login-admin.php, addcard.php
  config/        config.php (base_url), database.php (conexión MySQL)
public/          bootstrap, css, js, img  (assets)
system/          núcleo de CodeIgniter
  database/miplaza.sql   ← dump de la base de datos
index.php        front controller
```

## ▶️ Cómo ejecutarlo en local

1. Instala PHP 7+, MySQL y un servidor (XAMPP/Laragon o `php -S`).
2. Crea la base de datos e importa el dump:
   ```bash
   mysql -u root -e "CREATE DATABASE miplaza;"
   mysql -u root miplaza < system/database/miplaza.sql
   ```
3. Configura la conexión en `application/config/database.php` (`hostname`, `username`, `password`, `database`).
4. Ajusta `base_url` en `application/config/config.php`.
5. Levanta el servidor:
   ```bash
   php -S localhost:8080
   ```
6. Abre `http://localhost:8080`.

## 👤 Autor

**Alan Daniel Méndez Jiménez** — Ing. en Sistemas Computacionales, TecNM Celaya.
GitHub: [@Alan20111](https://github.com/Alan20111)
