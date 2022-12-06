---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

- [Proyecto:](#proyecto)
  - [Aplicación Web con Flask utilizando la API de Rick and Morty y bases de datos.](#aplicación-web-con-flask-utilizando-la-api-de-rick-and-morty-y-bases-de-datos)
  - [Materiales adicionales para pasar antes de la clase:](#materiales-adicionales-para-pasar-antes-de-la-clase)
    - [Pre clase:](#pre-clase)
    - [Otras herramientas y links de documentacion](#otras-herramientas-y-links-de-documentacion)
  - [Introduccion al desarrollo web - Instalaciones de dependencias](#introduccion-al-desarrollo-web---instalaciones-de-dependencias)
    - [Que tecnologias vamos a ver hoy en el taller?](#que-tecnologias-vamos-a-ver-hoy-en-el-taller)
    - [Input practico #1: Creacion de carpetas, activacion del entorno virtual y instalacion de librerias](#input-practico-1-creacion-de-carpetas-activacion-del-entorno-virtual-y-instalacion-de-librerias)
    - [Para que nos sirve un entorno virtual?](#para-que-nos-sirve-un-entorno-virtual)
    - [Activacion de entorno virtual](#activacion-de-entorno-virtual)
    - [Desactivar entorno virtual](#desactivar-entorno-virtual)
    - [Ejemplos de ERRORES:](#ejemplos-de-errores)
    - [Como sabemos que el entorno virtual esta activo](#como-sabemos-que-el-entorno-virtual-esta-activo)
    - [Eliminar entorno virtual](#eliminar-entorno-virtual)
    - [Posibles problemas en este input \*comentario para mentoras:](#posibles-problemas-en-este-input-comentario-para-mentoras)
    - [Empezamos a instalar lo necesario para el desarrollo web:](#empezamos-a-instalar-lo-necesario-para-el-desarrollo-web)
    - [Para que se utiliza Flask?](#para-que-se-utiliza-flask)
    - [Por que usamos Flask?](#por-que-usamos-flask)
    - [Instalacion de Flask](#instalacion-de-flask)
    - [Instalacion de la libreria requests](#instalacion-de-la-libreria-requests)
- [Input practico #2; empecemos con la creacion de archivos](#input-practico-2-empecemos-con-la-creacion-de-archivos)
  - [Guías anteriores Penguin](#guías-anteriores-penguin)

# Proyecto:

## Aplicación Web con Flask utilizando la API de Rick and Morty y bases de datos.

## Materiales adicionales para pasar antes de la clase:

### Pre clase:

Hola, penguins! 🐧 Mañana será día de workshop de Desarrollo Web, y estaremos trabajando con un montón de cosas nuevas. No se sientan abrumados que lo haremos paso a paso y juntos!
Así también, queremos dejarles unos recursos para que vayan adentrándose.

-   [_Sobre desarrollo web moderno_:](https://youtu.be/heKnQG2ATqg)
-   [_Sobre Flask_:](https://openwebinars.net/blog/que-es-flask/)
-   [_Sobre HTML y desarrollo web_:](https://youtu.be/ni3LEc3kvas)

También, les pedimos si pueden instalar una extensión en Visual Studio Code que se llama _Prettier_. Lo pueden buscar dentro de VS Code en la pestaña de “extensiones” y luego buscan “Prettier”, también “Live server”.

### Otras herramientas y links de documentacion

-   [Documentacion flask](https://flask.palletsprojects.com/en/2.2.x/quickstart/)
-   [Inicio de una aplicacion con Flask con base de datos](https://j2logo.com/tutorial-flask-leccion-5-base-de-datos-con-flask-sqlalchemy/)
-   Link de aplicaciones para visualizar json de las API, respuesta, etc (se recomienda usar Insomnia). [Insomnia](https://insomnia.rest/download), [Postman](https://www.postman.com/)
-   [Página de explicacion de flask](https://j2logo.com/category/blog/flask/)
-   [Jinja template](https://jinja.palletsprojects.com/en/3.1.x/)
-   [Actualizar base de datos con flask](https://j2logo.com/tutorial-flask-leccion-11-actualizar-base-de-datos-sqlalchemy/)
-   [Flask con base de datos tutorial breve](https://es.acervolima.com/conecte-flask-a-una-base-de-datos-con-flask-sqlalchemy/)

## Introduccion al desarrollo web - Instalaciones de dependencias

Las aplicaciones web consisten en dos componentes, una parte llamada cliente y otra parte llamada servidor, y se comunican cuando un cliente envia pedidos al servidor.

Para que estos clientes puedan comunicarse con los servidores web, es necesario que haya un lenguaje o protocolo común, con determinadas reglas sobre cómo debe ocurrir la comunicación. El protocolo utilizado para la comunicación web se llama HTTP, que significa HyperText Transfer Protocol (protocolo de transferencia de hipertexto).

Cualquier navegador (chrome o firefox, por ejemplo) usan HTTP para comunicarse con un servidor web cuando ingresamos una dirección en la barra de navegación, hacemos click en algún enlace de una página, enviamos la información de un formulario o cuando una página actualiza su información dinámica.

![MOSTRAR IMAGEN HTTP conexion usuario servidor](/assets/img/http_req_res.png)

### Que tecnologias vamos a ver hoy en el taller?

-   Flask
-   SQLAlchemy
-   SQLite3
-   TailwindCSS

### Input practico #1: Creacion de carpetas, activacion del entorno virtual y instalacion de librerias

1. Crear una carpeta en su escritorio con el nombre taller-web.
2. Acceder a su carpeta desde Visual Studio Code.
3. Abrir la terminal para comenzar las instalaciones necesarias
    > :bulb: **_OBS:_** para abrir la terminal tenemos que verificar en la esquina derecha que estemos en powershell,etc **(para el futuro se les puede pedir instalar git bash, por ahora nos adaptamos a lo que tengan)**
4. Luego verificar que estemos dentro de nuestra carpeta. taller-web y luego escribir la instruccion para abrir la terminal.

    Ejemplo de como debe de verse:

    ```console
    cd /Users/<usuario>/Desktop/taller-web
    ```

    Si no estamos en la carpeta correcta, nos debemos mover a la carpeta correcta con el comandando cd.

    ```console
    cd [nombre de la carpeta]
    ```

    _Adicionales comando utiles:_

    - Comando ls:

    ```console
    ls
    ```

    > Despliega los archivos que se encuentran en la carpeta

    - Comando cls o clear:

    ```console
    cls
    ```

    ```console
    clear
    ```

    > Limpia la terminal

    - Comando exit:

    ```console
    exit
    ```

    > Salir de la terminal

    - Comando mkdir:

    ```console
    mkdir [nombre de la carpeta]
    ```

    > Para crear una carpeta

    - Comando touch:

    ```console
    touch [nombre del archivo + extension]
    ```

    > Para crear un archivo con un nombre determinado y una extensión.

5. Ahora vamos a instalar las dependencias necesarias para el desarrollo web, para esto vamos a crear primero nuestro entorno virtual mediante los siguientes comandos

    - MAC/Linux:

    ```console
    python3 -m venv venv
    ```

    - Windows:

    ```console
    python -m venv venv
    ```

    o

    ```console
    py -m venv venv
    ```

    > **_OBS:_** De la siguiente linea que escribimos, `python -m venv [venv]` es el nombre que le asignamos a nuestro entorno virtual, puede ser otro pero por convencion se suele usar venv y asi lo usaremos y dentro de ella por defecto se crearan los archivos necesarios para el desarrollo web.
    > **Comentario:** si no escribimos el nombre de la carpeta, por defecto se creara una carpeta con el nombre de venv ejemplo en este caso `python -m venv`

### Para que nos sirve un entorno virtual?

Un entorno virtual se utiliza para resolver conflictos que se pueden generar al realizar instalaciones de librerias que no estan disponibles en el entorno de desarrollo actual.

Un entorno virtual es un entorno Python en el que el intérprete Python, las bibliotecas y los scripts instalados en él están aislados de los instalados en otros entornos virtuales, y (por defecto) cualquier biblioteca instalada en un «sistema» Python, es decir, uno que esté instalado como parte de tu sistema operativo.

Jaz: Sin profundizar mucho, un entorno virtual es como una caja, en donde indicamos la version de cada una de las tecnologias que vamos a usar en nuestro proyecto, y nuestro proyecto correra dentro de esa caja ya que las herramientas estan ahi.

### Activacion de entorno virtual

Como activar el entorno virtual, para ello vamos a escribir el siguiente comando:

        Para UNIX/Mac/Linux ---> source venv/bin/activate ✅
        Para Windows ---> .\venv\Scripts\activate --- o --- ./venv/Scripts/activate para hacer barra invertida se usa [Alt+92]
        (no en todos pinta en colores, generalmente es solo texto blanco)

### Desactivar entorno virtual

Para desactivar darle deactivate ✅
http://ingmmurillo.blogspot.com/2014/08/como-instalar-pip-y-virtualenv-para.html

### Ejemplos de ERRORES:

1. Windows error de scripts inabilitados:
    - correr powershell con permisos de administrador y ejecutar este comando:
    - --> Set-ExecutionPolicy -ExecutionPolicy Unrestricted
    - --> dar si a todo
2. Atender que el env este dentro de la carpeta taller

### Como sabemos que el entorno virtual esta activo

Podemos verificarlo mirando en la esquina izquierda que esta el nombre del entorno virtual activo,
En este caso seria así: `> (venv)`

### Eliminar entorno virtual

       MAC/Linux ---> sudo rm -rf venv ✅ darle deactivate y luego este comando para eliminarlo
       Windows ---> pyenv uninstall venv

### Posibles problemas en este input \*comentario para mentoras:

-Buscar como borrar un entorno virtual e instalar de nuevo. Para desactivar el entorno virtual ---> `deactivate`
-Manejar los comandos para windows y mac
-Como visualizar las librerias instaladas en el entorno virtual `--- pip freeze` corroborar los que estan instalados se puede usar ya con flask, etc.
-Como verificar que uno esta dentro del entorno virtual `--- (venv)`
-Sugerencias de versiones de pip es normal que salga, también buscar como actualizar pip ➡️python -m pip install --upgrade pip #actualizar la version de pip por ejemplo

-   para saber version de pip: `--> pip --version`

### Empezamos a instalar lo necesario para el desarrollo web:

Empezamos instalando flask, que es Flask es un framework escrito en Python, los framework son una serie de pasas establecidos que nos permiten crear aplicaciones web rápidamente y con un mínimo número de líneas de código. Pueden verlos como una receta de cocina para el desarrollo web y esta especificamente se escribe en el lenguaje python.

Flask trabaja ya con Jinja2, que es un motor de plantillas para Python que permite crear plantillas HTML dinámicamente.

### Para que se utiliza Flask?

-   Simplifica y hace más fácil la creación de Aplicaciones Web.
-   Aplicar conceptos aprendidos con operaciones en Python y desplegarlo en un formato más amigable que la consola.

### Por que usamos Flask?

-   Incluye un servidor web de desarrollo
-   Compatible con Python3
-   Buen manejo de rutas
-   Se pueden usar sesiones
-   Open Source

### Instalacion de Flask

    Mac/Linux: pip3 install flask ✅
    Windows: pip install flask

Para verificar que esta instalado, vamos a usar el comando:

    ---> pip list o
    ---> pip freeze ✅

Nos sale listado todo lo que esta instalado con sus respectivas versiones.

### Instalacion de la libreria requests

    Mac/Linux: pip3 install requests ✅
    Windows: python -m pip install requests

# Input practico #2; empecemos con la creacion de archivos

1. `Crear una carpeta llamada servidor `

    Opción 1: Crearla desde la terminal especificando el nombre de la carpeta > mkdir [servidor]

    Opción 2: Pueden crearla sin comandos, entrando a su carpeta taller-web.

2. `Crear dentro el archivo tipo python llamado app.py`

    - _Que es una libreria?_ Es un código externo que realiza funciones de apoyo a nuestro código. Se compone de la palabra reservada import.

        import x // (Importa la librería completa, time, requests).

3. `Escribir el siguiente codigo juntos:`

## Guías anteriores Penguin

-   [Repositorio base para el día de jueves:](https://github.com/kedavema/rick-and-morty-flask)
-   [Repositorio base para el día sábado repaso:](https://github.com/kedavema/todo-app-flask)
