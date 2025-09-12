# Opdracht: Conditionele Statements in JavaScript

## Doel
Leer hoe je conditionele statements gebruikt in JavaScript door een eenvoudig programma te schrijven dat verschillende condities controleert.

## Instructies
1. **Maak een nieuw JavaScript-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `conditions.js`.

2. **Schrijf je eerste conditionele statement:**
   - Typ de volgende code in `conditions.js`:
     ```javascript
     let age = 20;

     if (age >= 18) {
       console.log("Je bent een volwassene.");
     } else {
       console.log("Je bent een minderjarige.");
     }
     ```

3. **Voer het programma uit:**
   - Open de terminal in Visual Studio Code (gebruik `Ctrl + `).
   - Typ `node conditions.js` en druk op Enter.
   - Je zou de tekst "Je bent een volwassene." in de terminal moeten zien als `age` 18 of ouder is, anders "Je bent een minderjarige."

## Uitleg
- **`if` statement:** Controleert of een conditie waar is. Als dat zo is, wordt de code binnen het `if`-blok uitgevoerd.
- **`else` statement:** Wordt uitgevoerd als de conditie in het `if`-statement niet waar is.

## Extra Oefening
1. **Meerdere Condities:**
   - Voeg de volgende code toe aan `conditions.js`:
     ```javascript
     let score = 85;

     if (score >= 90) {
       console.log("Uitstekend!");
     } else if (score >= 75) {
       console.log("Goed gedaan!");
     } else if (score >= 50) {
       console.log("Voldoende.");
     } else {
       console.log("Onvoldoende.");
     }
     ```
   - Voer het programma opnieuw uit en bekijk het resultaat voor verschillende waarden van `score`.

2. **Geneste Conditionele Statements:**
   - Voeg de volgende code toe aan `conditions.js`:
     ```javascript
     let temperature = 30;

     if (temperature > 0) {
       if (temperature > 25) {
         console.log("Het is warm.");
       } else {
         console.log("Het is koel.");
       }
     } else {
       console.log("Het is koud.");
     }
     ```
   - Voer het programma opnieuw uit en bekijk het resultaat voor verschillende waarden van `temperature`.