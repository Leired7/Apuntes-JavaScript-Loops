# Loops

Un ```loop``` (en español "bucle") se utiliza en programación para repetir un número determinado de líneas de código dos o más veces. Existen varios tipos de loops. Veamos los más comunes:

## ```for loops```

El 'bucle for', o más correctamente dicho el ```for loop```, se utiliza para repetir una o más instrucciones un determinado número de veces mientras se cumpla una condición determinada. Nosotros elegimos tanto el número de veces que el loop tiene que repetirse como la condición que se tiene que dar para que ese loop se ejecute.

La sintaxis de un ```for loop```, en términos generales y escrita en pseudocódigo, es la siguiente:

```javascript
for (<variable>; <condición>; <modificación>) {
  <código que queremos que se ejecute>
}
```
```<variable>``` - Aquí pondremos código que queremos que se ejecute antes de que el loop inicie. Casi siempre se define una variable aquí.

```<condición>``` - En este espacio pondremos la condición que determinará si el código dentro del loop se va a ejecutar o no. Si esta condición es ```true```, el ```<código que queremos que se ejecute>``` será, en efecto, ejecutado. Pero, si esta condición es ```false```, el código no se ejecutará y el loop se dará por cerrado. 
veamos un ejemplo con código

```<modificación>``` - En este hueco pondremos el código que queremos que se ejecute al finalizarse el código dentro del loop. Casi siempre va a ser un modificador de la variable que hayamos puesto en ```<variable>```

Veamos un ejemplo de un ```for loop``` con código:
```javascript
for(let i = 0; i < 5; i++){
  console.log(i);
}

// Expected output:
// 0
// 1
// 2
// 3
// 4
```
