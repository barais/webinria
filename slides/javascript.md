#  JavaScript

----

##  JavaScript

- Définition
- Syntaxe
- Les objets
- Les évènements
- Les boîtes de dialogue
- Accès à un élément quelconque d'une page

----

##  JavaScript

- Mais à quoi ça sert ?
  - Manipulation et animation dynamiques du contenu des pages Web
  - Ouverture, fermeture de fenêtres
  - Communication avec « le » serveur
    - Warning : cross-domain scripting
  - Enregistrement des actions de l'utilisateur (!)
  - Réaction aux évènements utilisateur
  - Sauvegarde de données...

----

##  Définition

> JavaScript est un langage de programmation orienté objet développé par NETSCAPE dans les années 90, et s'appelait à l'origine LiveScript.

- Il fut adopté par la firme SUN (qui est à l'origine du langage JAVA) en 1995.
- Le JavaScript est une extension du langage HTML.

----
## Popularité de JavaScript (1)

- JavaScript, le langage de programmation populaire avec la plus importante progression (mais pas le plus grand nombre de lignes de code déployées)
- JavaScript langage de l'année 2014 et 2015 selon  l'Index TIOBE (nombre de développeurs + nombre de tutoriaux + nombre de vendeurs tiers, sur la base des recherches dans les moteurs Google, Bing, Yahoo!, Wikipedia, Amazon, YouTube et Baidu)

<div align="right"><img src="resources/image_3.png" width="10%"></div>

----
## Popularité de JavaScript (2)

<div align="center"><img src="resources/image_4.png" width="80%"></div>

http://www.tiobe.com/index.php/content/paperinfo/tpci/index.html

----
## Popularité de JavaScript (3)

- Autres indicateurs de popularité :
  - GitHub (plus nombre de dépôts de source avec JavaScript et plus projets JavaScript les plus populaires)
   - http://adambard.com/blog/top-github-languages-2014/
   - http://redmonk.com/sogrady/2014/01/22/language-rankings-1-14/
   - http://www.thoughtworks.com/radar/
   - http://pypl.github.io/PYPL.html

----
  <div align="center"><img src="resources/image_5.png" width="65%"></div>

  https://github.com/search?q=stars%3A%3E1&s=stars&type=Repositories

----
## Popularité de JavaScript (4)

- JavaScript présent dans tous les navigateurs web avec maintenant des implémentations à jour
- ECMAScript 6 disponible et implémentation progressive dans les différents moteurs
- Node.js et NPM à la base du nouveau succès de JavaScript (après avoir été le langage le plus détesté)
- Le plus de modules tiers disponibles grâce à NPM et GitHub. Il existe un module JavaScript existant pour quasiment chaque besoin, ou bien il est en train d'être écrit !

----
## Popularité de JavaScript (5)

http://modulecounts.com/
<div align="center"><img src="resources/image_6.png" width="85%"></div>

----
## Node.js choisi par les entreprises du web

- Plus de téléchargements des modules NPM durant la semaine que le week-end et les vacances
- Les modules JavaScript sont plus utilisés et développés dans le cadre des entreprises que dans le cadre des loisirs
- Node.js utilisé en production par Dow Jones, eBay, Walmart, PayPal, LinkedIn, Yahoo!, The New York Times, Über, Airbnb, Groupon, SAP, Rakuten, TF1, Google
- Node.js supporté officiellement par Oracle (http://nodejs.org/industry/)

----
## D'autres choix

- D'autres acteurs n'utilisent pas Node.js côté serveur :
  - Chez Twitter c'est du Java (après avoir débuté avec du Ruby On Rails)
  - Chez Facebook c'est du Hack (un nouveau PHP)
  - Chez GitHub c'est du Ruby On Rails et du Erlang
  - Google utilise d'autres langages que JavaScript et d'autres plateformes que Node.js : notamment Go (en remplacement de C++)

----
  ## Ubiquité

- On peut utiliser JavaScript :
 - Sur navigateur pour sites web et web apps
 - Sur serveur pour applications web
 - Sur navigateur + serveur pour applications isomorphiques
 - Sur serveur et poste développeur pour scripts/batches systèmes (export CSV, transformation/conversion de données, etc.)
 - Sur serveur et poste développeur pour scripts web (SlimerJS, PhantomJS, etc.)


----
 ## JavaScript
- Spécification de référence: ECMAScript-262 (édition 6.0 – 2015)
-  Fonctionnalités additionnelles incompatibles
- Caractéristiques :
 - Langage interprété
 - moteur intégré dans les navigateurs
 - Basé objet mais orienté prototype
 - Dynamique (typage, fonctions, code...)
 - Événementiel


----
## ECMAScript 6

- La spécification ECMAScript 6 est aussi appelée ES6, Harmony ou ES.next
- Finalisation de la spécification Juin 2015
- Les différents moteurs JavaScript implémentent  déjà progressivement ECMAScript 6 depuis des années en évoluant en même temps que la spec
- Apporte ce qui manquait à JavaScript pour faciliter la vie des développeurs (et qu'on pouvait déjà trouver dans d'autres langages comme Python, Java, etc.) : modules, collections, template strings, iterateurs, générateurs, etc.

----
## JavaScript

- Orienté “prototype” ???
 - Basé objet mais pas orienté objet
 - On déclare un objet générique, puis héritage
- Dynamique ???
 - Typage, fonctions, code...
 - Pratique mais dangereux...
- Événementiel ???
 - Paradigme de programmation
 - Attente” puis réaction aux actions “utilisateur”


----
### Définition

** Javascript **	| ** Java**
-- | --
Langage interprété		|  Langage compilé
Code intégré au HTML		|  Code (applet)
Langage peu typé		| Langage fortement typé
Liaisons dynamiques: les références des objets sont vérifiées au chargement		|  Liaisons statiques: Les objets doivent exister au chargement (compilation)
Accessibilité du code		|  Confidentialité du code
Sûr: ne peut pas écrire sur le disque dur		|  Sûr: ne peut pas écrire sur le disque dur


----
## JavaScript

- Définition
- **Syntaxe**
- Les objets
- Les évènements
- Les boîtes de dialogue
- Accès à un élément quelconque d'une page

----
## Syntaxe

- Intégration du script dans la page

```html
*inline*
<script type=”text/javascript”>....</script>
```

Appel externe avec une réf. comme pour css

```html
<script src=”/js/script.js” type=”text/javascript”/>
```

- Chargement du script
 - Importance du placement dans la page
 - Dans le header (délai)
 - Dans le body, ou en fin de body
 - Cache si appel externe (mieux), compression

----
## Syntaxe
- Bonnes pratiques
 - Fichier .js externe
- Lecture par événement “onload”
- “Separation of concerns” (Dijkstra)
 - Pour le script principal
 - Utilisation de fonctions
- chargement dynamique (cf plus tard)

----
## Syntaxe

- Le code JavaScript se trouve dans un fichier ayant pour extension .js

- L'inclusion de ce fichier se fait généralement au début des pages HTML grâce à la balise script:

```html
<script type="text/javascript" src="url/nomdufichier.js"> </script>
```

----
## Syntaxe

- Les structures conditionnelles ou répétitives (boucles)ont la même syntaxe qu'en langage C.
- JavaScript est un langage faiblement typé.

----
## Syntaxe

### Portée des variables:

- Une variable déclarée en début de script sera considérée comme étant globale.

- Les variables utilisées/déclarées dans une fonction restent locales à la fonction.


----
## Syntaxe

- The JavaScript syntax is similar to C# and Java
 - Operators (**+, *, =, !=, &&, ++, …)**
 - Variables (typeless)
 - Conditional statements (**if**, **else**)
 - Loops (**for**, **while**)
 - Arrays (**my_array[]**) and associative arrays (**my_array['abc']**)
 - Functions (can return value)
 - Function variables (like the *C#* delegates)

----
## JavaScript data types

- Numbers (integer, floating-point)
- Boolean (true / false)
- String type – string of characters

```js
var myName = "You can use both single
               or double quotes for strings";
```

- Arrays

```js
var my_array = [1, 5.3, "aaa"];
```

- Associative arrays (hash tables)

```js
var my_hash = {a:2, b:3, c:"text"};
```

----
## Everything is Object

- Every variable can be considered as object
- For example strings and arrays have member functions:

```js
// file: objects.html
var test = "some string";
alert(test[7]);               // shows letter 'r'
alert(test.charAt(5));        // shows letter 's'
alert("test".charAt(1));      // shows letter 'e'
alert("test".substring(1,3)); // shows 'es'
var arr = [1,3,4];
alert (arr.length); // shows 3
arr.push(7);        // appends 7 to end of array
alert (arr[3]);     // shows 7
```

----
### String Operations

The + operator joins strings (slow)

```js
string1 = "lol ";
string2 = "cats";
alert(string1 + string2);  // lol cats
```

What is "11" + 11?

```js
alert("11" + 11);  // 1111
```

Converting string to number:

```js
alert(parseInt("11") + 11);       // 22
alert(parseInt("011",8) + 11);      // 20 ???
alert(parseInt("011", 10) + 11);  // 22
```

----
### Arrays Operations and Properties

Declaring new empty array:

```js
var arr1 = new Array(); var arr2 = [];
```

Declaring an array holding few elements:

```js
var arr = [1, 2, 3, 4, 5];
```


Appending an element / getting the last element:

```js
arr.push(3); var element = arr.pop();
```


Reading the number of elements (array length):

```js
arr.length;
```

Finding element's index in the array:

```js
arr.indexOf(1);
```

----
## Conditional Statement (if)

```js
unitPrice = 1.30;
if (quantity > 100) {
  unitPrice = 1.20;
}

/*
Greater than: >
Less than: <
Greater than or equal to: >=
Less than or equal to: <=
Equal: ==
Not equal: !=
*/
```

----
## Conditional Statement (if)

The condition may be of Boolean or integer type:

```js
var a = 0;
var b = true;
if (typeof(a)=="undefined" || typeof(b)=="undefined") {
  document.write("Variable a or b is undefined.");
}
else if (!a && b) {
  document.write("a==0; b==true;");
} else {
  document.write("a==" + a + "; b==" + b + ";");
}
```

----
### Switch Statement

The switch statement works like in C#:

```js
switch (variable) {
  case 1:
    // do something
    break;
  case 'a':
    // do something else
    break;
  case 3.14:
    // another code
    break;
  default:
    // something completely different
}
```

----
### Loops

Like in C# (for, while, do while)
```js
/*
for loop
while loop
do … while loop
*/
var counter;
for (counter=0; counter<4; counter++) {
  alert(counter);
}
for (var key in haystack);
while (counter < 5) {
  alert(++counter);
}
```

----
## Syntaxe

- Les fonctions:
  - La syntaxe de définition d'une fonction est:
  ```js
function nomFonction(arg1,arg2,...)
```
  - Contrairement au langage C, on ne donne pas le type des arguments ni celui de la valeur de retour éventuelle

----
## Syntaxe

- Les chaînes de caractères:
 - Une chaîne de caractères est délimitée par des guillemets simples ou doubles.
 - Exemple:

 ```js
texte = "un beau texte"
```
Ou
```js
texte = 'un beau texte'
```

----
## Syntaxe
- Les chaînes de caractères:
 - Pour manipuler des chaînes de caractères, il existe de nombreuses fonctions.
 - Contrairement au langage C, il est possible de comparer deux chaînes de caractères à l'aide de l'opérateur ==.

----
## Functions


- Code structure – splitting code into parts
- Data comes in, processed, result returned
```js
function average(a, b, c) {
    var total;
    total = a+b+c;
    return total/3;
}
```
- Anonymous functions
```js
var average = function (a, b, c) { ... }
var res1 = average(1,2,3);
var myAvg = average;
var res2 = myAvg(1,2,3);
```

----
## Function Arguments and Return Value
- Functions are not required to return a value
- When calling function it is not obligatory to specify all of its arguments
- The function has access to all the arguments passed via arguments array

```js
function sum() {
  var sum = 0;
  for (var i = 0; i < arguments.length; i ++)
    sum += parseInt(arguments[i]);
  return sum;
}
alert(sum(1, 2, 4));
```

----
## JavaScript
- Définition
- Syntaxe
- **Les objets**
- Les évènements
- Les boîtes de dialogue
- Accès à un élément quelconque d'une page

----
## Les objets
- L'utilisation principale de JavaScript est la manipulation des objets d'une page et plus particulièrement des objets des formulaires
- Il est possible d'interagir à deux niveaux:
 - Au niveau du navigateur internet
 - Au niveau de la page affichée dans le navigateur

----
 ## Les objets
-  Une page est composée de façon hiérarchique.

----
## Les objets
<img src="resources/anim/image_1.jpg" width="60%">

----
## Les objets
<img src="resources/anim/image_3.jpg" width="60%">

----
## Les objets
<img src="resources/anim/image_4.png" width="60%">

----
## Les objets
<img src="resources/anim/image_5.png" width="60%">

----
## Les objets
- L'accès se fait de façon hiérarchique.
```js
window.document.forms["nomDuformulaire"].nomDeLélément
```
- Pour chaque niveau il existe des méthodes et des attributs. Exemple:
```html
<html><body>
		<form name="monForm">
			<label for="login">Votre login :</label>
			<input type="text" name="login" id="login" />
		</form>
</body></html>
```
- Si je souhaite avoir la valeur contenue dans le champ login du formulaire, j'utiliserai le code JavaScript suivant:

```js
leLogin=window.document.forms["monForm"].login.value;
```

----
## Les objets
- Classes are functions
- Objects are associative arrays
- **this** refers to the owning code
- **new** copies the prototype into new reference

```js
var person = new Object();
person.first = "Tim";
person.last = "Scarfe";

person.sayHello = function() {
    console.log("Hello, " + this.first + " " + this.last);
};
person.sayHello();
```

----
## Les objets
```js
function User(first, last) {
    this.first = first;
    this.last = last;

    this.sayHello = function() {
        console.log("Hello, " + this.first
                  + " " + this.last);
    }
}

var svi = new User("Svi", "Ivanov");
var alex = new User("Alex", "Ivanova");
svi.sayHello();
alex.sayHello();
```

----
## JavaScript
- Définition
- Syntaxe
- Les objets
- **Les évènements**
- Les boîtes de dialogue
- Accès à un élément quelconque d'une page

----
## Les évènements
- L'action sur un élément de la page se fait lors d'un événement particulier (clique de souris, changement de la valeur d'un champ, etc)
- Voici quelques évènements possibles pour une page WEB
 - Click (onClick)
 - Load (onLoad)
 - Unload (onUnload)
 - MouseOver (onMouseOver)
 - MouseOut (onMouseOut)
 - Focus (onFocus)
 - Change (onChange)
 - Submit (onSubmit)


----
 ## Les évènements
 - Pour qu'un objet réagisse à un événement, il faut lui associer une fonction de traitement.
 - Exemple:
 ```html
 <html><body>
<script src="mesFonctions.js" type="text/javascript"></script>
	<form name="monForm">
		<label for="login">Votre login :</label>
		<input type="text" name="login" id="login"
        onchange="afficheLogin();">
		<input type="text" name="loginBis" id="loginBis">
	</form>
</body></html>
 ```
 - Le fichier mesFonctions.js contient le code suivant:
 ```js
 function afficheLogin(){						   
   window.document.forms["monForm"].loginBis.value =
     window.document.forms["monForm"].login.value;
 }
 ```

----

## JavaScript
- Définition
- Syntaxe
- Les objets
- Les évènements
- **Les boîtes de dialogue**
- Accès à un élément quelconque d'une page

----
### Les boîtes de dialogue
- Il existe 3 types de boîtes de dialogue:
 - alert : affiche un message et un bouton ok
<div align="center"> <img src="resources/image_8.png" width="35%"></div>
 - confirm : affiche un message et un bouton ok et annuler
 <div align="center"> <img src="resources/image_9.png" width="35%"></div>

----
 ### Les boîtes de dialogue
- prompt : affiche une zone de saisie et un bouton ok.
 <div align="center"> <img src="resources/image_10.png" width="35%"></div>
- confirm retournera true ou false selon la réponse (ok ou annuler).
- prompt retournera le message contenu dans la zone de saisie.

----
## JavaScript
- Définition
- Syntaxe
- Les objets
- Les évènements
- Les boîtes de dialogue
- **Accès à un élément quelconque d'une page**

----
### Accès à un élément quelconque d'une page

- La manière la plus simple pour avoir accès à un élément quelconque d'une page est d'utiliser son identifiant
```js
var obj = document.getElementById("idelement") ;
```

- Il est ainsi possible d'avoir des informations et d'agir sur l'élément
 - **innerHTML** : va recupérer/modifier le contenu HTML de l'élément
 - **textContent** : va recupérer/modifier le contenu de l'élément
 - **nodeName** : va recupérer le nom de l'élément

----

## An example

```html
<div id="div1"></div>
<input type="button" value="Vert" onclick="vert();"/>
<input type="button" value="Rouge" onclick="rouge();"/>
```

----
## An example

```css
 #div1{
   background-color:#ff0000;
   width:200px;
   height:200px;
 }
```

----
## An example

```js
function vert(){
   document.getElementById('div1').style.backgroundColor='#00ff00';
}
function rouge(){
   document.getElementById('div1').style.backgroundColor='#ff0000';
}
```
