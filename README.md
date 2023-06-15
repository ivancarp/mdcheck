*Kubernetes Reporte Ivan Carpinteiro Salazar*
-- 
# ¿Cuál es la versión LTS de Django?

Basicamente, LTS hace referencia a Long-Term Support, lo cual significa que es una versión que recibirá un soporte prolongado y actualizaciones de seguridad por un largo período de tiempo. Por lo general, una versión LTS se considera estable y confiable, siendo recomendada para su implementación en entornos de producción a largo plazo.

Las versiones LTS resultan especialmente relevantes para proyectos y organizaciones que buscan mantener estabilidad y continuidad a largo plazo, ya que garantizan la entrega de correcciones de errores, actualizaciones de seguridad y, en algunos casos, incluso nuevas funcionalidades durante un período extenso. Esto permite a los usuarios y desarrolladores confiar en la versión LTS, asegurando el funcionamiento de sus aplicaciones o sistemas sin necesidad de actualizar.

**Versión usada: _4.2.1_**

---

## Configuración del proyecto

Primero, para crear el proyecto, se usa el siguiente comando:

```bash
django-admin startproject <Nombre del proyecto>
```


Al ejecutar este comando, se creó una carpeta con el nombre del proyecto y dentro de ella encontré una serie de archivos .py, que eran los siguientes:

- El archivo `manage.py` es una utilidad de línea de comandos que me permitió interactuar con mi proyecto Django.
- El directorio interno `<Nombre del proyecto>` es el paquete de Python real para mi proyecto y su nombre se utilizó para importar sus componentes.
- El archivo `__init__.py` era un archivo vacío que indicaba que el directorio era un paquete de Python.
- El archivo `settings.py` contenía la configuración de mi proyecto Django.
- El archivo `urls.py` definía las URL de mi proyecto Django.
- Los archivos `asgi.py` y `wsgi.py` eran puntos de entrada para servidores web compatibles con ASGI y WSGI, respectivamente.

Ahora ejecutamos el servidor con
```bash
python3 manage.py runserver
```
Al ejecutar este comando en la línea de comandos, Django comenzó a escuchar en el puerto predeterminado (generalmente el puerto 8000). Podemos saber que está funcionando correctamente y que todo salió bien cuando logramos ver una pantalla que muestra el texto "The install worked successfully congratulations" junto con la imagen de un cohete.

Hay más formas de levantar el servidor, como el comando "python manage.py runserver 8080", que cambia el puerto en el que se ejecuta el servidor de desarrollo de Django. En lugar de utilizar el puerto predeterminado (8000), el servidor ahora escuchará en el puerto 8080. Esto es útil si el puerto 8000 ya está en uso o si deseas utilizar un puerto específico para tu aplicación Django.

Por otro lado, el comando "python manage.py runserver 0.0.0.0:8000" cambia tanto la dirección IP como el puerto en los que se escucha el servidor de desarrollo. Al especificar "0.0.0.0" como dirección IP, el servidor estará disponible para conexiones desde cualquier dirección IP, lo que puede ser útil si deseas acceder al servidor desde diferentes dispositivos en tu red local.

---
# Creación de la app

Todo lo que realizo fue completamente para la configuración inicial del proyecto. Ahora debemos proceder a crear la base de nuestra aplicación utilizando el siguiente comando:
```bash
python manage.py startapp "Nombre_app"
```

Al ejecutar este comando, Django generará una estructura básica de directorios y archivos para la nueva aplicación dentro del proyecto, los cuales son los siguientes:

- `__init__.py`: Es un archivo vacío que indica que el directorio "Nombre_de_la_app" es un paquete de Python.
- `admin.py`: Es un archivo donde puedes registrar los modelos de la aplicación para administrarlos en el panel de administración de Django.
- `apps.py`: Es un archivo de configuración de la aplicación donde puedes realizar ajustes específicos si es necesario.
- `migrations/`: Es un directorio donde se almacenarán las migraciones de la base de datos para esta aplicación. Además, contiene un archivo `__init__.py` que indica que el directorio "migrations" es un paquete de Python.
- `models.py`: Es un archivo donde puedes definir los modelos de datos de la aplicación.
- `tests.py`: Es un archivo donde puedes escribir pruebas automatizadas para tu aplicación.
- `views.py`: Es un archivo donde puedes definir las vistas que manejan las solicitudes HTTP y generan las respuestas correspondientes.

Procederemos a crear nuestra primera vista. En este caso, se trata de un simple mensaje de saludo. Dentro del archivo `views.py` de nuestra carpeta de la aplicación, agregaremos el siguiente código:

```python
from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```
Básicamente, este código muestra el mensaje "Hello, world. You're at the polls index." como respuesta en el navegador web cuando se accede a la URL asociada a esta vista.

Ahora debemos de hacer que la página donde apuntar, por ello crearemos un archivo llamado urls.py en la carpeta de la aplicación y lo modificaremos de la siguiente manera:


```python
from django.urls import path
from . import views

urlpatterns = [
    path("", views.index, name="index"),
]

```
Este código define una única ruta que coincide con la URL base de la aplicación y llama a la función de vista index cuando se accede a esa URL.

Ahora, desde la carpeta del proyecto, agregaremos lo siguiente al archivo urls.py:


```python
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path("Nombreapp/", include("nombreapp.urls")),
    path("admin/", admin.site.urls),
]
```
Este código configura las rutas del proyecto Django para redirigir las solicitudes a diferentes partes del proyecto. Las URL que comiencen con "Nombreapp/" serán manejadas por las rutas definidas en la aplicación "nombreapp", y las URL que comiencen con "admin/" serán manejadas por el panel de administración de Django.
***
