# Opdracht: Loops in JavaScript

## Doel
Leer hoe je loops gebruikt in JavaScript door eenvoudige programma's te schrijven die herhalende taken uitvoeren.

## Instructies
1. **Installeer een IDE:**
   - Download en installeer Visual Studio Code van deze link.

2. **Maak een nieuw JavaScript-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `loops.js`.

3. **Schrijf een `for` loop:**
   - Typ de volgende code in `loops.js`:
     ```javascript
     for (let i = 1; i <= 10; i++) {
       console.log(i);
     }
     ```

4. **Voer het programma uit:**
   - Open de terminal in Visual Studio Code (gebruik `Ctrl + `).
   - Typ `node loops.js` en druk op Enter.
   - Je zou de getallen 1 tot en met 10 in de terminal moeten zien.

## Uitleg
- **`for` loop:** Herhaalt een blok code een bepaald aantal keren. In dit geval wordt de code 10 keer uitgevoerd.

## Extra Oefening
1. **`while` loop:**
   - Voeg de volgende code toe aan `loops.js`:
     ```javascript
     let j = 10;
     while (j >= 1) {
       console.log(j);
       j--;
     }
     ```
   - Voer het programma opnieuw uit en bekijk het resultaat.

2. **Geneste loops:**
   - Voeg de volgende code toe aan `loops.js`:
     ```javascript
     for (let x = 1; x <= 5; x++) {
       for (let y = 1; y <= 5; y++) {
         console.log(`x: ${x}, y: ${y}`);
       }
     }
     ```
   - Voer het programma opnieuw uit en bekijk het resultaat.