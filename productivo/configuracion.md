---
layout: page
title: Configuración
parent: Productivo
description: Pasos para configurar un proyecto en Laravel en un servidor de producción.

usuario: usuario
repositorio: repositorio
---

# {{  page.title }}
{: .no_toc }

{{ page.description }}
{: .no_toc .fs-6 .fw-300 }

## Contenido
{: .no_toc .text-delta }

1. TOC
{:toc}

---

### Crear repositorio Git

Crear carpeta con el nombre de la aplicación `{{ page.repositorio }}` e iniciar *Git*

```
git init
```

Agregar repositorio remoto en *GitLab / GitHub* mediante *HTTPS / SSH*
```
git remote add origin https://gitlab.com/{{ page.usuario }}/{{ page.repositorio }}.git
git remote add origin git@github.com:{{ page.usuario }}/{{ page.repositorio }}.git
```

Actualizar cambios
```
git pull origin master
```

### Instalar dependencias
```
composer install
```

### Asignar permisos a usuarios
```
sudo chown -R usuario:grupo {{ page.repositorio }}
```

### Cambiar permisos a carpetas
```
sudo chmod -R 775 storage
sudo chmod -R 775 bootstrap/cache
```

### Crear BD
- Nombre: `db_{{ page.repositorio }}`
- Character set: `utf8mb4`
- Collation: `utf8mb4_general_ci`

### Configuración de la aplicación
Configurar archivo `.env`
```
sudo cp .env.example .env
```

Generales de la aplicación
```
APP_NAME={{ page.repositorio | capitalize }}
APP_ENV=production
APP_DEBUG=false
```

Conexión a BD
```
DB_DATABASE=db_{{ page.repositorio }}
DB_USERNAME=
DB_PASSWORD=
```

### Generar llave de la aplicación
```
php artisan key:generate
```

### Importar base de datos
Creación de tablas
```
php artisan migrate
```
Inserción de valores iniciales en catálogos
```
php artisan db:seed
```
O importar desde un archivo

### Configurar VirtualHost

En CentOS `/etc/httpd/conf/httpd.conf`
```
<VirtualHost *>
  DocumentRoot "/var/www/{{ page.repositorio }}/public"
  ServerName {{ page.repositorio }}.dominio.com
  <Directory "/var/www/{{ page.repositorio }}/public">
    DirectoryIndex index.php
    AllowOverride All
    Allow from all
    Require all granted
  </Directory>
</VirtualHost>
```