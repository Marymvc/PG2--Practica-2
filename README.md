# PG2--Practica-2
# Uso de Django

Repositorio de ejemplo para el uso básico de Django en un proyecto de desarrollo web.

---

## 🧱 Crear entorno virtual

```bash
python -m venv venv
```

---

## ▶️ Activar entorno virtual

### Windows
```bash
.env\Scriptsctivate
```

### Linux/macOS
```bash
source venv/bin/activate
```

---

## 📦 Instalar dependencias

```bash
pip install -r requirements.txt
```

---

## 🚀 Crear proyecto Django

```bash
django-admin startproject practica2 .
```

---

## 🛠 Aplicar migraciones iniciales

```bash
python manage.py migrate
```

---

## 🧪 Iniciar servidor

```bash
python manage.py runserver
```

---

## 👤 Crear superusuario

```bash
python manage.py createsuperuser
```

---

## 📂 Crear aplicación

```bash
python manage.py startapp libros
```

---

## ⚙️ Agregar aplicación a `settings.py`

```python
INSTALLED_APPS = [
    ...
    'libros',
]
```

---

## 📌 Crear modelo

Escribir en `libros/models.py`:

```python
from django.db import models

class Autor(models.Model):
    nombre = models.CharField(max_length=100)
    fecha_nacimiento = models.DateField()

    def __str__(self):
        return self.nombre

class Libro(models.Model):
    titulo = models.CharField(max_length=100)
    autor = models.ForeignKey(Autor, on_delete=models.CASCADE, related_name="libros")
    fecha_publicacion = models.DateField()

    def __str__(self):
        return self.titulo
```

---

## 📥 Crear migraciones

```bash
python manage.py makemigrations
```

---

## ⚙️ Aplicar migraciones

```bash
python manage.py migrate
```

---

## 🔐 Configurar `admin.py`

Editar `libros/admin.py`:

```python
from django.contrib import admin
from .models import Autor, Libro

admin.site.register(Autor)
admin.site.register(Libro)
```

---

## 🌐 Acceder al panel de administración

Abrí tu navegador y visitá:

```
http://localhost:8000/admin/
```

Iniciá sesión con el superusuario. Ya deberías poder agregar autores y libros.

---

## ✅ Listo
Tu app básica de Django ya está funcionando. Podés continuar con vistas, URLs, formularios y más.
