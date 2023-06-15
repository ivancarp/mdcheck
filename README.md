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
Al ejecutar este comando en la línea de comandos, Django comenzó a escuchar en el puerto
predeterminado (generalmente el puerto 8000) podemos saber que esta funcionando correctamente y
que todo salio bien cuando logramos ver una pantalla que muestra el texto The install worked
successfully congratulations junto con la imagen de un cohete.hay mas formas de levantar el servidor como El comando "python manage.py runserver 8080" el cual
cambia el puerto en el que se ejecuta el servidor de desarrollo de Django. En lugar de utilizar el puerto
predeterminado (8000), el servidor ahora escuchará en el puerto 8080. Esto es útil si el puerto 8000 ya
está en uso o si deseas utilizar un puerto específico para tu aplicación Django.
Por otro lado, el comando "python manage.py runserver 0.0.0.0:8000" cambia tanto la dirección IP
como el puerto e
--

