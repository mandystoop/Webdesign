# Opdracht: JavaScript Verzamelingen (Arrays)

## Doel
Leer hoe je arrays gebruikt in JavaScript door een eenvoudig programma te schrijven dat verschillende array-methoden en operaties demonstreert.

## Instructies
1. **Maak een nieuw JavaScript-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `arrays.js`.

2. **Maak je eerste array:**
   - Typ de volgende code in `arrays.js`:
     ```javascript
     let cijfers = [10, 20, 30, 40, 50];
     console.log(cijfers);
     ```

3. **Voer het programma uit:**
   - Open de terminal in Visual Studio Code (gebruik `Ctrl + `).
   - Typ `node arrays.js` en druk op Enter.
   - Je zou de array `cijfers` in de terminal moeten zien.

## Uitleg
- **Array:** Een verzameling van elementen die toegankelijk zijn via een index.

## Extra Oefening
1. **Toegang tot Elementen:**
   - Voeg de volgende code toe aan `arrays.js`:
     ```javascript
     console.log(cijfers[0]); // Eerste element
     console.log(cijfers[2]); // Derde element
     console.log(cijfers[cijfers.length - 1]); // Laatste element
     ```

2. **Array-methoden:**
   - Voeg de volgende code toe aan `arrays.js`:
     ```javascript
     cijfers.push(60); // Element toevoegen aan het einde
     console.log(cijfers);

     cijfers.pop(); // Laatste element verwijderen
     console.log(cijfers);

     cijfers.shift(); // Eerste element verwijderen
     console.log(cijfers);

     cijfers.unshift(5); // Element toevoegen aan het begin
     console.log(cijfers);
     ```

3. **Itereren over Arrays:**
   - Voeg de volgende code toe aan `arrays.js`:
     ```javascript
     cijfers.forEach((cijfer) => {
       console.log(cijfer);
     });

     for (let i = 0; i < cijfers.length; i++) {
       console.log(cijfers[i]);
     }
     ```

4. **Array-methoden voor Transformatie:**
   - Voeg de volgende code toe aan `arrays.js`:
     ```javascript
     let verdubbeld = cijfers.map((cijfer) => cijfer * 2);
     console.log(verdubbeld);

     let gefilterd = cijfers.filter((cijfer) => cijfer > 20);
     console.log(gefilterd);

     let som = cijfers.reduce((totaal, cijfer) => totaal + cijfer, 0);
     console.log(som);
     ```

5. **Zoeken in Arrays:**
   - Voeg de volgende code toe aan `arrays.js`:
     ```javascript
     let index = cijfers.indexOf(30);
     console.log(index);

     let bevat = cijfers.includes(40);
     console.log(bevat);
     ```

6. **Sorteren en Omkeren:**
   - Voeg de volgende code toe aan `arrays.js`:
     ```javascript
     let gesorteerd = [...cijfers].sort((a, b) => a - b);
     console.log(gesorteerd);

     let omgekeerd = [...cijfers].reverse();
     console.log(omgekeerd);
     ```