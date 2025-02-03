#js

### DOM (*Document Object Model)

Le DOM est une API permettant d'interagir avec notre fichier HTML en direct avec JS.
L'API va interpréter notre HTML, va en créer une arborescence et le stocker dans un document.

`// console.log(document);`

  

`// ==========================`

`//  Selection des elements du DOM`

`// ==========================`

  

`// Recuperation par reference a la balise`

`const h1_element = document.querySelector("h1");`

`// console.log(h1_element);`

`// Recuperation par reference a la class`

`const active_list_element = document.querySelector(".active");`

`// console.log(active_list_element);`

`// Recuperation par reference a l'id`

`const id_element = document.querySelector("#best-fruit");`

`// console.log(id_element);`

  

`// Affiche le premier element li de la liste ul`

`const li_element = document.querySelector("#list > li");`

`// console.log(li_element);`

  

`// Affiche tous les li de la liste ul dans un objet Nodelist`

`const ul_list_element = document.querySelectorAll("#list li");`

`// console.log(ul_list_element);`

  

`// null <- EVENT_TARGET <- NODE <- ELEMENT <- HTML_ELEMENT / HTML_DOCUMENT`

`// Chaque element herite des methodes et des proprietes de ses parents (comme les classes css)`

  

`// ex: sur l'objet ELEMENT: la methode remove() existe mais ne sera pas forcement presente sur ses enfants`

  

`// ==========================`

`//  Methodes de manipulation du DOM`

`// ==========================`

  

`// Suppression d'un noeud par la methode remove`

`active_list_element.remove();`

  

`const ul_element = document.querySelector("ul");`

`// console.log(ul_element.parentElement, ul_element.children);`

  

`// Suppression du deuxieme element dans la liste ul (indexation a partir de 0)`

`ul_element.removeChild(ul_element.children.item(1));`

  

`// Modification de texte`

`h1_element.textContent = "Liste de super fruits ! :)";`

  

`// Ajout d'un nouvel element dans notre liste`

`const new_fruit_element = document.createElement("li");`

`new_fruit_element.textContent = "Framboise";`

  

`ul_element.appendChild(new_fruit_element);`

  

`//  Recuperer ou de definir le contenu HTML a l'interieur d'un element (pas conseille : faille XSS)`

`ul_element.innerHTML += "<li>Fragment</li>";`

  

`// Autres methodes utiles (il en existe plein d'autres)`

`// ul_element.after()`

`// ul_element.before()`

`// ul_element.insertBefore()`

`// ul_element.replaceChild()`

`// ul_element.replaceChildren()`

  

`// Modification d'un attribut CSS (attention:camelCase)`

`ul_element.style.backgroundColor = "red";`

  

`// Manipulation de class CSS par le DOM`

`ul_element.classList.add("bigText");`

`// ul_element.classList.remove("bigText");`

`// ul_element.classList.toggle("bigText");`

  

`// ==========================`

`//  Evenements`

`// ==========================`

  

`// Formulaire`

`const form_element = document.querySelector("form");`

  

`// Ecouteur d'evenement sur le click`

`// form_element.addEventListener("click", function (event) {`

`//     console.log(event,"J'ai clique sur le formulaire");`

`//   });`

  

`// Ecouteur d'evenement sur la soumission d'un formulaire`

`form_element.addEventListener("submit", function (event) {`

  `event.preventDefault(); //Empeche le comportement natif du navigateur de soumission par URL`

  `const formData = new FormData(form_element); //Permet de recuperer toutes les entrees du formulaire`

  `const nom_fruit = formData.get("nom_fruit");`

  `const new_fruit_element = document.createElement("li");`

  `new_fruit_element.textContent = nom_fruit;`

  

  `ul_element.appendChild(new_fruit_element);// Ajout dynamique de l'element rempli dans le formulaire lors de la lecture du click`

  

  `form_element.reset();`

`});`