---
title: "Js notes"
date: 2022-04-12
description: 'Aprendizaje de JavaScript'
---


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

## :sunrise: Arrays

Los arreglos en JavaScript son un **tipo de datos** para almacenar __secuencias__ de números y está escrito como una lista de valores entre corchetes, separados por comas.

```javascript
let listaDeNumeros = [3,21,33,44,11];
console.log(listaDeNumeros[3]);
// -> 44
```
- Para poder obtener un __elemento__ del arreglo se usan corchetes.
- El primer indice de un arreglo siempre sera 0.

## :sunrise_over_mountains: Propiedades

En JavaScript podemos acceder a las propiedades de valores y objetos, es decir, 






