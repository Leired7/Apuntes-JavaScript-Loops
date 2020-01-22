# Loops

Un ```loop``` (en español "bucle") se utiliza en programación para repetir un número determinado de líneas de código dos o más veces. Existen varios tipos de loops. Veamos los más comunes:

## ```for loop```

El 'bucle for', o más correctamente dicho el ```for loop```, se utiliza para repetir una o más instrucciones un determinado número de veces mientras se cumpla una condición determinada. Nosotros elegimos tanto el número de veces que el loop tiene que repetirse como la condición que se tiene que dar para que ese loop se ejecute.

La sintaxis de un ```for loop```, en términos generales y escrita en pseudocódigo, es la siguiente:

```javascript
for (<variable>; <condición>; <modificación>) {
  <código que queremos que se ejecute>
}
```
```<variable>``` - Aquí pondremos código que queremos que se ejecute antes de que el loop inicie. Casi siempre se define una variable aquí.

```<condición>``` - En este espacio pondremos la condición que determinará si el código dentro del loop se va a ejecutar o no. Si esta condición es ```true```, el ```<código que queremos que se ejecute>``` será, en efecto, ejecutado. Pero, si esta condición es ```false```, el código no se ejecutará y el loop se dará por cerrado. 
Veamos un ejemplo con código

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
Veamos paso a paso a paso lo que ha ocurrido en este loop:
- ```for(){}``` - Esta es la estructura general del ```for loop```. Con esto indicamos que estamos creando este tipo de loop.

- ```let i = 0``` - En el primer statement, hemos creado una variable ```let i = 0```. Esta será la variable con la que iteraremos. Por regla general, los programadores se han puesto de acuerdo para que esta variable se llame ```i```.

- ```i < 5``` - Esta es la condición que se tiene que cumplir para que el código dentro del loop se ejecute. Mientras ese statement sea ```true```, el código entre las llaves se va a ejecutar.

- ```i++``` - Este es el código que se va a ejecutar una vez termine de ejecutarse el código que está entre las llaves, es decir, ```console.log(i)```.

:warning: Recordemos que ```i++``` es lo mismo que ```i = i + 1```

- ```console.log(i)``` - Este es el código que se va a ejecutar siempre y cuando ```i < 5``` sea ```true```. Cuando termina de ejecutarse, se ejecuta ```i++``` y luego se verifica que se siga cumpliendo la condición de ```i < 5```. Si esta condición es ```true```, entonces se volverá a ejecutar ```console.log(i)```, seguido de ```i++``` y posteriormente la verificación de que ```i < 5``` sea ```true```. Y así sucesivamente hasta que esta última condición sea ```false```, lo que provocará que el código dentro de las llaves no se ejecute y que el loop finalice.

Veámoslo con otro ejemplo:

```javascript
let madridStudents = ["Escu", "Javi", "Caterina", "Angel", "Natalia", "Jara", "Leire", "María"];

for(let i = 0; i < madridStudents.length; i++){
  console.log(madridStudents[i]);
}

// Expected output:

// Escu
// Javi
// Caterina
// Angel
// Natalia
// Jara
// Leire
// María
```

En este caso, hemos utilizado el ```loop``` para imprimir en la consola los nombres de todos los items de ```madridStudents```. Pero hay otros loops que son más prácticos para realizar este tipo de iteración. Los veremos a continuación.

## ```for of loop```

Este tipo de loop nos facilita poder acceder a todos los elementos de un array de forma más rápida y concreta.

Al igual que antes, vamos a utilizarlo para imprimir los items de ```madridStudents```:

```javascript
for(let student of madridStudents){
  console.log(student);
}

// Expected output:

// Escu
// Javi
// Caterina
// Angel
// Natalia
// Jara
// Leire
// María
```

Como podemos ver, es una forma más fácil de conseguir el mismo resultado. En este caso, el loop se va a ejecutar automáticamente mientras recorre el ```array``` que le hemos indicado después de la palabra ```of```.

:warning: En este ejemplo he puesto ```student``` como nombre de la variable porque tiene sentido con el contexto del loop. En este tipo de loop no sería aconsejable llamarla ```i``` como lo hemos estado haciendo con los ```for loops```.

## ```for each loop```

Este loop permite ejecutar una callback function por cada elemento dentro del array. Esto nos puede facilitar la iteración entre elementos.

Veámoslo en un ejemplo iterando con ```madridStudents```:
```javascript
madridStudents.forEach((student)=>{
  console.log(student);
})

// Expected output:

// Escu
// Javi
// Caterina
// Angel
// Natalia
// Jara
// Leire
// María
```
En este caso la sintaxis es un poco diferente. ```forEach()``` es un método que se aplica directamente sobre el ```array```, por lo que hay que aplicarlo de esta forma: ``` <array>.forEach()``` como poder ver arriba. También, está ejecutando una ```arrow function``` con ```student``` como parámetro. 

## ```for in loop```

Este loop nos permite hacer iteración entre ```literal objects```. 

Veámoslo con un ejemplo:

```javascript
let personalInfo = {
  nombre: "Jaime",
  apellido: "Jacobo",
  edad: 25,
  vivo: true
};
```
```javascript
for(let key in personalInfo){
  console.log(key);
}

//Expected output

// nombre
// apellido
// edad
// vivo
```

Con este loop podemos iterar directamente entre las ```keys``` de un ```literal object``` determinado. Nuevamente, la variable ```key``` la he llamado de esta forma porque es coherente con el contexto, pero puedes poner el nombre que prefieras.

También podemos acceder a los values iterando sobre el ```literal object```:

```javascript
for(let i in personalInfo){
  console.log(personalInfo[i]);
}

//Expected output

// "Jaime"
// "Jacobo"
// 25
// true
```
## ```while loop```

Este loop nos permite ejecutar código infinitamente mientras se cumpla una condición determinada que nosotros le demos.

Veamos un ejemplo:

```javascript
let counter = 5;
while(counter > 0){
  console.log("Hello Wilders!");
  counter--;
}

//Expected output

//Hello Wilders!
//Hello Wilders!
//Hello Wilders!
//Hello Wilders!
//Hello Wilders!
```
Aquí podemos ver como el código que está entre las llaves se va a ejecutar siempre que se cumpla la condición que está entre paréntesis.

:warning: Hay que tener cuidado con este loop porque puedes entrar en un loop infinito y puede congelar tu ordenador. Siempre revisa dos veces si la condición va a ser ```false``` alguna vez, porque si siempre va a ser ```true```, el código nunca va a parar de ejecutarse.
## ```do while loop```

Este loop es igual que el ```while loop```, con la diferencia de que siempre va a correr un pedazo de código antes de revisar si se cumple la condición que le hemos puesto.

Veámoslo con un ejemplo:

```javascript
let countdown = 4;
do{
  console.log("Today is Friday!");
  countdown--;
} while (countdown > 0)

//Expected output

// Today is Friday!
// Today is Friday!
// Today is Friday!
// Today is Friday!
```
Como podemos ver, es prácticamente igual que el ```while loop``` pero con la sintaxis al revés. Este es el ```loop``` menos utilizado, pero alguna vez se puede dar el caso en el que sea de utilidad.
