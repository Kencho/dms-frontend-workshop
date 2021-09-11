# Taller de frontend

Código fuente de partida para el taller de frontend de la asignatura de Diseño y Mantenimiento del Software (Universidad de Burgos, Grado en Ingeniería Informática)

Seguir las instrucciones de la guía del taller disponible en el campus virtual.

## Instalación

Clonar este repositorio en la ruta deseada.

Desde dicha ruta, subdirectorio `frontend`, instalar las dependencias con:

```bash
pip3 install -r requirements.txt
```

## Arrancar y parar el servidor

Después de cada cambio, salvo en los elementos estáticos (e.g., hojas de estilos) será necesario reiniciar el servidor.

Para arrancarlo en el puerto `8080`, desde la ruta del frontend en el proyecto:

```bash
FLASK_APP=app.py flask run -p 8080
```

Una vez arrancado, como se indica en las instrucciones que muestra en la salida, puede pararse pulsando Ctrl+C.
