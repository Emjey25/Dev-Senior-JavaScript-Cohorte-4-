
## ¿Qué es JSON? (Explicación simple)

Imagínate que JSON es como una **caja organizada** donde guardamos información de forma ordenada.

**JSON** significa "JavaScript Object Notation", pero no te preocupes por el nombre complicado. Solo piensa en él como una forma de **escribir información que las computadoras entienden fácilmente**.

### ¿Por qué es importante?
- Es la forma más común de intercambiar información en internet
- Las páginas web lo usan para "hablar" con los servidores
- Es más fácil de leer que otros formatos

---

## ¿Cómo se ve JSON?

JSON se ve muy parecido a los objetos de JavaScript, pero con algunas reglas estrictas:

```json
{
  "nombre": "Juan",
  "edad": 20,
  "estudiante": true
}
```

### Piénsalo así:
- Es como una **libreta de contactos** digital
- Cada "página" tiene información organizada en pares de **etiqueta: valor**
- La etiqueta siempre va entre comillas dobles `"`

---

## Reglas básicas (¡Muy importantes!)

### ✅ SÍ se puede hacer:
```json
{
  "nombre": "Ana"
}
```

### ❌ NO se puede hacer:
```json
{
  nombre: "Ana"
}
```

### Las reglas son:
1. **Siempre usar comillas dobles** `"` (nunca simples `'`)
2. **Las etiquetas (claves) van entre comillas**
3. **No poner coma al final**

---

## Tipos de información que puede guardar JSON

### 1. Texto (String)
```json
{
  "nombre": "María",
  "ciudad": "Madrid"
}
```

### 2. Números
```json
{
  "edad": 25,
  "altura": 1.75
}
```

### 3. Verdadero o Falso (Boolean)
```json
{
  "tieneNovio": true,
  "esEstudiante": false
}
```

### 4. Nada/Vacío (null)
```json
{
  "segundoNombre": null
}
```

### 5. Listas (Array)
```json
{
  "coloresFavoritos": ["azul", "verde", "rojo"]
}
```

### 6. Más información dentro (Objeto)
```json
{
  "direccion": {
    "calle": "Calle Mayor 123",
    "ciudad": "Madrid"
  }
}
```

---

## Ejemplo completo y fácil

Imagina que queremos describir a una persona en JSON:

```json
{
  "nombre": "Carlos",
  "apellido": "García",
  "edad": 22,
  "esEstudiante": true,
  "materiasFavoritas": ["JavaScript", "HTML", "CSS"],
  "contacto": {
    "email": "carlos@email.com",
    "telefono": "123-456-789"
  },
  "mascota": null
}
```

### ¿Qué nos dice esto?
- Se llama Carlos García
- Tiene 22 años
- Sí es estudiante
- Le gustan 3 materias
- Su email es carlos@email.com
- Su teléfono es 123-456-789
- No tiene mascota

---

## JSON en JavaScript (Lo práctico)

### De JavaScript a JSON
```javascript
// Tengo un objeto en JavaScript
let persona = {
  nombre: "Ana",
  edad: 20
};

// Lo convierto a JSON (texto)
let textoJSON = JSON.stringify(persona);
console.log(textoJSON); // '{"nombre":"Ana","edad":20}'
```

### De JSON a JavaScript
```javascript
// Tengo un texto en formato JSON
let textoJSON = '{"nombre":"Luis","edad":25}';

// Lo convierto a objeto de JavaScript
let persona = JSON.parse(textoJSON);
console.log(persona.nombre); // "Luis"
```

### Recuerda:
- `JSON.stringify()` = Objeto → Texto JSON
- `JSON.parse()` = Texto JSON → Objeto

---

## Ejercicio súper fácil 🎯

### Paso 1: Crear tu primer JSON
Crea un archivo con tu información personal:

```json
{
  "nombre": "Tu nombre aquí",
  "edad": 0,
  "esEstudiante": true,
  "materiaFavorita": "JavaScript"
}
```

### Paso 2: Probarlo en JavaScript
```javascript
// Copia tu JSON aquí
let miInfo = '{"nombre":"Tu nombre","edad":20,"esEstudiante":true}';

// Convertirlo a objeto
let persona = JSON.parse(miInfo);

// Mostrar la información
console.log("Hola, soy " + persona.nombre);
console.log("Tengo " + persona.edad + " años");
```

---

## Errores típicos de principiantes

### Error 1: Usar comillas simples
```javascript
// ❌ Mal
'{"nombre": 'Juan'}'

// ✅ Bien
'{"nombre": "Juan"}'
```

### Error 2: Olvidar comillas en las claves
```javascript
// ❌ Mal
'{nombre: "Juan"}'

// ✅ Bien
'{"nombre": "Juan"}'
```

### Error 3: Poner coma al final
```javascript
// ❌ Mal
'{"nombre": "Juan",}'

// ✅ Bien
'{"nombre": "Juan"}'
```

---

## ¿Cuándo usamos JSON?

### 1. Cuando una página web pide información a un servidor
```javascript
// La página pide información de un usuario
// El servidor responde con JSON:
'{"nombre": "Ana", "edad": 25, "email": "ana@email.com"}'
```

### 2. Para guardar configuraciones
```json
{
  "colorTema": "oscuro",
  "idioma": "español",
  "mostrarNotificaciones": true
}
```

### 3. Para guardar listas de cosas
```json
{
  "productos": [
    {"nombre": "Café", "precio": 3.50},
    {"nombre": "Té", "precio": 2.25}
  ]
}
```

---

## Consejos para principiantes

### 1. Practica escribiendo JSON a mano
- Empieza con ejemplos simples
- Siempre revisa que tengas todas las comillas
- Usa un validador online como jsonlint.com

### 2. Usa las herramientas del navegador
```javascript
// Para ver JSON bonito en la consola
console.log(JSON.stringify(miObjeto, null, 2));
```

### 3. No te preocupes por memorizar todo
- Lo importante es entender el concepto
- Con la práctica se vuelve natural
- Siempre puedes revisar los ejemplos

---

## Práctica paso a paso

### Ejercicio 1: Tu primer JSON
Crea un JSON que describa tu comida favorita:
```json
{
  "nombre": "Pizza",
  "tipo": "italiana",
  "ingredientes": ["queso", "tomate", "jamón"],
  "precio": 12.50,
  "esVegetariana": false
}
```

### Ejercicio 2: Convertir a JavaScript
```javascript
let comidaJSON = '{"nombre":"Pizza","precio":12.50}';
let comida = JSON.parse(comidaJSON);

console.log("Mi comida favorita es: " + comida.nombre);
console.log("Cuesta: $" + comida.precio);
```

### Ejercicio 3: De JavaScript a JSON
```javascript
let miLibro = {
  titulo: "Harry Potter",
  autor: "J.K. Rowling",
  paginas: 500
};

let libroJSON = JSON.stringify(miLibro);
console.log(libroJSON);
```

---

## Resumen para recordar 📚

✅ JSON es una forma organizada de escribir información  
✅ Siempre usar comillas dobles `"`  
✅ Las claves (etiquetas) van entre comillas  
✅ `JSON.stringify()` convierte objeto a texto  
✅ `JSON.parse()` convierte texto a objeto  
✅ Es muy usado en páginas web modernas  
