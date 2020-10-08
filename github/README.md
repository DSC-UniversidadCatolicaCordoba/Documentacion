# Github Documentacion
## Tareas
**Jira** es una increible herramienta utilizada por muchas organizaciones que va a permitir administrar el flujo de trabajo. En este documento van a poder apreciar como va a ser la forma de desembolverse ante la situacion de tener que completar una tarea.

Estas practicas son muy utilizadas en ambientes laborales, ya que esto permite organizar a un conjunto de desarrolladores a tener buenas practicas evitando de esta forma que se generen problemas.

En base a lo comentado anteriormente procederemos a mostrar un caso practico de como trabajar. Lo primero de todo es acceder a nuestro tablero de trabajo presionando [aqui](https://dsc-ucc-donation.atlassian.net/secure/RapidBoard.jspa?rapidView=1&selectedIssue=PDDU-2)

Lo que vera sera algo como esto:
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/1.png)

Si pudo ver bien va a tener activiades que estan puestas a su nombre, si accede una de ellas se encontrara con lo siguiente.
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/2.png)
* Titulo
* Descripcion: Lo que se tendra que realizar en la siguiente tarea
* El encargado de la actividad.
* El estado el cual se encuentra la actividad.

Lo que se realizara en el caso de realizar la actividad es cambiar el estado de la actividad de **tarea por hacer** a **en curso**. Si se hizo correctamente veran como cambio de lugar la tarea.
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/3.png)

## Trabajar con Github
Lo que haremos a continuacion es trabajar con Github, para hacer esto iremos al repositorio el cual nos especifica la descripcion de la tarea y procederemos a clonarlo. Se puede realizar de dos formas, descargando el zip o utilizando los comandos de github.

`git clone http-del-repositorio`
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/4.png)
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/5.png)

Luego con `cd NombreDelArchivo` accedemos a la carpeta y podemos poner `code .` para abrir el vscode posicionados sobre esa carpeta.
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/6.png)

Luego procederemos a crear una nueva **branch** para realizar nuestra tarea. Esto se realizara con el siguiente comando `git checkout -b SiglasTablero-Descripcion`. Si no se entendio, ahora descompondremos este comando.
* `git checkout nombre` nos permite cambiar de rama, normalmente uno siempre trabaja en Master
* `git checkout -b nombre` nos permite cambiar de rama y si no existe la crea.
* `SiglasTablero-Descripcion` Es las siglas del tarea, si volvemos imagenes anteriores podemos ver que estamos trabajando con el tablero PDDU (el cual significa **P**ortal **D**e **D**esiciones **U**CC) luego en vez de agregar espacios (ya que github no lo toma como tal) ponemos guiones para separar las palabras. En este caso es github-doc, pero si crear una API para crear nuevos usuarios podriamos llamarla **create-user**. (Algo simple que lo explique).
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/7.png)

*Luego de que se programe todo, hay que proceder a guardarlo en github. Esto es lo que veremos a continuacion*

Lo primero que haremos es ver los cambios. Esto se hace a traves del comando `git status`.
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/8.png)

Luego tiraremos `git add .` para guardar de forma local todos los cambios que hicimos. (Si pueden ver en la siguiente terminal, la consola no tira ninguna respuesta pero el color de la consola cambio)
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/9.png)

Luego procederemos a hacer un comentario. Esto se realiza a traves de `git commit -m "comentario"`. Lo que esta entre comillas es la descripcion de los cambios que realizamos, es recomendable que sea bien descriptivo ya que cuando se hacen muchisimos commits en un proyecto estaria bueno en caso de tener un error volver a una version mas estables.
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/10.png)

**Atender a esto**, Para evitar problemas mas adelantes se recomienda hacer lo siguiente:
* `git checkout master` cambiamos a la rama Master (la principal)
* `git pull` traemos todos los cambios que sufrio el master
* `git checkout nameBranch` volvemos a la rama que estabamos trabajando
* `git merge master` mergeamos con master. Es decir mezclamos los cambios de master en nuestro proyecto.
* Analizamos los cambios. 

Lo anteriormente era un control, vemos si alguien mas hizo cambios en el master. Traemos esos cambios y los arreglamos en local. Luego cuando se soluciones esto volvemos a hacer un git add y commit.

Si esto no se realiza podriamos llegar a enviar bugs cuando hagamos un `pull request` o `PR` (mas adelante comentamos que es si no sabes)

![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/11.png)

* Si no tenemos problemas nos aparecera el mensaje anterior, caso contrario nos aparecere los cambios que se realizaron y debemos de analizar cuales aceptamos y cuales no.

Cuando todos los cambios esten realizados y este todo terminado procederemos a enviar el proyecto. Esto se realiza a travez del comando `git push` o `git push origin nombreRama`. Si llegara a tener un error seguramente github dice cual es el error si llegara a producirse uno, como es el siguiente caso:

![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/12.png)

Ya realizado esto, volveremos al github donde encontraremos el repositorio con una alerta de que hay una nueva rama con nuevos cambios.

![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/13.png)

Si accedemos a ella podremos ver el repo que estabamos trabajando. Aqui precionaremos en **Compare & new pull request**. Esto quiere decir que va a anzalizar el codigo y enviarlo a otra rama.
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/14.png)

Una vez ahi adentro podremos apreciar que es lo mismo que escribimos en el git de nuestra terminal pero con interfaz grafica. 
* Ahi pondremos hacia donde mergeamos (Normalmente si estamos en beta mergeamos a master y si estamos en cualquier rama mergeamos a beta, esto es ya que beta es una version mas inestable que master la cual es la version que entregamos al cliente)
* Luego podremos una descripcion detallada o simplemente el link a la tarea que estabamos desarrollando.
* Luego selecionamos los **Reviewers**. Ellos van a ser los encargados de ver el codigo y aceptarlo si no tienen ningun tipo de problema. (Esto permite calidad en el software, es una muy buena practica)
* Desde este punto puede que pase o que no. Caso contrario vas a tener una devolucion de lo que esta mal (Tener en cuenta que hay un 90% de probabilidad que un codigo pase a la primera, esto no es malo. Sirve para entregar calidad al cliente)
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/15.png)

Una vez precionado enter aparecera una notificacion a los reviewers para que controlen el codigo, si todo esta correcto aparecere la opcion siguiente que es para mergearlo directamente (NUNCA hacer esto de una, hay que esperar la validacion de los demas companieros)
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/16.png)

Cuando se acepte se podra ver la siguiente imagen de que ya esta mergeado
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/17.png)
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/18.png)

Ahora solo queda volver al tablero de trabajo y cambiar la actividad de **en Curso** a **revision** en caso de que hay gente que debe revisar el codigo o **finalizado** si esta terminado al 100% (Osea aceptado en master el cambio)
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/19.png)

Si ponemos que pase a **revision** procedemos a cambiar el encargado a la persona/s encargadas de revisar el codigo y luego el decidira si se termino la actividad o se tiene que volver a hacer porque existen errores.
![alt text](https://github.com/DSC-UniversidadCatolicaCordoba/Documentacion/tree/main/github/imagenes/20.png)

### Resumen de comandos
* `git clone ...`
* `git checkout -b nombreRama`
* Codear
* `git status`
* `git add .`
* `git commit -m "descripcion"`
* `git checkout master` // o beta, depende a que rama vamos a hacer el pull request
* `git pull`
* `git checkout nombreRama`
* `git merge master`
* Corregir todos los erroes
* `git status` `git add .` `git commit -m"merge with master"`
* `git push origen nombreRama`
* Hacer un pull request (PR)

### Para leer mas sobre github
* https://www.atlassian.com/es/git/tutorials/using-branches/git-checkout


