# Opdracht: Asynchroniteit in JavaScript

## Doel
Leer hoe je asynchrone operaties beheert in JavaScript door een eenvoudig programma te schrijven dat gebruik maakt van `setTimeout`, `Promises` en `async/await`.

## Instructies
1. **Maak een nieuw JavaScript-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `async.js`.

2. **Gebruik `setTimeout`:**
   - Typ de volgende code in `async.js`:
     ```javascript
     console.log("Start");

     setTimeout(() => {
       console.log("Dit bericht verschijnt na 2 seconden.");
     }, 2000);

     console.log("Einde");
     ```

3. **Voer het programma uit:**
   - Open de terminal in Visual Studio Code (gebruik `Ctrl + `).
   - Typ `node async.js` en druk op Enter.
   - Je zou de berichten "Start", "Einde" en vervolgens "Dit bericht verschijnt na 2 seconden." in de terminal moeten zien.

## Uitleg
- **`setTimeout`:** Een functie die een andere functie uitvoert na een bepaalde tijd (in milliseconden).

## Verder met asynchroniteit
1. **Gebruik van Promises:**
   - Voeg de volgende code toe aan `async.js`:
     ```javascript
     let belofte = new Promise((resolve, reject) => {
       let succes = true;

       setTimeout(() => {
         if (succes) {
           resolve("De operatie was succesvol!");
         } else {
           reject("Er is iets misgegaan.");
         }
       }, 2000);
     });

     belofte
       .then((boodschap) => {
         console.log(boodschap);
       })
       .catch((fout) => {
         console.log(fout);
       });
     ```

2. **Gebruik van `async` en `await`:**
   - Voeg de volgende code toe aan `async.js`:
     ```javascript
     async function asyncFunctie() {
       try {
         let resultaat = await belofte;
         console.log(resultaat);
       } catch (fout) {
         console.log(fout);
       }
     }

     asyncFunctie();
     ```

3. **Asynchrone Functie met `fetch`:**
   - Voeg de volgende code toe aan `async.js`:
     ```javascript
     async function fetchData() {
       try {
         let response = await fetch('https://jsonplaceholder.typicode.com/posts/1');
         let data = await response.json();
         console.log(data);
       } catch (error) {
         console.log("Er is een fout opgetreden:", error);
       }
     }

     fetchData();
     ```

4. **Chaining van Asynchrone Operaties:**
   - Voeg de volgende code toe aan `async.js`:
     ```javascript
     async function fetchAndProcessData() {
       try {
         let response = await fetch('https://jsonplaceholder.typicode.com/posts');
         let data = await response.json();

         let firstPost = data[0];
         console.log("Eerste post:", firstPost);

         let userResponse = await fetch(`https://jsonplaceholder.typicode.com/users/${firstPost.userId}`);
         let userData = await userResponse.json();
         console.log("Gebruiker van de eerste post:", userData);
       } catch (error) {
         console.log("Er is een fout opgetreden:", error);
       }
     }

     fetchAndProcessData();
     ```