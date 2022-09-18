# Taller de frontend

Código fuente de partida para el taller de frontend de la asignatura de Diseño y Mantenimiento del Software (Universidad de Burgos, Grado en Ingeniería Informática)

Seguir las instrucciones de la guía del taller disponible en el campus virtual.

## Instalación

Clonar este repositorio en la ruta deseada.

> **Opcional**: Para realizar estos pasos dentro de un entorno virtual ejecutar desde un terminal:
>
> ```bash
> sudo apt install -y python3-venv # Si venv no está instalado
> python3 -m venv .venv
> source .venv/bin/activate
> ```
>
> El terminal reflejará el cambio precediendo el _prompt_ con el nombre del entorno virtual.
> En VS Code, configurar el intérprete de Python a usar en la opción _"Python: Select interpreter"_ en la paleta de comandos (`Ctrl+Shift+P`) y seleccionando el intérprete del entorno virtual `.venv`.

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

Una vez arrancado, como se indica en las instrucciones que muestra en la salida, puede pararse pulsando `Ctrl+C`.

> En VS Code es posible arrancarlo y depurarlo desde el propio IDE creando un fichero `.vscode/launch.json` en el directorio raíz del proyecto:
>
> ```json
> {
>     "version": "0.2.0",
>     "configurations": [
>         {
>             "name": "Frontend: Dev",
>             "type": "python",
>             "request": "launch",
>             "module": "flask",
>             "env": {
>                 "FLASK_APP": "frontend/app.py",
>                 "FLASK_DEBUG": "1"
>             },
>             "args": [
>                 "run",
>                 "--debugger",
>                 "--reload",
>                 "-p",
>                 "8080"
>             ],
>             "jinja": true,
>             "justMyCode": true
>         },
>         {
>             "name": "Frontend: Run",
>             "type": "python",
>             "request": "launch",
>             "module": "flask",
>             "env": {
>                 "FLASK_APP": "frontend/app.py",
>                 "FLASK_DEBUG": "0"
>             },
>             "args": [
>                 "run",
>                 "--no-debugger",
>                 "--no-reload",
>                 "-p",
>                 "8080"
>             ],
>             "jinja": true,
>             "justMyCode": true
>         }
>     ]
> }
> ```
>
> Esta configuración permite arrancarlo con dos configuraciones diferentes: en modo de desarrollo (con depuración y autorrecarga habilitadas) o en modo convencional (sin depuración ni autorrecarga).
