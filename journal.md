# cien días de codificación

## Día 1 - 2021-03-21

Este será mi primer día de codificación y de escribir durante 100 días.
Anteriormente no había encontrado nada que me motivara a codificar por un número de días ni tampoco algo que me mantuviera interesado en llevar un diario de forma constante.
Decidí entonces buscar en un repositorio de software (GitHub) por un proyecto abierto que desarrolle un editor de texto en mi lenguaje de programación favorito (Python).
Fue así como encontré el editor [chronoflask](https://github.com/kmbn/chronoflask). 
Este editor está escrito en Python y usa el microframework Flask para hacer accesible este aplicativo desde un navegador. 
El proyecto me interesó muchísimo porque se vé sencillo y me permitirá entonces escribir pero también me permitirá adicionar nuevas características al editor de ser necesario.
Es más, como el editor es sencillo puedo imaginarme su diseño y repensarmelo haciéndolo orientado a microservicios lo que facilitará su extensiblidad. 

Emocionado, hice una copia (cloné el software en términos de Git [https://github.com/josanabr/chronoflask](https://github.com/josanabr/chronoflask)) del software y lo descargué. 
Sin embargo, he encontrado que el código no compila. 
**Primer gran escollo.**
Código de terceros y código muy antiguo (como este es el caso, un código de 4 años) es probable que no pueda compilar. 
Está bien, no me funcionó, no se ejecutó pero este será el primer escollo a resolver.

**¿Cómo traer a la vida un software antiguo?**
Lo primero que identifiqué es que una de las librerías que ofrecía problemas estaba bastante desactualizada. 
Esa librería estaba relacionada con WTForms. 
Esa librería parece que también tiene algún tipo de asociación con el microframework porque existe un requerimiento de Flask-WTF.
Hice las averiguaciones de versiones actuales del código y no puse las más recientes sino otras que estuvieran entre las versiones con las que venía el software y las versiones actuales. 
Fue así como Flask-WTF pasó de 0.9.4 a 0.10 y WTForms de 1.0.5 a 2.0.0.

Una vez se hicieron los ajustes en el `requirements.txt` se lanzo el `pip install -r requirements`, se lanzó la ejecución del aplicativo `python run.py` y funcionó.

Creo que el día de mañana estudiaré un poco el flujo del aplicativo y trataré de entender como funciona WTForms y Flask-WTF. 
Entre otras cosas creo que ellos se encargan de hacer validación de los usuarios. 
Es posible que sea un buen momento de actualizar el aplicativo de modo que incorpore otro tipo de librerías para autenticar usuarios.

---

# Ideal del aplicativo

Al identificar las partes funcionales del software, la idea es migrar el software para que sea orientado a servicios.

---

## Día 2 - 2021-03-22

Este es el segundo día de los 100 días que se dedicarán a la codificación. 
He decidido que dedicaré las primeras partes de este ejercicio diario a revisar las notas del día anterior. 
De esta manera no solo avanzaré con las notas del nuevo día sino que también depuraré lo que se hizo el día inmediatamente anterior.

Este ejercicio me tomó alrededor de 7 minutos.

<table>
<tr>
<th>Tiempo de revision </th>
</tr>
<tr>
<td> 7 minutos </td> 
</tr>
</table>

Vale la pena resaltar que este no es solo un ejercicio de codificación sino que también es un ejercicio de escritura.
El día de hoy es final del segundo puente de lo que va corrido del año.
Puente para los colombianos es una secuencia de tres días en los cuales no se trabaja, desde el sábado hasta el lunes. 
Estos puentes son usados por los colombianos para distraerse, salir a pasear, visitar familiareas y en general hacer turismo interno.
Nosotros, mi esposa, su familia y yo; estuvimos este fin de semana en Pereira. 
Una de sus tías se encuentra mal de salud y fue la oportunidad para visitarla.
La señora no está bien de salud pero está rodeada de personas que cuidan de ella.

Han sido días muy lluviosos en Colombia y hoy en particular hubo inundaciones importantes en algunas zonas de la ciudad donde yo vivo. 
Yo vivo en la ciudad de Cali. 
Al momento no hay víctimas mortales pero seguro si hay daños y pérdidas materiales.

**Volviendo a la programación** debo decir que he decidido leer el código y pensar cual es la arquitectura del aplicativo.
Es decir, leer el código e identificar cuales son los elementos funcionales del aplicativo. 
Hacer un diagrama.
A continuación identificaré cuantos programas en Python por orden de aparición:

<table>
<tr>
<td>1 </td>
<td>./run.py </td>
</tr>
<tr>
<td>2 </td>
<td>./app/mail.py </td>
</tr>
<tr>
<td>3 </td>
<td>./app/db.py </td>
</tr>
<tr>
<td>4 </td>
<td>./app/auth/__init__.py </td>
</tr>
<tr>
<td>5 </td>
<td>./app/auth/forms.py </td>
</tr>
<tr>
<td>6 </td>
<td>./app/auth/views.py </td>
</tr>
<tr>
<td>7 </td>
<td>./app/admin/__init__.py </td>
</tr>
<tr>
<td>8 </td>
<td>./app/admin/forms.py </td>
</tr>
<tr>
<td>9 </td>
<td>./app/admin/views.py </td>
</tr>
<tr>
<td>10 </td>
<td>./app/__init__.py </td>
</tr>
<tr>
<td>11 </td>
<td>./app/details.py </td>
</tr>
<tr>
<td>12 </td>
<td>./app/pagination.py </td>
</tr>
<tr>
<td>13 </td>
<td>./app/parse.py </td>
</tr>
<tr>
<td>14 </td>
<td>./app/main/__init__.py </td>
</tr>
<tr>
<td>15 </td>
<td>./app/main/forms.py </td>
</tr>
<tr>
<td>16 </td>
<td>./app/main/errors.py </td>
</tr>
<tr>
<td>17 </td>
<td>./app/main/views.py </td>
</tr>
<tr>
<td>18 </td>
<td>./app/decorators.py </td>
</tr>
      
</table>

Así mismo, he sacado el número de líneas que tienen los archivos o códigos fuentes.
<table>
<tr>
<th> número de líneas </th>
<th> nombre del archivo </th>
</tr>
<tr>
 <td>4 </td>
 <td> ./app/admin/__init__.py </td>
</tr>
<tr>
<td> 5 </td>
<td> ./app/main/__init__.py </td>
</tr>
<tr>
<td> 5 </td> 
<td>./run.py </td>
</tr>
<tr>
<td> 7 </td>
<td> ./app/auth/__init__.py </td>
</tr>
<tr>
<td> 7 </td>
<td> ./app/details.py </td>
</tr>
<tr>
<td> 11 </td>
<td> ./app/decorators.py </td>
</tr>
<tr>
<td> 14</td>
<td> ./app/admin/forms.py </td>
</tr>
<tr>
<td> 15 </td>
<td> ./app/main/errors.py </td>
</tr>
<tr>
<td> 19 </td>
<td> ./app/mail.py </td>
</tr>
<tr>
<td> 38 </td>
<td> ./app/db.py </td>
</tr>
<tr>
<td> 41 </td>
<td> ./app/__init__.py </td>
</tr>
<tr>
<td> 41 </td>
<td> ./app/main/forms.py </td>
</tr>
<tr>
<td> 42 </td>
<td>./app/pagination.py </td>
</tr>
<tr>
<td> 44 </td>
<td> ./app/admin/views.py </td>
</tr>
<tr>
<td> 95 </td>
<td>./app/parse.py </td>
</tr>
<tr>
<td> 111 </td>
<td>./app/auth/forms.py </td>
</tr>
<tr>
<td> 144 </td>
<td> ./app/auth/views.py </td>
</tr>
<tr>
<td> 172 </td>
<td> ./app/main/views.py </td>
</tr>
</table>

Hay 810 líneas para 18 archivos. 
Eso equivale a 45 líneas promedio por archivo. 
Nada complejo.
Así mismo y observando la forma como se generaron los archivos, se pueden identificar dos bloques:

* `./run.py`
* `./app`

El "módulo" `./app` consta de los siguientes elementos:

* `mail.py`
* `db.py`
* `auth`
* `admin`
* `__init__.py`
* `details.py`
* `pagination.py`
* `parse.py`
* `main`
* `decorators`

Aprendí que en el `run.py` hay una línea que hace el import del paquete `app` de este aplicativo. 
Esto causa que se ejecute lo que está en el archivo `__init__.py`.
Esto está documentado [aquí](https://docs.python.org/3/reference/import.html#regular-packages).

Mañana estudiaré el `__init__.py` del paquete `app`. 

---

## Día 3 - 2021-03-23

El día de hoy fue un día con varias tareas administrativas:

* Reuniones para gestionar el proceso de registrar a la Universidad del Valle en AWS Educate. Se habló con Isabella y Alejandro de AWS Educate los cuales me dieron los pasos para llevar a cabo esta actividad. Ya me puse en contacto con Laura Rodríguez para que desde la Universidad me brinden apoyo en lo que requiera.

* Tuve clase de curso dirigido para validar avances de estudiantes de posgrado que toman el curso.

* Se escribió un preliminar de un documento que será la guía para un podcast con tips sobre infraestructuras computacionales. [Aquí](https://docs.google.com/document/d/10kIxK-g-NkP_64U6aZq_dOHabn4G8eibOEmOz19yqSI/edit?usp=sharing) el enlace al documento que debo pulir mañana y grabar mañana el podcast.

* Se escribió el guión para el podcast de la clase del jueves y se subió a la plataforma [anchor.fm](https://anchor.fm).

* También estuve ensayando algo de bajo para practicar un coro que se presentará el día domingo. 

Hoy comencé a leer un libro de Fiodor Dostoievski llamado **Notes from undeground**. 
El libro parece interesante. 
Lo que entendí, es que el libro aborda la problemática de un hombre que tiene alguna especie de subconsciente que lo mortifica. 
En el primer capítulo se describe él mismo (el personaje de la obra) como un hombre enfermo con una enfermedad quizá del hídago por muchos años.
También se muestra como un hombre recio y con un desprecio por la vida después de los 40 años.
Parece que será una lectura interesante.

**Respecto a la programación** hoy comencé a estudiar el archivo `__init__.py` en el directorio `app`. 
Aunque es un programa corto refleja algo muy interesante y es el concepto de *blueprint*.
Si bien es cierto de forma inicial no logré con certeza entender a lo que se refiere, si logré comprender que el concepto de *blueprint* permite que se desarrolle una aplicación de manera modular. 
El construir la aplicación de manera modular permite el descomponer la aplicación en elementos funcionales que podrían luego ser usados en otras aplicaciones, por ejemplo: se puede pensar en un módulo de autenticación.
Este módulo se puede reutilizar en muchas y diferentes aplicaciones.

Observando entonces los *blueprint* que hay en el `__init__.py` se puede intuir que hay al menos tres grandes bloques, el `admin`, el `auth` y el `main`.
Luego lo que hay son importaciones de vistas y errores, inicialización de algunas configuraciones de la aplicación, puesta a punto del correo y el *boostrap*.

Para mañana seguiré revisando lo del *blueprint* en [este enlace](https://realpython.com/flask-blueprint/). 
Quizá me dé tiempo para ver lo de la configuración del objeto `app`([Configuration Handling](https://flask.palletsprojects.com/en/1.1.x/config/)), que significa el constructor `Mail(app)` y lo del `Boostrap(app)`.

Realmente hoy el avance fue poco pero:

* Hubo avance. Con relación al día anterior observo que he avanzado poco pero he avanzado. Solo he visto el código de `app/__init__.py`. He leido lo del concepto de blueprint en [este enlace](https://realpython.com/flask-blueprint/) y parece que es un recurso muy útil que provee el microframework Flask.

* Aprendí algo nuevo. Cada vez que veo este código sencillo, veo que aprendo algo aún en aplicaciones sencillas. Esto me emociona porque estoy incrementando mi arsenal de conocimiento.

* Estoy emocionado de aprender de otros. Leer código no es muy diferente de leer libros en el siguiente sentido. Leer libros te permite conocer de puntos de vistas de otras personas. Aprender de sus experiencias, de su sabiduría, de su cultura. Leer código es aprender técnicas de programación, de diseño de aplicaciones, de trucos, de técnicas, etc. Realmente es muy excitante.

Casi lo olvido, el día de ayer aprendí de los archivo `__init__.py` en [este enlace](https://docs.python.org/3/reference/import.html#regular-packages). 
El `__init__.py` es un archivo que se localiza dentro de un directorio, que en el contexto de Python, se convierte en un paquete. 
Al importar (`import`) un paquete este `__init__.py` es lo primero que se ejecuta a la hora de importar el paquete.

En estos 100 días aprenderé de muchas cosas, quizá no con la suficiente profundidad pero ciertamente aprenderé mucho.

Lo olvidaba, el tiempo de edición del día anterior fue el siguiente:

<table>
<tr>
<th>Tiempo de revision </th>
</tr>
<tr>
<td> 6 minutos </td> 
</tr>
</table>

No estoy seguro la causa pero inicialmente pienso que hubo menos líneas que editar.
