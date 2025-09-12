# Opdracht: Functies in JavaScript

## Doel
Leer hoe je functies gebruikt in JavaScript door eenvoudige programma's te schrijven die herbruikbare codeblokken definiëren en aanroepen.

## Instructies
1. **Maak een nieuw JavaScript-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `functions.js`.

2. **Schrijf een eenvoudige functie:**
   - Typ de volgende code in `functions.js`:
     ```javascript
     function greet(name) {
       console.log("Hello, " + name + "!");
     }

     greet("Student");
     ```

3. **Voer het programma uit:**
   - Open de terminal in Visual Studio Code (gebruik `Ctrl + `).
   - Typ `node functions.js` en druk op Enter.
   - Je zou de tekst "Hello, Student!" in de terminal moeten zien.

## Uitleg
- **Functie:** Een blok code dat kan worden hergebruikt. Functies worden gedefinieerd met het `function` keyword en aangeroepen door hun naam te gebruiken.

## Extra Oefening
1. **Functie met meerdere parameters:**
   - Voeg de volgende code toe aan `functions.js`:
     ```javascript
     function add(a, b) {
       return a + b;
     }

     console.log(add(5, 10));
     ```
   - Voer het programma opnieuw uit en bekijk het resultaat.

2. **Functie die een andere functie aanroept:**
   - Voeg de volgende code toe aan `functions.js`:
     ```javascript
     function multiply(a, b) {
       return a * b;
     }

     function square(n) {
       return multiply(n, n);
     }

     console.log(square(5));
     ```

     