---
title: "Js notes"
date: 2022-04-12
description: 'Aprendizaje de JavaScript'
---

# ELEMENTOS BÁSICOS DE JS

- Bindings (let y const)

Dentro del mundo de la computadora, solo existen datos. Los datos son fundamentalmente parecidos pues se almacenan como grandes secuencias de bits.

Los bits pueden tener dos valores (cero y uno) y dentro de las computadoras los bits toman formas de cargas eléctricas altas o bajas, señales fuerters o débiles, etc. Cualquier pedazo de infromación discreta puede ser reducida a una secuencia de unos y ceros y, de esa manera ser representada en bits.

## valores

Las porciones de bits pueden ser clasificadas y en JavaScript esas porciones son conocidas como valores. Aunque todos los valores estan hechos de bits, estos juegan papeles diferentes. Cada valor tiene un rol. Algunos son números, otros pedazos de texto, otros son funciones, etc.

### números

```
9
```

valores tipo *number* son numéricos. JavaScript usa 64 bits para almacenar valores numéricos y solo existe una cantidad finita de patrones que podemos crear con 64 bits 2 ^ 64 = 18 trillones aproximadamente. sin embargo, los bits tambien indican números negativos por lo que el número entero (También llamados *integers*) más grande que puede ser almacenado esta en el rango de los nueve mil billones (inmenso!).

#### fraccionarios

```
9.33
```

para números muy grandes o muy pequeños podemos usar la notación cientifica agregando *e*, seguida por el exponente del número


```
9.33e8
```

Esto seria: 9.33 x 10 ^ 8 = 933000000

### Strings

Son usados para representar texto. Son escritos encerrando su contenido entre comillas **simples, dobles o invertidas*:

```
"Debajo del mar"
'Descansa el oceano'
`Flota el oceano`
```
Cuando hay un simbolo que precede a una diagonal invertida significa que el caracter que le sigue tiene un significado especial. Esto se conoce como *Escapar* del caracter. Por ejemplo:
"\n" significa un salto de linea (Newline)
"\t" es un caracter de tabulación
Si resulta que queremos escribir una linea invertida dentro de un String es posible agregando una doble linea invertida, esto ocasionara un colapso de ellas y podras imprimir una linea invertida como caracter:


> Un carácter de salto de linea es escrito así: "\\n"






- Imprimir valores (console.log)

# Sentencia Return

Con esta sentencia podemos devolver datos de una función, supongamos que tenemos la siguiente Función:

~~~
function calcularImc(peso,altura){
        imc = peso/(altura*altura);
        document.write(imc);
    }
~~~

Bueno podemos ahorrarnos ese "document.write" y [RETORNAR](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/return) solo el resultado de nuestra operación.

~~~
function calcularImc(peso,altura){
        return (peso/(altura*altura));
    }
~~~

## 🌎 Arrays

Los arreglos en JavaScript son un **tipo de datos** para almacenar __secuencias__ de números y está escrito como una lista de valores entre corchetes, separados por comas.

```javascript
let listaDeNumeros = [3,21,33,44,11];
console.log(listaDeNumeros[3]);
// -> 44
```
- Para poder obtener un __elemento__ del arreglo se usan corchetes.
- El primer indice de un arreglo siempre sera 0.

## 🪐 Propiedades

En JavaScript podemos acceder a las propiedades de valores y objetos por ejemplo:

> ```miString.length```
> En este primer caso accedemos a la propíedad *length* del valor *miString*
> ```Math.max```
> y en este caso accedemos a la propiedad *max* del objeto *Math*

En JavaScript hay dos formas principales para acceder a las propiedades con punto y con corchete:

valor.x o bien valor[x]

## 🍧 Módulos 

Los módulos vienen a solucionar el problema de los programas *Big Ball of Mud*, es decir, aquellos que son muy grandes y sin estructura bien defnida.

> Un módulo  es una pieza del programa que especifica en qué otras piezas este depende (su *dependencias*) y qué funcionalidad proporciona para que otros módulos usen su *interfaz*

***Las *relaciones* entre los modulos se llaman *dependencias* *** 

> Cuando un módulo necesita una pieza de otro módulo se dice que depende de ese módulo.

Cuando se trabaja con diferentes archivos estos comparten el mismo espacio de nombres globales y puedenm intencionalmente o accidentalmente interfer con las vinculaciones de cada uno.

Una recomendación: si aún te encuentrass explorando el problema no es necesario perder el tiempo preocupandote por los módulos sino que una vez qeu tengas algo más sólido, es buen momento para dar un paso atrás y organizarlo.

### interfaces

Es la parte del módulo que es visible desde otros módulos.

### dependencias

Son los otros módulos que este utiliza.

### NPM

es un repositorio de paquetes de JAvaScript.

## 📣 Módulos CommonJS

Este enfoque es el más utilizado y el concepto principal es una *Función* llamada *require* ("*requerir*"). Cuando la llmas con el nombre del módulo de una dependencia, esta se asegura de que elk módulo sea cargado y retorna su interfaz.

> Para evitar cargar el mismo módulo varias veces, *require* mantiene un (caché) almacenado de módulosñ que ya han sido cargados

Cuando se llama, primero verifica si el módulo solicitado  ya ha sido cargado y, si no, lo carga. Esto implica leer el código del módulo, envolverlo en una función y llamarlo.


## 🌗 Modificando Clases

### Ejemplo prático

Es posible modificar una clase con otro script de la siguiente manera: 

1. Creamos una clase que al ser llamada por otro módulo instancie un objeto, ademas de un método para imprimir en consola un mensaje pasado como parametro:

```javascript
class Logger {
  constructor (name) {
    this.count = 0
    this.name = name
  }

  log (message) {
    this.count++
    console.log('[' + this.name + '] ' + message)
  }
}

module.exports = new Logger('DEFAULT') // Nuevo objeto instanciado
module.exports.Logger = Logger // Clase
```

2. Creamos una función extra que modificara al objeto instanciado

```javascript
        /* require('./logger') nos dara el objeto y require('./logger').Logger nos dara la clase */
        
 require('./logger').customMessage = function () {
         console.log('This is a new functionality')
}

```

3. En tu archivo main.js deberas llamar primero al modulo que crea una nueva funcionalidad para despues llamar al modulo que instancia el objeto.

```javascript
 
 require('./patcher')
 const Logger = require('./logger')
 logger.customMessage()
        
```
## ⚾ Módulos ECMAScript

Este sistema de módulos fue introducido en 2015 y es llamado *Módulos ES*. Su diferencia con otro tipo de módulos es que en lugar de llama a una función para acceder a una dependencia, utilizas la palabra clave **import**.

La interfazz de un módulo ES no es un valor único, sino un conjunto de vinculaciones con nombres. Cuando importas desde otro módulo, importas la *vinculación*, no el valor, lo que significa que un módulo exportado puede cambiar el valor de la vinculación en cualquier momento, y que los módulos que la importen varán su nuevo valor.

Cuando hay una vinculación llamada default. esta se trata como el principal valor del módulo exportado.

Es posible renombrar la vinculación importada usando la palabra as ("como").

```javascript

 import {days as nombreDias} from "date-names";
 consolo.log(nombreDias.length)
```
# References

[Eloquent JavaScript](https://eloquentjavascript.net/)
[Markdown](http://ares.inf.um.es/00Rteam/documentos/usandoMarkdown.pdf)


