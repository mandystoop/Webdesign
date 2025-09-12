# Opdracht: Objecten in JavaScript

## Doel
Leer hoe je objecten gebruikt in JavaScript door een eenvoudig programma te schrijven dat objecten aanmaakt en ermee werkt.

## Instructies
1. **Maak een nieuw JavaScript-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `objects.js`.

2. **Maak je eerste object:**
   - Typ de volgende code in `objects.js`:
     ```javascript
     let persoon = {
       naam: "John",
       leeftijd: 30,
       beroep: "Programmeur"
     };

     console.log(persoon);
     ```

3. **Voer het programma uit:**
   - Open de terminal in Visual Studio Code (gebruik `Ctrl + `).
   - Typ `node objects.js` en druk op Enter.
   - Je zou het object `persoon` in de terminal moeten zien met de eigenschappen `naam`, `leeftijd`, en `beroep`.

## Uitleg
- **Object:** Een verzameling van eigenschappen, waarbij elke eigenschap een naam (key) en een waarde heeft.
- **Eigenschap:** Een variabele die deel uitmaakt van een object.

## Extra Oefening
1. **Toegang tot Eigenschappen:**
   - Voeg de volgende code toe aan `objects.js`:
     ```javascript
     console.log(persoon.naam); // Toegang via puntnotatie
     console.log(persoon["leeftijd"]); // Toegang via bracketnotatie
     ```

2. **Eigenschappen Toevoegen en Wijzigen:**
   - Voeg de volgende code toe aan `objects.js`:
     ```javascript
     persoon.woonplaats = "Amsterdam"; // Eigenschap toevoegen
     persoon.leeftijd = 31; // Eigenschap wijzigen

     console.log(persoon);
     ```

3. **Methoden in Objecten:**
   - Voeg de volgende code toe aan `objects.js`:
     ```javascript
     persoon.groet = function() {
       console.log("Hallo, mijn naam is " + this.naam);
     };

     persoon.groet(); // Methode aanroepen
     ```

4. **Geneste Objecten:**
   - Voeg de volgende code toe aan `objects.js`:
     ```javascript
     let bedrijf = {
       naam: "Tech Solutions",
       adres: {
         straat: "Hoofdstraat",
         nummer: 123,
         stad: "Utrecht"
       }
     };

     console.log(bedrijf);
     console.log(bedrijf.adres.straat); // Toegang tot geneste eigenschap
     ```
