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
