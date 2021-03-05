---
layout: page
title: Ramas
parent: Productivo
description: Desarrollo en local mediante ramas en Git

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

### Siempre verificar cambios antes de iniciar
```
git pull origin master
```

### Crear rama `dev` o el nombre que se requiera para realizar un cambio en el proyecto
```
git branch dev
```

### Cambiar a rama `dev` y trabajar los cambios
```
git checkout dev
```

### Indicar en `app/Http/Helpers.php` el número de versión
```
function version()
{
    return 'v0.0.x';
}
```

### Registrar cambios en rama `dev`
```
git add .
git commit -m "Mensaje"
```

### Cambiar a rama `master` y fusionar rama `dev`
```
git checkout master
git merge dev
```

### Versionar el proyecto
```
git tag v0.0.x
```

###  Publicar cambios en GitLab y versión
```
git push origin master
git push origin --tags
```

### Cambiar a rama `dev` y copiar rama `master` para actualizar
```
git checkout dev
git merge master
```