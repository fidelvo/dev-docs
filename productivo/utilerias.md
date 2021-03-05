---
layout: page
title: Utilerías
parent: Productivo
description: Instrucciones útiles al actualizar versión del repositorio

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

### Al actualizar
```
php artisan config:clear
php artisan cache:clear
php artisan view:clear

composer dump-autoload
```

### Reiniciar servidor
```
sudo apachectl restart
sudo service httpd restart
```

### Ruta de archivo `log`
```
storage/logs/laravel.log
```

### Remover caché en `.gitignore`
```
git rm -r --cached .
```

### Git log & branches
```
git log --oneline
git log --oneline --all --decorate --graph
```

### Refrescar base de datos
Cuando las tablas tuvieron cambios
```
php artisan migrate:fresh --seed
```
Cuando se desea solamente setear a valores iniciales
```
php artisan db:seed
```