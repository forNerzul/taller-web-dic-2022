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
    - [Teoria de HTML](#teoria-de-html)
    - [Teoria de CSS](#teoria-de-css)
    - [Explicacion de Frameworks y Tailwind CSS.](#explicacion-de-frameworks-y-tailwind-css)
    - [Ejemplo de sintaxis en tailwind css: `ejemplo_tailwind.html`](#ejemplo-de-sintaxis-en-tailwind-css-ejemplo_tailwindhtml)
- [Input practico 3: Instalacion de Tailwind CSS](#input-practico-3-instalacion-de-tailwind-css)
    - [MATERIALES PARA QUE MIREN LUEGO DE LA CLASE O DURANTE:](#materiales-para-que-miren-luego-de-la-clase-o-durante)
  - [Guías anteriores Penguin](#guías-anteriores-penguin)

# Proyecto:

## Aplicación Web con Flask utilizando la API de Rick and Morty y bases de datos.

## Materiales adicionales para pasar antes de la clase:

### Pre clase:

Hola, penguins! 🐧 Mañana será día de workshop de Desarrollo Web, y estaremos trabajando con un montón de cosas nuevas. No se sientan abrumados que lo haremos paso a paso y juntos!
Así también, queremos dejarles unos recursos para que vayan adentrándose.

-   [_Sobre desarrollo web moderno_](https://youtu.be/heKnQG2ATqg)
-   [_Sobre Flask_](https://openwebinars.net/blog/que-es-flask/)
-   [_Sobre HTML y desarrollo web_](https://youtu.be/ni3LEc3kvas)

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
    > 📔 **_OBS:_** para abrir la terminal tenemos que verificar en la esquina derecha que estemos en powershell,etc **(para el futuro se les puede pedir instalar git bash, por ahora nos adaptamos a lo que tengan)**
4. Luego verificar que estemos dentro de nuestra carpeta. taller-web y luego escribir la instruccion para abrir la terminal.

    Ejemplo de como debe de verse:

    ```powershell
    cd /Users/<usuario>/Desktop/taller-web
    ```

    Si no estamos en la carpeta correcta, nos debemos mover a la carpeta correcta con el comandando cd.

    ```bash
    cd [nombre de la carpeta]
    ```

    _Adicionales comando utiles:_

    - Comando `ls`:

    ```bash
    ls
    ```

    > Despliega los archivos que se encuentran en la carpeta

    - Comando `cls` o `clear`:

    ```console
    cls
    ```

    ```console
    clear
    ```

    > Limpia la terminal

    - Comando `exit`:

    ```console
    exit
    ```

    > Salir de la terminal

    - Comando `mkdir`:

    ```bash
    mkdir [nombre de la carpeta]
    ```

    > Para crear una carpeta

    - Comando `touch`:

    ```console
    touch [nombre del archivo + extension]
    ```

    > Para crear un archivo con un nombre determinado y una extensión.

5. Ahora vamos a instalar las dependencias necesarias para el desarrollo web, para esto vamos a crear primero nuestro entorno virtual mediante los siguientes comandos

    - MAC/Linux:

    ```bash
    python3 -m venv venv
    ```

    - Windows:

    ```powershell
    python -m venv venv
    ```

    o

    ```console
    py -m venv venv
    ```

    > 📔**_OBS:_** De la siguiente linea que escribimos, `python -m venv [venv]` es el nombre que le asignamos a nuestro entorno virtual, puede ser otro pero por convencion se suele usar venv y asi lo usaremos y dentro de ella por defecto se crearan los archivos necesarios para el desarrollo web.
    > **Comentario:** si no escribimos el nombre de la carpeta, por defecto se creara una carpeta con el nombre de venv ejemplo en este caso `python -m venv`

### Para que nos sirve un entorno virtual?

Un entorno virtual se utiliza para resolver conflictos que se pueden generar al realizar instalaciones de librerias que no estan disponibles en el entorno de desarrollo actual.

Un entorno virtual es un entorno Python en el que el intérprete Python, las bibliotecas y los scripts instalados en él están aislados de los instalados en otros entornos virtuales, y (por defecto) cualquier biblioteca instalada en un «sistema» Python, es decir, uno que esté instalado como parte de tu sistema operativo.

Jaz: Sin profundizar mucho, un entorno virtual es como una caja, en donde indicamos la version de cada una de las tecnologias que vamos a usar en nuestro proyecto, y nuestro proyecto correra dentro de esa caja ya que las herramientas estan ahi.

### Activacion de entorno virtual

Como activar el entorno virtual, para ello vamos a escribir el siguiente comando:

-   Para UNIX/Mac/Linux:

```console
source venv/bin/activate
```

-   Para Windows:

```console
.\venv\Scripts\activate
```

> 📔**OBS:** para hacer barra invertida se usa [Alt+92]

### Desactivar entorno virtual

Comando `deactivate`:

```console
deactivate
```

> 📔**OBS:** Asegurarse de estar adentro de un venv antes de poder desactivar =)

🍕[Mas info sobre entorno virtual en python](http://ingmmurillo.blogspot.com/2014/08/como-instalar-pip-y-virtualenv-para.html)

### Ejemplos de ERRORES:

1. Windows error de scripts inabilitados:
   Correr Powershell con permisos de administrador y ejecutar este comando:
    ```powershell
    Set-ExecutionPolicy -ExecutionPolicy Unrestricted
    ```
    > 📔**OBS:** darle si a todo a las cosas que aparecen al ejecutar el comando
2. Atender que el env este dentro de la carpeta taller

### Como sabemos que el entorno virtual esta activo

Podemos verificarlo mirando en la esquina izquierda que esta el nombre del entorno virtual activo,
En este caso seria así: `> (venv)`

### Eliminar entorno virtual

-   Para UNIX/Mac/Linux:

```bash
sudo rm -rf venv
```

-   Para Windows:

```console
pyenv uninstall venv
```

> 📔**OBS:** antes de ejecutar `rm` para eliminar el venv asegurarse de desactivar el venv.

### Posibles problemas en este input \*comentario para mentoras:

-Buscar como borrar un entorno virtual e instalar de nuevo. Para desactivar el entorno virtual ---> `deactivate`
-Manejar los comandos para windows y mac
-Como visualizar las librerias instaladas en el entorno virtual `--- pip freeze` corroborar los que estan instalados se puede usar ya con flask, etc.
-Como verificar que uno esta dentro del entorno virtual `--- (venv)`
-Sugerencias de versiones de pip es normal que salga, también buscar como actualizar pip ➡️python -m pip install --upgrade pip #actualizar la version de pip por ejemplo

-   para saber version de pip: `--> pip --version`

## Empezamos a instalar lo necesario para el desarrollo web:

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

-   Para UNIX/Mac/Linux:

```bash
pip3 install flask
```

-   Para Windows:

```console
pip install flask
```

Para verificar que esta instalado, vamos a usar el comando:

    ---> `pip list`
    o tambien
    ---> `pip freeze`

> 📔**OBS:**Nos sale listado todo lo que esta instalado con sus respectivas versiones.

### Instalacion de la libreria requests

-   Para UNIX/Mac/Linux:

```bash
pip3 install requests
```

-   Para Windows:

```console
python -m pip install requests
```

### Input practico #2; empecemos con la creacion de archivos

1. Crear una carpeta llamada servidor

    > Opción 1: Crearla desde la terminal especificando el nombre de la carpeta > `mkdir [servidor]`

    > Opción 2: Pueden crearla sin comandos, entrando a su carpeta taller-web.

2. Crear dentro el archivo tipo python llamado app.py

    > ⚠️**OBS:** Recalcar _Que es una libreria?_ Es un código externo que realiza funciones de apoyo a nuestro código. Se compone de la palabra reservada import.

    ```python
    import [nombre_de_libreria] # (Importa la librería completa, time, requests).
    ```

3. Escribir el siguiente codigo juntos:

```python
#Empezamos a crear la aplicación importando la librería Flask

from flask import Flask #Importa la librería Flask.

app = Flask(__name__) #Crea la aplicación Flask.

@app.route("/") #Crear ruta home
def index(): #Esta es la función que se va a ejecutar en el backend una vez que el usuario ingrese a la ruta definida arriba.
    return "<p>Hello, World!</p>"  #Devuelve una cadena de texto en codigo html del navegador.

if __name__ == "__main__":
    app.run() #Ejecuta la aplicación Flask facilmente desde la terminal.
    debug=True #Ejecuta la aplicación Flask en modo debug (no es necesario volver a ejecutar para actualizar la pagina web.)
```

4. Correr la aplicación tipo python de la terminal:

    > Comando: `python app.py`

5. Activando el Debug Mode:

    > Intro teoria: Flask viene con un modo debug que es muy útil usar mientras estamos desarrollando, ya que cada vez que hagamos un cambio en nuestro código reiniciará el servidor y no tendremos que hacerlo manualmente para que los cambios se tengan en cuenta.

    - Comando para activar DEBUG en flask con WINDOWS:

```console
---> $env:FLASK_ENV = "development" ---> el debug sale abajo active
```

-   Comando para activar DEBUG en flask con LINUX/MAC

```console
---> export FLASK_DEBUG=1
```

-   Comando para ejecutar flask:

```console
---> flask --debug run
```

> 📔**TAREA:**

1. Pedirles la creacion de la carpeta templates y creacion de un archivo index.html dentro del directorio templates
2. En el archivo app.py creamos la ruta index y enviamos un string(“Hola Mundo”)
   TAREA PARA ELLOS:
   Crear una ruta nueva llamada nombre en flask y enviar tu nombre como un string(return "Mi nombre es Mayra")
3. Modificamos el index, con render template
4. Teoria de HTML

### Teoria de HTML

HTML Concepto base:

Las etiquetas HTML son pequeños bloques de código, que indican al navegador como debe interpretar el contenido recogido entre dichas etiquetas. Por ejemplo, si queremos «pintar» un párrafo de texto, hay una etiqueta especifica para que el navegador interprete ese texto como un párrafo.
Generalmente las etiquetas HTML están compuestas por una etiqueta de apertura, y una etiqueta de cierre.
Aunque hay excepciones, como por ejemplo la etiqueta para cargar una imagen que son llamadas etiquetas huérfanas, ya que solo tienen etiqueta de apertura.

Diferenciación etiquetas y atributos. https://carontestudio.com/blog/listado-de-etiquetas-html/

-   Etiquetas fundamentales o raiz html /html
-   Metadatos head title -Etiquetas de secciones body h1 header footer
-   Etiquetas de agrupacion de contenido p hr ol ul div -Etiquetas para incrustar contenido img iframe
-   Etiquetas para crear formularios form input button IMAGEN 05

10. Creamos un HTML, renderizamos el html con render_template, enviamos como parametro el texto 'Hola Mundo' y lo mostramos dentro del p explicando Template Engine llamado Jinja

    Tarea: Crear un html llamado nombre.html, renderizarlo con el render_template en la ruta creada anteriormente, y enviar el nombre como parametro 'nombre', mostrarlo dentro de un h1

    Jaz: Sintaxis basica de Jinja que vamos a manejar:

    -   Usamos `{ {nombre_de_la_variable} }` para usar las variables que mandamos a traves de render_template
    -   Usamos `{ % codigo... % }` para introducir lineas de codigo python en nuestro html
        Visitar la documentacion de JinJa para ver mas detalles

11. `Teoria de CSS y Tailwind CSS: `
12. `Instalacion de Tailwind`

### Teoria de CSS

CSS significa «hojas de estilo en cascada». Es un lenguaje que maneja el diseño y presentación de las páginas web.
Funciona junto con el lenguaje HTML que se encarga del contenido básico de las páginas y nos permite crear reglas que definen propiedades visuales para nuestros elementos.

Estos archivos se generan con la extensión .css.

`> Generar un archivo css llamado style.css y mostrar el siguiente codigo desmostrativo luego borrar el archivo:`

Ejemplo de sintaxis codigo css:

    body {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    color: #ff0000;
    }
    h1 {
    font-size : 4em;
    }

Como tarea pueden hacer: Dentro de la etiqueta body { } editar el “color” del texto con valores
hexadecimales:

R G B (Red, Green, Blue) (Rojo, Verde, Azul)

Ejemplo:
Verde: #00ff00
Turquesa: #00BFFF

Css no se utilizara en este taller porque trabajaremos con framework tailwindcss, pero les compartimos las paginas de documentacion.

Borrar el archivo style.css

---

### Explicacion de Frameworks y Tailwind CSS.

Los frameworks web son un conjunto de herramientas, estilos y librerías dispuestas a través de una estructura o esqueleto base, para el desarrollo de aplicaciones web más escalables y sencillas de mantener.

Gracias a estos frameworks web, podemos ahorrar grandes cantidades de tiempo y costes, pero vamos a profundizar más en las ventajas que tienen, causantes de su gran éxito y expansión.

Tailwind CSS es un framework CSS que permite un desarrollo ágil, basado en clases de utilidad que se pueden aplicar con facilidad en el código HTML y unos flujos de desarrollo que permiten optimizar mucho el peso del código CSS.

### Ejemplo de sintaxis en tailwind css: `ejemplo_tailwind.html`

    <body class="bg-orange-400">
        <h1 class="text-white text-2xl font-bold border-2 m-20 p-5"> Hola mundo!  </h1>
    </body>

---

# Input practico 3: Instalacion de Tailwind CSS

Tarea: Instalamos Tailwind mendiante CDN, para esto buscar en google "tailwindcss", buscar el script donde dice CDN Play y pegar dentro de la etiqueta head

---> ir a la página https://tailwindcss.com/docs/installation/play-cdn

`CDN: <script src="https://cdn.tailwindcss.com"></script>  `

13. `Creamos la estructura de nuestras tarjetas, debe tener "Imagen"(utilizar la del perrito fachero), "Nombre"`

14. `Explicar que los parametros se pueden pasar como listas, diccionarios`
    Tarea 1: Completar la tarjeta añadiendo 'especie' y 'estado' en etiquetas p y una imagen a elección
    Tarea 2: En flask crear una lista de especies y renderizar en el template(card del perrito) utilizando jinja Ejemplo: lista_creada[0]
    Tarea 3: En Flask, crear un diccionario con nombre, especie, estado e imagen y renderizar en el template creado

15. `Buscamos en google una tarjeta hecha en tailwind y reemplazamos nuestras tarjetas y agregamos las clases faltantes de tailwind`
    Hacer juntos.

16. `INTRO A LAS APIs, JSON, Rick and Morty`

(JSON es un formato de texto sencillo para el intercambio de datos.)

API es Application Programming Interface.
Se puede definir como un conjunto de protocolos, procedimientos y herramientas que permiten la interacción entre dos aplicaciones. Serie de protocolos, procedimientos y herramientas que hacen que dos aplicaciones se comuniquen entre si.
Las API conectan diferentes partes de una plataforma de software con el fin de garantizar que la información acabe en el lugar adecuado.

Ejemplos de como funciona y para que sirve:

-   Compartir información de vuelos entre líneas aéreas y sitios de viajes
-   Usar Google Maps en una aplicación de uso compartido de transporte
-   Crear bots de chat en un servicio de mensajería
-   Integrar vídeos de YouTube en una página web
-   Automatizar flujos de trabajo entre herramientas de software
-   Para buscar, recopilar y compartir datos
-   Para reducir el trabajo repetitivo
-   Para fomentar la innovación y la colaboración

.

Jaz: (Ejemplo de que es una api): Conocemos varias aplicaciones que funcionan con mapas, como Bolt o Uber. Estas aplicaciones no desarrollan desde cero un mapa para funcionar, sino que aprovechan que google creo Google Maps. Utilizan la API de Google Maps para obtener informacion que ya existe en la web, ademas que les facilita a la hora de desarrollar, para no tener que desarrollar un mapa desde cero.

(Nota) \* Ver si el ejemplo es acorde al entendimiento de los participantes (que entiendan lo que es maps/uber/bolt)

16. `INTRO A REQUESTS`

El contenido que un cliente web manda al servidor siempre va almacenado en la Request. En Flask la Request se representa mediante el objeto request. Para poder utilizar el objeto request deberemos de importarlo al principio de nuestro programa Flask

    > from flask import request

Una de las primeras cosas para las que podemos utilizar el objeto request es la de saber el tipo de petición que nos hace el cliente: GET, POST.

Explicación Get y POST

La comunicación entre clientes y el servidores en Internet, se realizan a través del protocolo HTTP (Protocolo de Transferencia de Hipertexto).
Un usuario envía una solicitud a un servidor, el cual da como respuesta una pagina web (un documento HTML). Los métodos utilizados para este tipo de comunicación son los parámetros GET y POST.

La diferencia entre estos dos parámetros es que GET, envía la información haciéndola visible en la URL de la pagina web. Mientras que POST, envía la información ocultándola del usuario.

17. `En el servidor utilizamos el metodo get del requests para enviar el json de la api al template`
    Hacemos juntos

18. `Enviar los personajes a travez de un parametro personajes y mostrar en el html en las tarjetas existentes`
    Tarea: Completar Especie, Status e Imagen

19. `Mostrar sintaxis de FOR LOOP con google (buscar: for loop in jinja)`

20. `Agregamos la tarjeta dentro del for loop`

21. `Mejoramos el diseño utilizando más clases de tailwind`

22. `En Flask: creamos la base de datos en app.py con los atributos necesarios`

23. `Creamos una carpeta llamada database`

24.` En la terminal, entramos a la carpeta database(cd database) y ejecutamos el comando: sqlite3 database.db, luego volvemos a la misma carpeta(cd ..).`

25. `Ahora necesitamos crear la tabla Personaje dentro de la base de datos`, para eso abrimos shell de python, escribiendo python3(en sistemas unix) o py(en windows) una vez que se nos abra la shell(deberia aparecer algo como esto '>>>', escribimos: from app import db
    , luego ejecutamos: db.create_all()

26. `Salimos de la shell de python escribiendo exit()`

27. `Envolvemos toda la card dentro de un form, y agregamos inputs type hidden de cada dato necesario para enviarlo al backend`

28. `En Flask: creamos un endpoint para recibir los datos del formulario, explicamos el request.form(name del input), agregamos la url al action del formulario`

29. `Creamos el objeto dentro del endpoint, explicamos el redirect y el url for, redireccionamos al index primero luego cambiaremos la redirección a la nueva ruta`

30. `Mostrar crear un endpoint para renderizar el html con los objetos guardados de la base de datos, enviarlo como un parametro personajes`

31. `Tarea 2: renderizar los personajes con un for loop(jinja) utilizando la card ya creada anteriormente`

---

### MATERIALES PARA QUE MIREN LUEGO DE LA CLASE O DURANTE:

DOCUMENTACION HTML:

1. https://www.w3schools.com/html/html_intro.asp
2. https://developer.mozilla.org/es/docs/Web/HTML

DOCUMENTACION FLASK: 1)https://flask.palletsprojects.com/en/2.1.x/quickstart/

DOCUMENTACION TAILWIND:

1. https://tailwindcss.com/

API a utilizar:

https://rickandmortyapi.com/api/character

image.png de explicacion de API servidor, etc como funciona el sistema (por whatsapp enviado)

JSON viewer:
https://chrome.google.com/webstore/detail/json-viewer/gbmdgpbipfallnflgajpaliibnhdgobh

## Guías anteriores Penguin

-   [Repositorio base para el día de jueves:](https://github.com/kedavema/rick-and-morty-flask)
-   [Repositorio base para el día sábado repaso:](https://github.com/kedavema/todo-app-flask)
