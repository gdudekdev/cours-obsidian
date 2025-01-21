#js

### **1. Déclaration de Variables**

- `let` : Déclare une variable avec portée de bloc.
- `const` : Déclare une variable constante, sa valeur ne peut pas être modifiée.
- `var` : Déclare une variable avec portée fonctionnelle (anciennement utilisé, à éviter).

javascript

`let x = 10; const name = "Alice"; var y = 20;`

---

### **2. Types de Données**

- **Primitifs** : `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`
- **Objet** : `Object`, `Array`, `Function`, etc.

`let str = "Hello";  // string let num = 42;       // number let isActive = true; // boolean let obj = { name: "Alice", age: 25 }; // object let arr = [1, 2, 3]; // array let notDefined; // undefined`

---

### **3. Structures de Contrôle**

- **Conditionnelle**

`if (x > 10) {     console.log("Plus grand que 10"); } else if (x === 10) {     console.log("Égale à 10"); } else {     console.log("Plus petit que 10"); }`

- **Switch**

`switch (x) {     case 1:         console.log("C'est un");         break;     case 2:         console.log("C'est deux");         break;     default:         console.log("Autre"); }`

- **Boucles**

`// For loop for (let i = 0; i < 10; i++) {     console.log(i); }  // While loop let i = 0; while (i < 10) {     console.log(i);     i++; }  // For...of (pour tableaux) for (let item of arr) {     console.log(item); }  // For...in (pour objets) for (let key in obj) {     console.log(key, obj[key]); }`

---

### **4. Fonctions**

- Déclaration

`function greet(name) {     return "Hello, " + name; }  let result = greet("Alice"); // "Hello, Alice"`

- Fonction fléchée (arrow function)

`const sum = (a, b) => a + b; console.log(sum(3, 5)); // 8`

- Fonction anonyme

`let sayHello = function(name) {     return "Hello, " + name; }; console.log(sayHello("Bob"));`

---

### **5. Manipulation des Objets**

`let person = {     name: "John",     age: 30,     greet: function() {         console.log("Hello " + this.name);     } };  // Accéder aux propriétés console.log(person.name); // "John" console.log(person['age']); // 30  // Ajouter une propriété person.city = "Paris";  // Supprimer une propriété delete person.age;`

---

### **6. Tableaux (Arrays)**

- Créer un tableau

`let fruits = ["Apple", "Banana", "Cherry"];`

- Accéder aux éléments

`console.log(fruits[0]); // "Apple"`

- Ajouter un élément

`fruits.push("Grape"); // Ajoute à la fin fruits.unshift("Orange"); // Ajoute au début`

- Supprimer un élément

`fruits.pop(); // Supprime du dernier fruits.shift(); // Supprime du premier`

- Boucle sur un tableau
- 
`for (let fruit of fruits) {     console.log(fruit); }`

---

### **7. Manipulation des Chaînes de Caractères**

`let str = "Hello World";  // Longueur console.log(str.length); // 11  // Conversion en majuscules / minuscules console.log(str.toUpperCase()); // "HELLO WORLD" console.log(str.toLowerCase()); // "hello world"  // Substring console.log(str.substring(0, 5)); // "Hello"  // Recherche d'un mot console.log(str.includes("World")); // true  // Remplacer une partie de la chaîne console.log(str.replace("World", "JavaScript")); // "Hello JavaScript"`

---

### **8. Gestion des Promesses (Promises)**

Les promesses sont utilisées pour gérer les opérations asynchrones.

`let promise = new Promise((resolve, reject) => {     let success = true;     if (success) {         resolve("Tout va bien !");     } else {         reject("Il y a eu une erreur.");     } });  promise     .then((result) => {         console.log(result); // "Tout va bien !"     })     .catch((error) => {         console.log(error); // "Il y a eu une erreur."     });`

---

### **9. Manipulation du DOM (Document Object Model)**

- Sélectionner un élément

`let element = document.getElementById("monElement");  // Par ID let elements = document.querySelectorAll(".className"); // Par classe`

- Modifier le contenu

`element.innerHTML = "Bonjour, le monde!"; element.style.color = "blue";`

- Ajouter un événement

`element.addEventListener("click", function() {     alert("Élément cliqué !"); });`

- Créer un nouvel élément

`let newElement = document.createElement("div"); newElement.innerText = "Nouveau div!"; document.body.appendChild(newElement);`

---

### **10. Les Classes et Objets**

`class Person {     constructor(name, age) {         this.name = name;         this.age = age;     }      greet() {         console.log("Hello " + this.name);     } }  let person1 = new Person("Alice", 25); person1.greet(); // "Hello Alice"`

---

### **11. Les Opérateurs**

- **Arithmétiques** : `+`, `-`, `*`, `/`, `%`, `++`, `--`
- **Logiques** : `&&` (ET), `||` (OU), `!` (NON)
- **Comparaison** : `==`, `===` (strict), `!=`, `>`, `<`, `>=`, `<=`
- **Conditionnels** : `?:` (opérateur ternaire)

`let a = 10; let b = 5; console.log(a + b); // 15  let isTrue = true; let isFalse = false; console.log(isTrue && isFalse); // false  let result = (a > b) ? "A est plus grand" : "B est plus grand"; console.log(result); // "A est plus grand"`

---

### **12. Déstructuration (Destructuring)**

- **Tableaux**

`let arr = [1, 2, 3]; let [a, b] = arr; console.log(a, b); // 1, 2`

- **Objets**

`let person = { name: "John", age: 30 }; let { name, age } = person; console.log(name, age); // "John", 30`

---

### **13. Spread et Rest**

- **Spread (pour les objets et tableaux)**

`let arr = [1, 2, 3]; let newArr = [...arr, 4, 5]; // [1, 2, 3, 4, 5]  let obj = { name: "Alice", age: 25 }; let newObj = { ...obj, city: "Paris" }; // { name: "Alice", age: 25, city: "Paris" }`

- **Rest (pour les paramètres de fonction)**

`function sum(...numbers) {     return numbers.reduce((acc, num) => acc + num, 0); } console.log(sum(1, 2, 3, 4)); // 10`

---

### **14. Async/Await (Asynchrone)**

`async function fetchData() {     let response = await fetch("https://api.example.com");     let data = await response.json();     console.log(data); } fetchData();`

---

### **15. Modèles de chaînes (Template Literals)**

``let name = "Alice"; let age = 25; console.log(`Je m'appelle ${name} et j'ai ${age} ans.`);``

---

### **16. JSON (JavaScript Object Notation)**

- **Parse JSON** : Convertir une chaîne JSON en objet JavaScript

`let jsonString = '{"name": "Alice", "age": 25}'; let jsonObj = JSON.parse(jsonString); console.log(jsonObj.name); // "Alice"`

- **Stringify JSON** : Convertir un objet JavaScript en chaîne JSON

`let obj = { name: "Alice", age: 25 }; let jsonString = JSON.stringify(obj); console.log(jsonString); // '{"name":"Alice","age":25}'`