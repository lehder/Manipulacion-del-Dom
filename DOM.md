# CURSO DE MANIPULACION DEL DOM

# CLASE 1 

En este curso vamos a aprender a manipular el DOM con JavaScript, vamos a hacer esto sin framenwors y sin librerias.

Para comenzar vamos a descargar Node JS en nuestra computadora.

```js

https://nodejs.org/es/download/

```

Y este sera el repositorio de GitHub.

```js

GitHub - jonalvarezz/platzi-dom: Workshops del Curso de manipulación del DOM de Platzi

```

# Clase 2

# Que es el DOM ?

El DOM es un concepto maravilloso que utliza todos lo navegadores para renderizar y trabajar sobre una pagina web, todo esto empieza en un proceso llamado el (CRITICAL RENDERING PATH), Y este es un proceso importante que los navegadores hacen para que el codigo que nosotros enviemos (html, css, y javascript) se convierta en pixeles en la pantalla de nuestros ususarios, asi de importante es, se puede dividir en muchas faces entre 4 o 5, pero lo que a nosotros nos interesa en este curso y para esta introducccion, es conocer que como parte de este proceso, el navegador crea dos arboles.

* Un arbol llamado el DOM (Document Object Model)

Y otro arbol llamado

* CSSOM (CSS Object Model)

Y se le llama arboles, por que esa es la estructura de datos que representan.

El DOM corresponde al arbol del Html, y el CSSOM corresponde al arbol del Css.

Lo podriamos visualizar de esta manera, tenemos una pagina con un Html, que a su ves tiene un (HEAD), y este tiene un (TITLE), con un (P) o parrafo, y este imprime otro nodo con un (H1) y otro (P), por esta razon se le llama arbol.

De esta manera tenemos una representacion para nosotros los humanos lo que es una reprecentacion de nodos.

Para resumirlo, 
* El DOM es una reprecentacion del Html.
* Es una estructura en forma de arbol de nodos, cada hoja o arista corresponde a un nodo de Html.
* Y por ultimo el DOM es un modelo que existe para ser modificado, el proposito para que se construya un DOM, es que por medio del lenguaje de programacion, y muy espesificamente, por medio de JS, podamos modificar y manipular el DOM a nuestro antojo.

# Clase 3


# Web APIs modernas

Cuando nosotros conbinamos el DOM con JavaScript, obtenemos una Web API.

DOM + JavaScript = Web API

API: No es nada mas que un puente, otra forma para poder ver esto, es que una Web API  nos permite conectar el DOM con JavaScript, para que nosotros podamos manipularlo, podamos agregra o manipularlo a nuestro antojo, existen mas de 70 APIs.

El DOM que es lo que estamos viendo ahora es una de ellas, pero existen para hacer animaciones, para hacer Dragan Drow, para manejar archivos, pero tambien para cosas super avansadas como transmision de video, RTC, manejo de video juegos, y tambien APIs un poco mas experimentales, para realizar pagos quqe no dependen de librerias o de servicios externos.

La forma de como nosotros trabajamos con Web APIs va a ser atra ves de dos tipos de preguntas, la primera es.

# (Como utilizo una Web API?)

El citio web (developer.mozilla.org) nos va a responder esta pregunta, este citio que tambien se conoce como (MDN) Es nuetra biblia en el desarrollo web, 

Seguida  de esta, nos debemos preguntar.

# (Puedo usar esta API?)
Tengamos en cuenta que si bien una API existe, no significa que todos los navegadores la esten utlizando o que la soporten en igual medida, a dia de hoy Google Chrom es pionero de las APIs.

El citio (caniuse.com) nos va a responder de una manera muy resumida, las caracteristicas de una Web API que tiene en particular en los navegadores

Apartir de aqui vamos a aprender a manipular nodos.


# Clase 4

# Leer Nodos

La primera de las operaciones que vamos a aprender con el DOM, es como leer un Nodo, como vamos a traerlo de ese arbol , y como vamos a leerlo.

Esto es lo que sostiene internet, y a todas las aplicaciones que se encuentran en el mundo,  

# document.getElementById= 
Para traer un elemento por su ID.

# parent.getElementByTagName=
Para obtenerlo por el nombre de la etiqueta.

# parent.getElementByClassName=
Para traerlo por medio del nombre de la clase.

Para conocer esto mas a fondo debemos ir a la pantalla paracticarlo, vamos a ir a la pagina de (getbootstrap.com) por que parte de sus ejemplos estan llenos de elemntos que podemos manipular, vamos a Examples, vamos a utlizar (Checkout form), vamos a abrir las erramientas del navegador, si queremos ver la imagen de como es un arbol, o que es el DOM, aca lo podemos ver, podemos ver en la consola en (Consola) para poder examinar codigo JavaScript, recordemos que nosotros tenemos tres poderosas ayudas que se llaman
(document.getElemntById, parent.getElementByTagName, parent.getElementByClassName)

Vamos a comenzar con el primero (document.getElementById), si nosotros inspeccionamos los elementos del Html, vamos a encontrar algun input en algun lado que debe de tener un ID, por ejemplo vamos a a inspeccionar este elemento 

<div class="col-md-6 mb-3">...</div>
 si nosotros lo expandimos, nos vamos a encotar con input

<div class="col-md-6 mb-3">

<input type="text" class="form-control" id="firsName" placeholder value required>...</input>

</div> 

Efectivamente vemos que cuando fue escrito en el Html, fue escrito con un ID con el nombre "firsName", siendo asi yo puedo utilizar JavaScript para escribir algo como document.getElementById(' ') y dentro vamos a poner el nombre exacto de la clase, en este caso es (firsName)

```js

document.getElementById('firsName')

```

Si le damos enter a la consola, ella nos dira, efectivamente dentro de esta clase tenemos el siguiente elemento, que contiene efectivamente un input.

De la misma manera si utlizamos (parent.getElementByTagName) y aqui poder expesificar una etiqueta para que JavaScript me la devuelva, como por ejemplo si le decimos, traeme todos los (inputs) que corresponda a esta etiqueta, JavaScript y el DOM y la Web API, me va a devolver una coleccion de todas las etiquetas que correspondan a un (input)

```js

document.getElementByTagName('input')


HTMLCollection(17) [input.form-control, input#firstName.form-control, input#lastName.form-control, input#username.form-control, input#email.form-control, input#address.form-control, input#address2.form-control, input#zip.form-control, input#same-address.form-check-input, input#save-info.form-check-input, input#credit.form-check-input, input#debit.form-check-input, input#paypal.form-check-input, input#cc-name.form-control, input#cc-number.form-control, input#cc-expiration.form-control, input#cc-cvv.form-control, firstName: input#firstName.form-control, lastName: input#lastName.form-control, username: input#username.form-control, email: input#email.form-control, address: input#address.form-control, …]0: input.form-control1: input#firstName.form-control2: input#lastName.form-control3: input#username.form-control4: input#email.form-control5: input#address.form-control6: input#address2.form-control7: input#zip.form-control8: input#same-address.form-check-input9: input#save-info.form-check-input10: input#credit.form-check-input11: input#debit.form-check-input12: input#paypal.form-check-input13: input#cc-name.form-control14: input#cc-number.form-control15: input#cc-expiration.form-control16: input#cc-cvv.form-controladdress: input#address.form-controladdress2: input#address2.form-controlcc-cvv: input#cc-cvv.form-controlcc-expiration: input#cc-expiration.form-controlcc-name: input#cc-name.form-controlcc-number: input#cc-number.form-controlcredit: input#credit.form-check-inputdebit: input#debit.form-check-inputemail: input#email.form-controlfirstName: input#firstName.form-controllastName: input#lastName.form-controlpaymentMethod: input#credit.form-check-inputpaypal: input#paypal.form-check-inputsame-address: input#same-address.form-check-inputsave-info: input#save-info.form-check-inputusername: input#username.form-controlzip: input#zip.form-controllength: 17[[Prototype]]: HTMLCollection

```

Una cosa curiosa entre los dos es que (document.getElementById) va a retornar unicamente un elemento, por que solo puede haber un ID, mientras que por etiquetas pueden haber 0, o 1, o mas etiquetas.

De la misma manera sucede con la etiqueta (document.getElementByName) este tipo de selector puede tener 1 o mas de un elemento, si por ejemplo nos traemos la classe que se llama (form-control) el browser y mas expecificamente JS me deberian devolver todos los elementos que hacen mash con la clase (form-control)

```js

document.getElentByName('form-control')

NodeList []length: 0[[Prototype]]: NodeListentries: ƒ entries()forEach: ƒ forEach()item: ƒ item()keys: ƒ keys()length: (...)values: ƒ values()constructor: ƒ NodeList()Symbol(Symbol.iterator): ƒ values()Symbol(Symbol.toStringTag): "NodeList"get length: ƒ length()[[Prototype]]: Object

```

Otra cosa que debemos tener en cuenta, es que cuando utlizamos (document.getElementsByClassName) unicamente pasamos el nombre no es necesario poner un punto al principio como si se tratara de Css, simplemente el nombre de la classe y ejecutamos. 

```js

document.getElementsByClassName(".form-control)

document.getElementsByClassName("form-control)

```

Si bien esta clase de selector son nuestros heroes, tambien debemos tener en cuenta que la web API a cambiado muchicimo y a evolucionado, generalmente utilizar estos selectoner no es muy conveniente cuando trabajamos en aplicaciones reales.

Es por esto que existen dos selectores mas cool que se llaman.

```js

querySelector

querySelectorAll


```

# querySelector()

Este es un selector que me va a dejar elegir o seleccionar desdel DOM cualquier cosa que yo espesifique dentro de su primer argumento en forma de cadena, esto tambiene esta ligado a los selectores del Css, asi que si yo quisiera obtener un ID, deberiamos hacerlo asi, llamamos al selector y le pasamos el ID, tengamos en cuenta que si hacemos la llamada por su ID, debemos empezar con un numeral (#).

```js

document.querySelector('#username')

<input type="text" class="form-control" id="username" placeholder="Username" required>

```

De esta misma manera podemos decirle que queremos todas las etiquetas de tipo input, 

```js

document.querySelector('input')

<input type="text" class="form-control" placeholder="Promo code">

```

Pero este me va a traer unicamente el primer elemento que se encuentre, y esto funciona iguamente para las classes. 

Funciona de igual forma para las clases, si quicieramos traernos una clase como lo hicimos hace poco con (form-control).

En este caso vamos a utilizar antes de colocar el nombre de la clase pondremos un punto 
('.form-control'), por que asi se especifica en Css, de esta manera le estamos diciendo, traeme el primer elemento que tenga la classe (.form-control), en este caso me trajo este elemento que es un (input).


```js

document.querySelector('.form-control')

<input type="text" class="form-control" placeholder="Promo code">

```

querySelector acepta cualquier tipo de selector que tenga sentido en Css, como por ejemplo y un poco innecesario pero que tambien lo haceptaria es de esta manera.

```js

document.querySelector('div[class="row g-5"]')




<div class="col-md-5 col-lg-4 order-md-last">
        <h4 class="d-flex justify-content-between align-items-center mb-3">
          <span class="text-primary">Your cart</span>
          <span class="badge bg-primary rounded-pill">3</span>
        </h4>
        <ul class="list-group mb-3">
          <li class="list-group-item d-flex justify-content-between lh-sm">
            <div>
              <h6 class="my-0">Product name</h6>
              <small class="text-body-secondary">Brief description</small>
            </div>
            <span class="text-body-secondary">$12</span>
          </li>
          <li class="list-group-item d-flex justify-content-between lh-sm">
            <div>
              <h6 class="my-0">Second product</h6>
              <small class="text-body-secondary">Brief description</small>
            </div>
            <span class="text-body-secondary">$8</span>
          </li>
          <li class="list-group-item d-flex justify-content-between lh-sm">
            <div>
              <h6 class="my-0">Third item</h6>
              <small class="text-body-secondary">Brief description</small>
            </div>
            <span class="text-body-secondary">$5</span>
          </li>
          <li class="list-group-item d-flex justify-content-between bg-body-tertiary">
            <div class="text-success">
              <h6 class="my-0">Promo code</h6>
              <small>EXAMPLECODE</small>
            </div>
            <span class="text-success">−$5</span>
          </li>
          <li class="list-group-item d-flex justify-content-between">
            <span>Total (USD)</span>
            <strong>$20</strong>
          </li>
        </ul>

        <form class="card p-2">
          <div class="input-group">
            <input type="text" class="form-control" placeholder="Promo code">
            <button type="submit" class="btn btn-secondary">Redeem</button>
          </div>
        </form>
      </div>

```

Esto seria lo que nos devolveria, aun que esta manera es poco usada he innecesaria, este es un selector aceptado por querySelector y podemos tener en cunta que tambien lo podemos hacer de esta manera.

# querySelectorAll

Ahora podemos utlizar querySelectorAll cuando queramos traernos todos los elementos que concuerden con ese selector, si volvemos a nuestro primer ejemplo de (input), le estamos diciendo que no queremos uno, si no que con (All) le estamos diciendo que los queremos todos.

```js

document.querySelectorAll('input');

NodeList(17) [input.form-control, input#firstName.form-control, input#lastName.form-control, input#username.form-control, input#email.form-control, input#address.form-control, input#address2.form-control, input#zip.form-control, input#same-address.form-check-input, input#save-info.form-check-input, input#credit.form-check-input, input#debit.form-check-input, input#paypal.form-check-input, input#cc-name.form-control, input#cc-number.form-control, input#cc-expiration.form-control, input#cc-cvv.form-control]0: input.form-control1: input#firstName.form-control2: input#lastName.form-control3: input#username.form-control4: input#email.form-control5: input#address.form-control6: input#address2.form-control7: input#zip.form-control8: input#same-address.form-check-input9: input#save-info.form-check-input10: input#credit.form-check-input11: input#debit.form-check-input12: input#paypal.form-check-input13: input#cc-name.form-control14: input#cc-number.form-control15: input#cc-expiration.form-control16: input#cc-cvv.form-controllength: 17[[Prototype]]: NodeList


```

Y esto es todo lo que me va a devolver, tambien me dice que me devuelve un ( NodeList(17) ) con dieciciete elementos.

Tambien le podemos decir que nos traiga todas las classes que contengan por ejemplo la classe="mb-3, de esta manera.

```js

document.querySelectorAll('.mb-3')



NodeList(5) [div.dropdown.position-fixed.bottom-0.end-0.mb-3.me-3.bd-mode-toggle, h4.d-flex.justify-content-between.align-items-center.mb-3, ul.list-group.mb-3, h4.mb-3, h4.mb-3]0: div.dropdown.position-fixed.bottom-0.end-0.mb-3.me-3.bd-mode-toggle1: h4.d-flex.justify-content-between.align-items-center.mb-32: ul.list-group.mb-33: h4.mb-34: h4.mb-3length: 5[[Prototype]]: NodeList


```

 En tonces el me va a decir que me devuelve cinco classes, que corresponde a difenetes etiquetas, pero cada una de ellas tiene la clase que me estas pidiendo.

En la gran malloria de aplicaciones, querySelector, y querySelectoAll van a ser los selectores que nos van a dar la mayor flexibilidad y el mayor beneficio cuando estemos manipulando el DOM.

NOTA:

Hay un detalle muy pequeño que tiene el querySelectorAll, que lo vamos a ver en la siguiente classe.


# Clase 5

# NodeLists vs Array

Si nos fijamos, cuando utlizamos anteriormente el (querySelectorAll) este nos devolvio un tipode dato llamado (NodeList)

NodeList es diferente a un Array, y ojo esta es de esae tipo de preguntas que salen en las entrevistas de frondtend y que hoy la vamos a ver en mas detalle.

# Cual es la diferencia entre un NodeList y un Array, y por que es tan importante?

Veamoslo en el navegador, cuando utilizamos el (querySelectorAll) el navegador nos devuelve el tipo (NodeList) 

```js

document.querySelectorAll('div');

NodeList(46) [div.dropdown.position-fixed.bottom-0.end-0.mb-3.me-3.bd-mode-toggle, div.container, div.py-5.text-center, div.row.g-5, div.col-md-5.col-lg-4.order-md-last, div, div, div, div.text-success, div.input-group, 

```

El NodeList es muy diferente a un Array de toda la vida que tiene esta expresion [], 
Entonces lo que vamos hacer es que esta expresion la vamos a guardar en una variable para que la analicemos.

```js

const nodeList = document.querySelectorAll('div');

undefined
nodeList.length
46

nodeList.for
undefined

```

La principal diferencia es que NodeList carece de operaciones que los arrays si tienen, por ejemplo este NodeList tiene una longitud que es esperado, tambien tiene metodos para hacer un forEach,
pero por ejemplo no puedo utilizar (map) por que no existe, (some) tampoco existe, (filter) tampoco existe, tampoco otros metodos como el (reduce), y otros metodos que los arrays si tienen etc

Si nosotros construimos en su contraparte un Array, como por ejemplo crearemos un Array vacio y le pondremos como nombre (arr) y le diremos que simplemente sea un arry basio, veremos que si podremos tener los metodos que mensionamos anteriormente.

```js

const arr = [] 

undefined

arr.filter
ƒ filter() { [native code] }
arr.reduce
ƒ reduce() { [native code] }


```

Ahora bien tenemos una forma facil de pasar un NodeList a Array, utilizando la numenclatura de (As) y podemos inplementarla de la siguiente manera, vamos a crear una variable y le pondremos un nombre cualquiera, en este caso (nodeListAsArray) esta sera = a (nodeList) que es la variable donde tenemos este tipo de dato, pero a este lo vamos a englobar dentro de un Array osea [nodeList] pero debemos de utilizar el spray operector de JS para hacer la transformacion de esta manera [...nodeList] el Spray operactor de JS son los tres puntos anates del metodo.

Con esto [...nodeList] yo le estoy diciendo que este nodeList lo voy a convertir en un Array, asi que si ejecuto esta linea de codigo, nodeList que ahora se llama (nodeListAsArray) tendra los metodos abansados que contiene un Array.

```js

const nodeListAsArray = [...nodeList]
undefined
const nodeListAsArray = [...nodeList];
undefined
nodeListAsArray.filter
ƒ filter() { [native code] }
nodeListAsArray.m
undefined
nodeListAsArray.map
ƒ map() { [native code] }
nodeListAsArray.reduce
ƒ reduce() { [native code] }

```

```js

document.querySelectorAll('div')

NodeList(46) [div.dropdown.position-fixed.bottom-0.end-0.mb-3.me-3.bd-mode-toggle, div.container, div.py-5.text-center, div.row.g-5, div.col-md-5.col-lg-4.order-md-last, div, div, div, div.text-success, div.input-group, div.col-md-7.col-lg-8, div.row.g-3, div.col-sm-6, div.invalid-feedback, div.col-sm-6, div.invalid-feedback, div.col-12, div.input-group.has-validation, div.invalid-feedback, div.col-12, div.invalid-feedback, div.col-12, div.invalid-feedback, div.col-12, div.col-md-5, div.invalid-feedback, div.col-md-4, div.invalid-feedback, div.col-md-3, div.invalid-feedback, div.form-check, div.form-check, div.my-3, div.form-check, div.form-check, div.form-check, div.row.gy-3, div.col-md-6, div.invalid-feedback, div.col-md-6, div.invalid-feedback, div.col-md-3, div.invalid-feedback, div.col-md-3, div.invalid-feedback, div#loom-companion-mv3]
const nodeList = document.querySelectorAll('div');
undefined
const nodeListAsArray = [...nodeList];
undefined
nodeListAsArray.filter
ƒ filter() { [native code] }
nodeListAsArray.m
undefined
nodeListAsArray.map
ƒ map() { [native code] }
nodeListAsArray.reduce
ƒ reduce() { [native code] }

```

Esto si bien parece que sea una diferencia minuscula y que podemos ignorar, lo aconsejable es que cada que tengamos un nodeList lo pasemos a Array, no solo porque trabajar con Arrays es mas conveniente, si no por que los navegadores y los motores de JS, sobre todo el motos V8, esta optimizado para trabajar con Arrays y no con nodeList, asi que cuando trabajemos con colecciones muy grandes de nodos, aseguremosnos de que sean Arrays, vamos a la siguiente clase donde veremos como agregar nodos.

# Clase 6

# Crear y Agregar Nodos

Ahora vamos a meternos mas en profundidad y vamos a ver dos metodos o mas bien una coleccion de metodos para crear y agregar Nodos y vamos a empezar con el mas simple, los Nodos que podemos crear seran de dos tipos, podemos crear un Elemento, o podemos crear un Texto y respectivamente podemos utlizar (createElement) para un elemento o (createTextContent) para un texto.

# createElement

Si queremos ver mas a detalle esta API, la debemos de utlizar de esta manera.

```js

document.createElement(
  "ELEMENTO"
  )


```

Le diremos a al document.createElement que queremos crear un elemento y entre comillas le decimos que (etiqueta) queremos crear, podriamos crear un "div" o podemos crear un "h1", a qui podemos crear cualquier etiqueta y el navegador y JS o mas bien la API nos va a devolver el elemento creado.

OJO: El hecho que creemos un elemento no quiere decir que se agrgue al DOM, esta creacion sucede en memoria y cuando la creamos la asignamos a una variable, pero en ningun momento lo hemos agregado.

# createTextNode

A si mismo podemos crear texto utlizando (createTextContent) de esta manera 

```js 

document.createTextNode(
  "TEXTO"
  )


```

Si pasamos html dentro de este texto sera ejecutado como un texto, esto sera solo texto y no tendra ningun otro significado, el hecho que se cree no significa que se agregue, en tonces la practica de crear NODOS  no la veremos asta que aprendamos a agrgarlos y es aqui donde se vuelve muy divertido, especialmente por que para agrgar Nodos lo pódemos hacer de muchas formas, y depende de las necesidades en especifico.

Estas seran algunas de los metodos que podemos utilizar.

```js

parentElement.appendChild
parentElement.append
parentElement.insertBefore
parentElement.insertAdjacentElement

```

Ahora vamos a practicar directamente en el navegador, abrimos la consola y comenzaremos con el metodo (appendChild) este biene pegado del (document.appendChild) en tonces vamos a trabajar con la misma pagina de bootstrap, y vamos a trabajar con el nodo que crea la primera parte desdel titulo asta el parrafo, en tonces vamos a leer este nodo.

vamos a guardar en una constatnte y a este le vamos a llamar container, por llamarlo de alguna manera, y este sera igual a un (querySelector) de un (div) que tiene las siguientes clases, y son las clases exactas del elemento que queremos leer ene este caso sera esta classe (py-5 text-center) y esta sera su sintaxis.

```js

const container = document.querySelector('div.py-5.text-center');
     
undefined

container

<div class="py-5.text-center">...</div>


```

Y este seria el elemento que nos devuelve esta const, ahora necesitamos dos cosas,
necesitamos un Nodo de referencia y necesito el Nodo que necesitamos agrgar, asi que despues de esto vamos a crear otro Nodo, crearemos un (h3) y le vamos a decir al document que  me cree un elemnto, no un atributo, un elenmto (h3).

Una ves creado este le vamos a decir al padre o al contenedor (container) que quiero agrgar un hijo (appendChild) y este hijo sera un (h3) 

```js

const h3 = document.createElement('h3');

undefined

container.appendChild(h3);

<h3>​</h3>​


```

Si nosotros vemos la patalla a la izquierda, veremos que el h3 del navegador no se a modificado, pero si vemos en la consola notaremos que se a creado un nuevo h3. 
Si quicieramos ser un poco mas creativos, podriamos decirle que quremos crear otro text, vamos a crear otra variable por ejemplo llamada (texto) y le vamos a decir al document que nos cree un (textNode) que va a tener la descripcion de ("Hola amigos") y este texto se lo vamos a meter al h3 que creamos anteriormente, como este h3 lo tenemos en una variable, y le vamos a decir a ese h3 que nos hagregue un hijo (appendChild) que es un (texto) de esta manera 

```js

const texto = document.createTextNode('Hola Amigos');

undefined

h3.appendChild(texto);

"Hola Amigos"



```

De esta manera vemos como este hijo a sido agrgado y lo podremos ver inpreso en pantalla, este seria el codigo completo.

```js

const container = document.querySelector('div.py-5.text-center');
     
undefined

container

<div class="py-5.text-center">...</div>


const h3 = document.createElement('h3');

undefined

container.appendChild(h3);

<h3>​</h3>

const texto = document.createTextNode('Hola Amigos');

undefined

h3.appendChild(texto);

"Hola Amigos"



```

# Insertar una imagen con appendChild

Para insertar una imagen en una página web utilizando JavaScript, puedes utilizar el método createElement del objeto document. Este método te permite crear un nuevo elemento de imagen y, a continuación, puedes establecer su atributo src para especificar la ubicación de la imagen y agregarlo a la página utilizando el método appendChild del elemento padre donde deseas insertar la imagen.

Aquí tienes un ejemplo de cómo insertar una imagen en una página web utilizando JavaScript:


```js

Copy code// Crea un nuevo elemento de imagen 
var img = document.createElement('img'); 
 
// Establece la ubicación de la imagen 
img.src = 'ruta/a/mi/imagen.jpg'; 
 
// Agrega la imagen al documento 
document.body.appendChild(img); 

```

También puedes utilizar el atributo innerHTML de un elemento existente para insertar la imagen en la página. Por ejemplo:

```js

Copy code// Selecciona el elemento donde deseas insertar la imagen 
var container = document.getElementById('mi-container'); 
 
// Inserta la imagen en el elemento 
container.innerHTML = '<img src="ruta/a/mi/imagen.jpg">'; 

```

Otro ejemplo:

```js

const container = document.querySelector('div.pricing-header.p-3.pb-md-4.mx-auto.text-center');
undefined
container
<div class=​"pricing-header p-3 pb-md-4 mx-auto text-center">​…​</div>​
const img = document.createElement('img');
undefined
img
<img>​
img.src = 'https://media.gettyimages.com/id/200430632-001/es/foto/basketball-on-basketball-court-elevated-view.jpg?s=612x612&w=0&k=20&c=afjUqLwOMLew9airDmiGRei4t0AePYtzg4hjq70HZLQ=';
'https://media.gettyimages.com/id/200430632-001/es/foto/basketball-on-basketball-court-elevated-view.jpg?s=612x612&w=0&k=20&c=afjUqLwOMLew9airDmiGRei4t0AePYtzg4hjq70HZLQ='
document.body.appendChild(img);
<img src=​"https:​/​/​media.gettyimages.com/​id/​200430632-001/​es/​foto/​basketball-on-basketball-court-elevated-view.jpg?s=612x612&w=0&k=20&c=afjUqLwOMLew9airDmiGRei4t0AePYtzg4hjq70HZLQ=">​
container.innerHTML = '<img src="https://media.gettyimages.com/id/200430632-001/es/foto/basketball-on-basketball-court-elevated-view.jpg?s=612x612&w=0&k=20&c=afjUqLwOMLew9airDmiGRei4t0AePYtzg4hjq70HZLQ=">';
'<img src="https://media.gettyimages.com/id/200430632-001/es/foto/basketball-on-basketball-court-elevated-view.jpg?s=612x612&w=0&k=20&c=afjUqLwOMLew9airDmiGRei4t0AePYtzg4hjq70HZLQ=">'

```

El (appendChild) siempre nos va a agregar un Nodo al final, este (appendChild) es un API que existe hace mucho tiempo y tiene muchas limiotaciones, sinembargo existe una nueva API o un nuevo metodo y este se llama (append) y este es la evolucion de (appendChild) y las cventajas son.

# Podemos agrgar mas de un Nodo
# Le podemos agrgar un texto 
# Y no funciona de manera adecuada en internet xplorer

Podemos conocer mas de esta API, si seguimos este link.

https://developer.mozilla.org/es/docs/Web/API/ParentNode/append

https://developer.mozilla.org/en-US/docs/Web/API/Element/append



Juguemos un poco con (append) siguiendo con el mismo ejemplo, podriamos utlizar el (container), y le vamos a decir al (append) que queremos agregar un otro texto, pero que ademas quermos crear un elemento (createElement) y que quiero crear un (div) asi que que al dar enter deberia de terminar al final con un (texto) y consiguiente se crea un (div), la sintxis correcto seria de esta manera.


```js 

container.append('Una de los mejores recursos', document.createElement('div')):

```
De esta manera podemos agregar mas de un elemento en el html., esta sera la sintaxis completa.

```js

const container = document.querySelector('div.py-5.text-center');
     
undefined

container

<div class="py-5.text-center">...</div>

container.append('Una de los mejores recursos', document.createElement('div')):

```

Otro ejemplo:

```js

var imagen = new Image(); 
imagen.onload = imagenCargada; 
imagen.src = "ejemplo.png" 



<!doctype html> 
<html> 
 <head> 
 <title>Cargar imagen</title> 
 <meta charset="utf-8" /> 
 <script type="text/javascript"> 
 document.addEventListener("DOMContentLoaded", inicio, false); 
 function inicio() 
 { 
 var nuevaImagen = new Image(); 
 alert("Se procede a la carga en memoria de la imagen"); 
 nuevaImagen = cargarImagen("ejemplo.png"); 
 } 
 function cargarImagen(url) 
 { 
 var imagen = new Image(); 
 imagen.onload = imagenCargada; 
 imagen.src = url; 
 return imagen; 
 } 
 function imagenCargada() 
 { 
 alert("La imagen se ha cargado correctamente"); 
 } 
 </script> 
 </head> 
 <body> 
 </body> 

```

¿Cómo muestro una imagen dentro de un If en Javascript?
Un pequeño ejemplo para mostrar imagen

Otro ejemplo:

```js
var peso, altura, prom,imc,eleva;
var image1=document.getElementById("#image1");
peso=parseFloat(prompt("Ingresa tu peso en Kg: "));
altura=parseFloat(prompt("Ingresa tu altura : "));
eleva=Math.pow(altura,2);
imc=parseFloat((peso/eleva));

imc=imc.toFixed(2);
alert("Tu IMC Es: "+imc);

if(imc<=16){
document.write("Critero de Hospital");
image.innerHTML=document.write('<IMG class="image1"
SRC="img/pesonormal.png">');
}
else if(imc>16 && imc<17){
document.write("Infrapeso");

}
else if(imc>=17 && imc<18){
document.write("Bajo Peso");

}
else if(imc>=18 && imc<25){
document.write("Peso Normal");

}

```

Y un ejemplo para cambiar imágenes:

(fuente Como hacer que cambien imagenes con un condicional IF en javascript (https://es.stackoverflow.com/questions/196094/como-hacer-que-cambien-imagenes-con-un-condicional-if-en-javascript) )

```js

<html> 
    <head> 
        <title> DateFast </title> 
        <script type="text/javascript" src="BrandonWelding_67824.js"></script> 
    </head> 
    <body> 
         <center> 
             <img src= "corazon.jpg"> 
             <h1> DateFast </h1> 
         </center> 
         <table style="width: 100%;"    > 
             <tr> 
                 <th style="    width: 20%;">Datos</th> 
                 <th style="    width: 40%;">Resultados</th> 
             </tr> 
             <tr> 
                <h2>Introducir su edad:</h2> 
                <input type="number" value="18" min="18" max="40" id="edad"> 
                <br> </br> 
                <h2>Intruducir sexo:</h2> 
                <input type="radio" name="gender" value="Hombre" id="hombre">Hombre 
                <input type="radio" name="gender" value="Mujer" id="mujer">Mujer 
                <br> </br> 
                <button style="margin-top: 20px, padding:10px 0px 10px 0px;" id="boton" value="uno" onclick="calcular()">Conseguir Pareja...</button> 
                <table style="height: 100%; ">   
                    <th style="height:  300px;" >    
                        <img style="width:  100%; height: 100%;" src="Base.png" id="imgbase1"> 
                    </th> 
                    <th style="height: 300px;">  
                        <img style="width:  100%; height: 100%;" src="Base.png" id="imgbase2"> 
                    </th> 
                    <th style="height:  300px;">     
                        <img style="width:  100%; height: 100%;" src="Base.png" id="imgbase3"> 
                    </th> 
                </table>         
            </tr> 
        </table> 
    </body> 
</html> 




function calcular(){ 
 
    var edad=document.getElementById("edad").value; 
    var gender=document.getElementById("hombre").checked; 
    var imagenacambiar1=document.getElementById("imgbase1"); 
    var imagenacambiar2=document.getElementById("imgbase2"); 
    var imagenacambiar3=document.getElementById("imgbase3"); 
 
    if (gender===("hombre"||"mujer")) 
    { 
        imagenacambiar1.src="jlaw.jpg" 
        imagenacambiar2.src="estone.jpg" 
        imagenacambiar3.src="girl3.jpg" 
    } 
    else 
    { 
        imagenacambiar1.src="h1.jpg" 
        imagenacambiar2.src="h2.jpg" 
        imagenacambiar3.src="h3.jpg"         
    } 
} 

```

# Este es un ejemplo con (append)

```js


const contenedor = document.querySelector('div.col-md-5.col-lg-4.order-md-last');

undefined

contenedor

<div class=​"col-md-5 col-lg-4 order-md-last">​…​</div>​<h4 class=​"d-flex justify-content-between align-items-center mb-3">​…​</h4>​flex<ul class=​"list-group mb-3">​…​</ul>​flex<form class=​"card p-2">​…​</form>​flex

"Tus cartas"

<main>​</main>​</div>​

contenedor.append('Los mejores recursos', document.createElement('main'));

undefined

```


Si tienes que soportar Internet xplorer tenemos dos obciones.
Una utlizamos (appendChild), o dos creamos un polifil para que soporte (append), y este polifil lo vamos a encontar en MDN, esta nos provee de una funcion que hace lo mismo que (append) y funciona en cualquier tipo de navegador, 


------------------------------------------------------------------------------

Vamos a ver otro metodo que nos permite agregar elementos antes de la referencia, a diferencia de (appendChild y append) que nos agregaba al final de la referencia, esta se llama (inserBefore) para insertarlo antes del Nodo de referencia.

# InsertBefore

A este le tenemos que pasar dos cosas, primero debemos de decirle cual es el Nodo que queremos agregar, y segundo cual es la referencia en la que nos estamos basando a la hora de agregar.

En tonces vamos a escoger algun elemento padre donde queramos insertar en este caso este.

const contenedor = document.querySelector('div.col-md-5.col-lg-4.order-md-last');

A qui vamos acrear un elemento nuevo y le vamos a llamar titulo, para esto lo vamos hacer creando un elemento nuevo con un "h1" de esta manera.

const titulo = document.createElement('h1');

y lo que queremos es crear este elemento entre la imagen y el "h2" que lla tenemos.
En tonces vamos a tomar el "h2" como referencia y lo guardaremos de esta manera.

const referencia = document.querySelector('h2');

Lo debemos inprimir trallendo el nombre con el que lo hemos guardado en este caso el nombre es (referencia)


referncia

Al darle enter me devuelve el elemento de referencia, en este caso.

<h2>Checkout form</h2>

siendo asi podemos decir que al (container) quiero insertar utilizando el (insertBifore)  el Nodo que se llama (titulo)
apartir de esta referencia a la que hemos llamado (referencia), al darle enter nos devuelve un (h1) que es el que hemos creado he insertado,
entre la imagen y el (h2).

La clave para todos los metodos que contienen (insert) es la referencia, la referencia va despues del Nodo dode queremos agrgar, 
para verlo de forma grafica si insertamos un (h1) antes del (p) en el elemento (div) nos quedaria con este resultado

div------------h1
                     DIV.insertBefore(h1, p,)
   ------------p
   

Tengamos en cuenta que en el (inserBifore) el Nodo de referencia tiene que ser un hijo directo del padre, 
es decir que si el Nodo de referncia se encuentra en un nivel o mucho mas niveles adentro del arbol, no va a funcionar.

EJEMPLOS 1:

```js

<div id="parentElement">
  <span id="childElement">foo bar</span>
</div>

<script>
  // Crear el nodo a insertar
  var newNode = document.createElement("span");

  // Obtener una referencia al nodo padre
  var parentDiv = document.getElementById("childElement").parentNode;

  // Comienzo del test [ 1 ] : Existe un childElement --> Todo funciona correctamente
  var sp2 = document.getElementById("childElement");
  parentDiv.insertBefore(newNode, sp2);
  // Fin del test [ 1 ]

  // Comienzo del test [ 2 ] : childElement no es del tipo undefined
  var sp2 = undefined; // No existe un nodo con id "childElement"
  parentDiv.insertBefore(newNode, sp2); // Implicit dynamic cast to type Node
  // Fin del test [ 2 ]

  // Comienzo del test [ 3 ] : childElement es de Tipo "undefined" ( string )
  var sp2 = "undefined"; // No existe un nodo con id "childElement"
  parentDiv.insertBefore(newNode, sp2); // Genera "Type Error: Invalid Argument"
  // Fin del test [ 3 ]
</script>

```

EJEMPLOS 2:

```js

<div id="parentElement">
  <span id="childElement">foo bar</span>
</div>

<script>
  // Crea un nuevo, elemento <span>
  var sp1 = document.createElement("span");

  // Obtener una referencia al elemento, antes de donde queremos insertar el elemento
  var sp2 = document.getElementById("childElement");
  // Obtener una referencia al nodo padre
  var parentDiv = sp2.parentNode;

  // Inserta un nuevo elemento en el DOM antes de sp2
  parentDiv.insertBefore(sp1, sp2);
</script>

```

No existe el método insertAfter(). Puede ser emulado mediante la combinación del método con Node.nextSibling().

En el ejemplo anterior, sp1 podría insertarse después de sp2 usando:

```js

parentDiv.insertBefore(sp1, sp2.nextSibling);


```

Si sp2 no tiene ningún hermano depués de él, entonces debe ser el último hijo — sp2.nextSibling devuelve null, y sp1 se inserta al final de la lista de nodos hijos (inmediatamente después de sp2).

Ejemplo 3
Inserta un elemento antes del primer elemento hijo, utilizando la propiedad firstChild (en-US).

JS

```js

// Obtener una referencia al elemento en el que se quiere insertar un nuevo nodo
var parentElement = document.getElementById("parentElement");
// Obtener una referencia al primer hijo
var theFirstChild = parentElement.firstChild;

// Crear un nuevo elemento
var newElement = document.createElement("div");

// Insertar el nuevo elemento antes que el primer hijo
parentElement.insertBefore(newElement, theFirstChild);


```

Cuando el elemento no tiene ub primer hijo, entonces firstChild es null. 
Aun así, el elemento se añade al padre después del último hijo. Puesto que el 
elemento padre no tenía primer hijo, tampoco tiene último hijo. Por tanto, 
el nuevo elemento es el único elemento después de ser insertado.


-------------------------------------------------------------------------------------------------

# ref.insertAdjacentBifore

Este es quizas uno de los metodos mas dificiles para agregar Nodos en html o un Nodo en el DOM, pero es uno de los mejores y poderosos metodos que tenemos 
para agregar Nodos, vamos a verlo en nuestros navegadores.

Para trabajar con (insertAdjacentBifore), la clave al igual que con los demas (insert)
es que vamos a definir nuestra referencia, asi que vamos a crear una variable (const) la cual
le vamos a llamar (referencia) y la vamos a hacer igual (=) por ejemplo tomemmos el (h2) que tenemos
<h2>Checkout form</h2> asi que diremos (document.querySelector) y entre parentesis y
despues del (document.querySelector) pondremos la referencia en este caso sera ('h2') si le 
damos enter, veremos como nos devuelve la refencia.

Tambien vamos a crear otro Nodo, (const) le vamos a poner nombre en este caso (nodo) y esto
sera igual a un (document.createElement) y este sera igual a un ('span') para cambiar un poco, en tonces si le damos enter 
en tonces nodo sera igual a un (span), y la referencia sera un  <h2>​Checkout form​</h2>

Entonces cuando podemos utlizar (insertAdjacentBifore)?

Podremos utilizar (insertAdjacentBifore) apartir de la referncia, es decir que apartir de aqui 
<span>​</span> vamos a llamar la referencia (referencia) y le vamos a insertar (insertAdjacentElement
) con estas opciones ('') y le vamos agregar este (nodo) osea de esta manera ('', nodo);

referencia.insertAdjacentElement('', nodo);

y las opciones que podemos pasarle que son cuatro, estaran dentro de las comillas simples.

# La primera sera (biforebegin)
Si utlizo esta nos va a insertar el nodo anter de la referencia osea asi.

<span>​</span>
<h2>​Checkout form​</h2>

# La segunda sera (afterbegin)
Con este el Nodo creado se pondra justo debajo o despues de la referencia asi.

<h2>
<span>​</span>
​Checkout form
​</h2>

# La tercera sera (beforeend).
Con esta al ejecutarla, nos va a poner el Nodo, justo antes donde finaliza el Nodo de 
referncia, osea justo antes de la etiqueta terminada del (h2) osea asi.


<h2>
​Checkout form
<span>​</span>
​</h2>

# La cuarta sera (afterend).
Este conciste en insertar el nodo creado justo despues de la etiqueta de finalizacion de referencia
asi.


<h2>
​Checkout form
​</h2>
<span>​</span>



```js

const referencia = document.querySelector('h2');

undefined

referencia

<h2>​Checkout form​</h2>

const nodo = document.createElement('span');

undefined

nodo

<span>​</span>

referencia.insertAdjacentElement('beforebegin', nodo);

<span>​</span>​

referencia.insertAdjacentElement('afterbegin', nodo);

<span>​</span>

referencia.insertAdjacentElement('beforeend', nodo);

<span>​</span>

referencia.insertAdjacentElement('afterend', nodo);

<span>​</span>​​​​​

```

El (insertAdjacentElement) es le metodo que mas control nos da cuando queremos agregar un elemento al DOM,
Esta es una API que debemos consultar antes de utlizarla, asi que no nos preocupemos al utilizarla
solo debemos de saber que tenemos un control granular de un elemento y que lo podemos hacer con 
(insertAdjacentElement) y que podemos insertar un lemento antes del Nodo, despues de que enpiza, antes de que termine, 
y despues de que termine ese elemento. 




# Clase numero 7

# OTRAS FORMAS DE AGREGAR


Existen otras formas de leer y agregar nodos que son mucho mas convenientes utlizando  (String o cadenas de texto) esto consta de (node.outerHTML (leer)) esto para leer HTML, Y Tambien de (node.innerHTML (escribir)) este para escribir HTML.

Estas formas son muy faciles de usar, pero debemos de tener en cuenta algo sobre seguridad, vamos a verlo en pantalla y veremos que es lo que sucede.

Para esto vamos a utlizar un nodo de referencia, vamos a seleccionar un nodo en este caso vamos a elegir un <h2>

Recordemos que para seleccionar un nodo debemos de utlizar.

```js

document.querySelecto

```

Pero en este caso vamos a descubrir un tips interesante de como lo podemos hacer, como estamos directamente en el navegador, lo que podemos hacer es seleccionar un elemento, ponemos el cursor sobre es elemento lo marcamos, y luego nos vamos a la consola y ponemos 

```js

$0
  <h2>Checkout form</h2>

```

Y esto nos traera automaticamente el elemento que queremos, en este caso marcamos el <h2> y ponemos simbolo de peso y cero $0.

Ahora vamos con el primer metodo que se llama (outerHTML)

```js

$0
  <h2>Checkout form</h2>

$0.outerHTML
   <h2>Checkout form</h2>
  
```

Este metodo nos devuelve una cadena de texto (<h2>Checkout form</h2>) el HTML de ese elemento, 

Asi mismo existe (innerHTML) donde le podemos decir al <h2> seleccionado con ($0), si lo ejecuto, me dice cual es el valor actual que consiste de este texto (Checkout form) de esta manera.

```js

$0
  <h2>Checkout form</h2>

$0.innerHTML
   "Checkout form"
  
```

Pero que tambien lo puedo asignar a otras cosas, por ejemplo le podemos decir.

```js

$0
  <h2>Checkout form</h2>

$0.innerHTML
   "Checkout form"

$0.innerHTML = "Algo nuevo"   
  
```

De esta manera nos va a remplazar el texto que teniamos en este caso era (Check form) y lo remplaza por el texto que nosotros hemos escrito, en este caso (Algo nuevo).
Si por ejemplo nosotros seleccionamos un elemento <div> y luego pasamos a la consola y llamamos el ( $0 ), veremos como nos imprime todo el elemento (div), 
y si le decimos ($0.innerHTML) esto nos va a traer todo el HTML que tenemos dentro de ese contenedor (div).


```js

$0
  body > div.container > main > div.py-5.text-center

  $0.outerHTML
     <div class="py-5 text-center">
      <img class="d-block mx-auto mb-4" src="/docs/5.3/assets/brand/bootstrap-logo.svg" alt="" width="72" height="57">
      <h2>Algo como esto</h2>
      <p class="lead">Below is an example form built entirely with Bootstrap’s form controls. Each required form group has a validation state that can be triggered by attempting to submit the form without completing it.</p>
     </div>    
  
```

Nos a traido todo el HTML que teneiamos en ese div.

ESto es muy conveniente por que en tonces yo podria hacer cosas como por ejemplo reemplazar lo que ya 
escribimos (Algo nuevo) por (Algo viejo) como esto es un texto, esto lo podemos hacer creando una constante, 
dandole un nombre y esto seria igual
a ($0.outerHTML.replace('Algo nuevo', 'Algo viejo')) osea con esto le estamos diciendo que queremos reemplazar
(Algo nuevo) por (Algo viejo), veamoslo en consola.


```js

const nuevoHTML = $0.outerHTML.replace('Algo nuevo', 'Algo viejo')

```

De esta manera podemos reemplazar u texto por otro texto, de una manera muy censilla, si damos enter, y le decimos 

```js

nuevoHTML 

```

Esto deberia guardarme un HTML y posteriormente ya que nos lo a guardado, ahora lo que queremos es que nos lo cambien, por que hasta el momneto lo unico que ha hecho es guaradarlo, en tonces le vamos a decir, quiero que ahora el HTML (innerHTML) sea igual a la nueva cadena que acabamos de crear osea (nuevoHTML) 

```js

$0.innerHTML = nuevoHTML

```

El navegador no me va a preguntar nada, y simplemente lo que sea que yo le pase en esta nueva variable me lo va a  reemplazar, osea que me va a reemplazar el texto nuevo por el viejo, 



```js

$0
<h2>​Checkout form​</h2>​
$0.innerHTML
'Checkout form'
$0.innerHTML = "Algo nuevo"
'Algo nuevo'
const nuevoHTML = $0.outerHTML.replace('Algo nuevo', 'ALgo viejo')
undefined
nuevoHTML
'<h2>ALgo viejo</h2>'
$0innerHTML = nuevoHTML
'<h2>ALgo viejo</h2>'
$0.innerHTML = nuevoHTML
'<h2>ALgo viejo</h2>'

```


Como lo hemos visto a cambiado el texto y este se ve reflejado en el navegador, aun que esto paresca muy conmveniente, tiene algunos problemas de seguridad, esto es peligroso en el caso de que, esto permite inyecciones de XSS, es decir que yo puedo utlizar estos metodos para inyectar codigo maligno, esto no quiere decir que no debemos utilizar innerHTML, de hecho debemos de utilizarlo pero hay que ser muy cuidadosos cuando lo usemos, lo unico es que debemos evitar usarlo cuando la cadena de texto, lo que vamos a rrenderizar uzando innerHTML proviene del usuario, si esto de alguna forma fue escrito por el usuario, nunca pero nunca debemos de confiar en eso, y siempre hay que pasarlo por un presoso de sanytais,  que se encarga de tomar el HTML como texto y darle una limpieza para esegurarse de que este texto no contiene nada malicioso y por consiguiente rrenderizarlo con innerHTML
, aun que esto nos parezca muy conveniente, tiene algunos problemas de seguridad
y es que podremos insertar codigo malicioso o mas conocido como
inyecciones XSS, Osea que podre utlizarlo como ya lo dijimos
para inyectar codigo maligno.

Nos vemos en la siguiente clase.




# Clase numero 8


# Atributos y propiedades















```js



```



