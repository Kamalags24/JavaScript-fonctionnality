# JavaScript-fonctionnality


Voici une liste de fonctionnalités courantes en JavaScript :

1. **Manipulation du DOM** :
   - Sélection et modification d'éléments (`document.getElementById`, `document.querySelector`, etc.)
   - Ajout et suppression de classes (`classList.add`, `classList.remove`)
   - Création et suppression d'éléments (`document.createElement`, `element.remove`)

2. **Gestion des événements** :
   - Ajout d'écouteurs d'événements (`addEventListener`)
   - Gestion des événements (`click`, `mouseover`, `keydown`, etc.)
   - Événements personnalisés (`CustomEvent`)

3. **Ajax et Fetch API** :
   - Requêtes HTTP (`XMLHttpRequest`, `fetch`)
   - Promesses pour la gestion asynchrone (`then`, `catch`, `async/await`)

4. **Manipulation des objets et des tableaux** :
   - Méthodes de tableau (`map`, `filter`, `reduce`, `forEach`)
   - Manipulation des objets (accès aux propriétés, méthodes `Object.keys`, `Object.values`)

5. **Fonctions et scope** :
   - Déclaration de fonctions (`function`, `const`, `let`, `var`)
   - Fonctions fléchées (`=>`)
   - Scope des variables (global, local, closures)

6. **Modules ES6** :
   - Importation et exportation de modules (`import`, `export`)
   - Modules par défaut et nommés

7. **Manipulation des dates et des heures** :
   - Objet `Date`
   - Méthodes pour obtenir et définir les composants de la date (`getFullYear`, `setMonth`, etc.)

8. **Gestion des erreurs** :
   - Bloc `try/catch`
   - Génération d'erreurs (`throw`)

9. **Manipulation des chaînes de caractères** :
   - Méthodes de chaîne (`slice`, `substring`, `replace`, `toUpperCase`, `toLowerCase`)
   - Modèles de chaînes de caractères (`template literals`)

10. **Classes et programmation orientée objet** :
    - Déclaration de classes (`class`, `constructor`)
    - Héritage (`extends`, `super`)

11. **JSON** :
    - Sérialisation et désérialisation (`JSON.stringify`, `JSON.parse`)

12. **Local Storage et Session Storage** :
    - Stockage de données localement (`localStorage`, `sessionStorage`)
    - Méthodes (`setItem`, `getItem`, `removeItem`)

13. **Web APIs** :
    - Géolocalisation (`navigator.geolocation`)
    - Notification API (`Notification`)
    - Canvas API pour le dessin 2D

14. **Promise et Async/Await** :
    - Création et utilisation de promesses (`Promise`, `resolve`, `reject`)
    - Syntaxe asynchrone avec `async/await`

15. **Service Workers** :
    - Enregistrement et gestion des Service Workers pour les applications web progressives (PWA)

Ces fonctionnalités couvrent une large gamme de ce que JavaScript permet de faire dans le développement web moderne.

Voici des exemples d'implémentation pour les fonctionnalités courantes en JavaScript :

1. **Manipulation du DOM** :
   ```javascript
   // Sélection d'un élément
   const element = document.getElementById('myElement');

   // Modification du contenu
   element.textContent = 'Hello, world!';

   // Ajout et suppression de classes
   element.classList.add('active');
   element.classList.remove('inactive');

   // Création et suppression d'éléments
   const newElement = document.createElement('div');
   newElement.textContent = 'New Element';
   document.body.appendChild(newElement);

   newElement.remove();
   ```

2. **Gestion des événements** :
   ```javascript
   // Ajout d'un écouteur d'événement
   element.addEventListener('click', () => {
     alert('Element clicked!');
   });

   // Gestion des événements
   document.addEventListener('keydown', (event) => {
     if (event.key === 'Enter') {
       console.log('Enter key pressed');
     }
   });

   // Événements personnalisés
   const customEvent = new CustomEvent('myCustomEvent', { detail: { someData: 123 } });
   element.dispatchEvent(customEvent);
   ```

3. **Ajax et Fetch API** :
   ```javascript
   // Utilisation de Fetch API
   fetch('https://api.example.com/data')
     .then(response => response.json())
     .then(data => console.log(data))
     .catch(error => console.error('Error:', error));

   // Avec async/await
   async function fetchData() {
     try {
       const response = await fetch('https://api.example.com/data');
       const data = await response.json();
       console.log(data);
     } catch (error) {
       console.error('Error:', error);
     }
   }
   fetchData();
   ```

4. **Manipulation des objets et des tableaux** :
   ```javascript
   // Méthodes de tableau
   const numbers = [1, 2, 3, 4, 5];
   const doubled = numbers.map(num => num * 2);
   const even = numbers.filter(num => num % 2 === 0);
   const sum = numbers.reduce((acc, num) => acc + num, 0);

   // Manipulation des objets
   const user = { name: 'Alice', age: 25 };
   const keys = Object.keys(user);
   const values = Object.values(user);
   ```

5. **Fonctions et scope** :
   ```javascript
   // Déclaration de fonctions
   function greet(name) {
     return `Hello, ${name}`;
   }

   const greetArrow = name => `Hello, ${name}`;

   // Scope des variables
   let globalVar = 'I am global';
   function scopeExample() {
     let localVar = 'I am local';
     console.log(globalVar); // Accessible
     console.log(localVar); // Accessible
   }
   console.log(localVar); // Erreur, non accessible en dehors de la fonction
   ```

6. **Modules ES6** :
   ```javascript
   // Dans module1.js
   export const myVar = 42;
   export function myFunction() {
     console.log('Hello from module1');
   }

   // Dans module2.js
   import { myVar, myFunction } from './module1.js';
   console.log(myVar); // 42
   myFunction(); // 'Hello from module1'
   ```

7. **Manipulation des dates et des heures** :
   ```javascript
   const now = new Date();
   console.log(now.getFullYear()); // Année actuelle
   console.log(now.getMonth()); // Mois actuel (0-11)

   const future = new Date();
   future.setFullYear(2050);
   console.log(future.getFullYear()); // 2050
   ```

8. **Gestion des erreurs** :
   ```javascript
   try {
     throw new Error('Something went wrong');
   } catch (error) {
     console.error(error.message); // 'Something went wrong'
   }
   ```

9. **Manipulation des chaînes de caractères** :
   ```javascript
   const str = 'Hello, world!';
   console.log(str.slice(7)); // 'world!'
   console.log(str.replace('world', 'JavaScript')); // 'Hello, JavaScript!'
   console.log(str.toUpperCase()); // 'HELLO, WORLD!'

   // Modèles de chaînes de caractères
   const name = 'Alice';
   const greeting = `Hello, ${name}!`;
   console.log(greeting); // 'Hello, Alice!'
   ```

10. **Classes et programmation orientée objet** :
    ```javascript
    class Person {
      constructor(name, age) {
        this.name = name;
        this.age = age;
      }

      greet() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
      }
    }

    class Student extends Person {
      constructor(name, age, grade) {
        super(name, age);
        this.grade = grade;
      }

      study() {
        console.log(`${this.name} is studying for grade ${this.grade}.`);
      }
    }

    const alice = new Student('Alice', 20, 'A');
    alice.greet(); // 'Hello, my name is Alice and I am 20 years old.'
    alice.study(); // 'Alice is studying for grade A.'
    ```

11. **JSON** :
    ```javascript
    const obj = { name: 'Alice', age: 25 };
    const jsonString = JSON.stringify(obj);
    console.log(jsonString); // '{"name":"Alice","age":25}'

    const parsedObj = JSON.parse(jsonString);
    console.log(parsedObj); // { name: 'Alice', age: 25 }
    ```

12. **Local Storage et Session Storage** :
    ```javascript
    // Local Storage
    localStorage.setItem('username', 'Alice');
    const username = localStorage.getItem('username');
    console.log(username); // 'Alice'
    localStorage.removeItem('username');

    // Session Storage
    sessionStorage.setItem('sessionKey', '12345');
    const sessionKey = sessionStorage.getItem('sessionKey');
    console.log(sessionKey); // '12345'
    sessionStorage.removeItem('sessionKey');
    ```

13. **Web APIs** :
    ```javascript
    // Géolocalisation
    navigator.geolocation.getCurrentPosition(position => {
      console.log('Latitude:', position.coords.latitude);
      console.log('Longitude:', position.coords.longitude);
    });

    // Notification API
    if (Notification.permission === 'granted') {
      new Notification('Hello, world!');
    } else if (Notification.permission !== 'denied') {
      Notification.requestPermission().then(permission => {
        if (permission === 'granted') {
          new Notification('Hello, world!');
        }
      });
    }

    // Canvas API
    const canvas = document.getElementById('myCanvas');
    const ctx = canvas.getContext('2d');
    ctx.fillStyle = 'green';
    ctx.fillRect(10, 10, 100, 100);
    ```

14. **Promise et Async/Await** :
    ```javascript
    // Utilisation des Promises
    const promise = new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve('Promise resolved');
      }, 1000);
    });

    promise.then(result => console.log(result)).catch(error => console.error(error));

    // Avec async/await
    async function asyncFunction() {
      try {
        const result = await promise;
        console.log(result); // 'Promise resolved'
      } catch (error) {
        console.error(error);
      }
    }
    asyncFunction();
    ```

15. **Service Workers** :
    ```javascript
    // Enregistrement d'un Service Worker
    if ('serviceWorker' in navigator) {
      navigator.serviceWorker.register('/service-worker.js')
        .then(registration => {
          console.log('Service Worker registered with scope:', registration.scope);
        })
        .catch(error => {
          console.error('Service Worker registration failed:', error);
        });
    }
    ```

Ces exemples couvrent une large gamme de fonctionnalités courantes en JavaScript.
