## Clase: Introducción a JSON (para principiantes)

Objetivo: Entregar material claro y práctico para enseñar JSON a personas que no lo conocen. El contenido incluye teoría mínima, ejemplos paso a paso, ejercicios y soluciones.

Duración sugerida: 60-90 minutos.

Checklist de requisitos del usuario:

- Crear clases (material) sobre JSON lo más entendible posible — Hecho
- Incluir ejemplos y ejercicios para principiantes — Hecho
- Proveer soluciones para los ejercicios — Hecho

## 1. ¿Qué es JSON? (explicación en una frase)

JSON (JavaScript Object Notation) es un formato ligero para intercambiar datos que usa texto legible por humanos y una estructura basada en pares clave:valor y arreglos.

Por qué usarlo: es fácil de leer, ampliamente soportado en APIs y en casi todos los lenguajes de programación.

## 2. Estructura básica y tipos de datos

- Objeto: colección desordenada de pares clave:valor encerrada en llaves { }.
- Arreglo (array): lista ordenada de valores encerrada en corchetes [ ].
- Valor: puede ser número, cadena (string), booleano (true/false), null, objeto o arreglo.

Reglas importantes (principales errores comunes):

- Las claves (keys) deben ir entre comillas dobles: "nombre".
- Las cadenas (strings) usan comillas dobles: "hola" (no simples ' ').
- No se permiten comas finales después del último elemento.
- No se permiten comentarios dentro del JSON estándar.

Ejemplo simple (explicado):

```
{
	"nombre": "Ana",
	"edad": 28,
	"estudiante": false,
	"hobbies": ["leer", "correr"],
	"direccion": { "ciudad": "Lima", "pais": "Perú" }
}
```

Explicación breve:

- "nombre" es una clave con valor string.
- "edad" es un número.
- "hobbies" es un arreglo de cadenas.
- "direccion" es un objeto anidado.

## 3. Ejemplos paso a paso

a) Lista simple (JSON que representa una lista de números):

```
[1, 2, 3, 4]
```

b) Objeto con varios tipos:

```
{
	"producto": "Cuaderno",
	"precio": 12.5,
	"disponible": true,
	"tags": ["papeleria", "escuela"],
	"proveedor": null
}
```

c) Array de objetos (ejemplo típico en APIs):

```
[
	{ "id": 1, "nombre": "Luis" },
	{ "id": 2, "nombre": "María" }
]
```

## 4. Demo en vivo (guión corto)

1. Abrir un editor (VSCode o un editor online).
2. Escribir el objeto simple del ejemplo y validar con un validador (p. ej. jsonlint.org o la extensión de JSON de VSCode).
3. Modificar: cambiar un string por comillas simples para mostrar el error y cómo leer el mensaje del validador.
4. Mostrar cómo convertir JSON a un objeto en JavaScript (ejemplo corto):

```
const jsonText = '{"nombre":"Ana","edad":28}';
const obj = JSON.parse(jsonText);
console.log(obj.nombre); // Ana
```

Y cómo convertir un objeto a JSON:

```
const texto = JSON.stringify(obj);
console.log(texto); // '{"nombre":"Ana","edad":28}'
```

## 5. Ejercicios (para clase)

Ejercicio 1 (fácil): Crear un objeto JSON que represente a una persona con: nombre, edad y ciudad.

Ejercicio 2 (fácil): Crear un arreglo JSON con 3 frutas.

Ejercicio 3 (intermedio): Crear un objeto llamado "curso" con: titulo, duracion (horas), docentes (arreglo de nombres) y online (booleano).

Ejercicio 4 (intermedio): Dado el siguiente JSON, acceder en JavaScript al nombre del segundo alumno:

```
const data = '{ "alumnos": [{"nombre":"Diego"},{"nombre":"Carla"}] }';
// ¿Cómo obtener "Carla"?
```

Ejercicio 5 (desafío): Escribir un JSON válido que represente una lista de tareas, cada tarea tiene id, descripcion, completada y etiquetas (array). Crear 3 tareas con distintos estados.

## 6. Soluciones rápidas

Solución 1:

```
{
	"nombre": "Pablo",
	"edad": 34,
	"ciudad": "Quito"
}
```

Solución 2:

```
["manzana", "banana", "uva"]
```

Solución 3:

```
{
	"titulo": "Introducción a APIs",
	"duracion": 8,
	"docentes": ["Ana", "Luis"],
	"online": true
}
```

Solución 4 (JavaScript):

```
const obj = JSON.parse(data);
console.log(obj.alumnos[1].nombre); // Carla
```

Solución 5 (ejemplo):

```
[
	{ "id": 1, "descripcion": "Enviar reporte", "completada": false, "etiquetas": ["trabajo"] },
	{ "id": 2, "descripcion": "Comprar leche", "completada": true, "etiquetas": ["hogar"] },
	{ "id": 3, "descripcion": "Estudiar JSON", "completada": false, "etiquetas": ["aprendizaje", "programacion"] }
]
```

## 7. Errores comunes y cómo solucionarlos

- Olvidar comillas dobles en claves o strings -> usar validador para ver el error de parseo.
- Coma extra al final -> el validador indica "Unexpected token".
- Valores no válidos (NaN, funciones) -> JSON solo soporta tipos primitivos y objetos/arrays.

## 8. Herramientas y recursos útiles

- Validador online: https://jsonlint.com/ o https://jsonformatter.curiousconcept.com/
- Extensión VSCode: soporte JSON integrado y linters.
- Documentación: https://www.json.org/json-es.html
