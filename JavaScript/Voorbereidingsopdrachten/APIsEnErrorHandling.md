# Opdracht: Error Handling en API-gebruik in JavaScript

## Doel
Leer hoe je API's gebruikt en fouten afhandelt in JavaScript door een eenvoudig programma te schrijven dat gegevens ophaalt van een API en robuuste foutafhandeling implementeert.

## Instructies
1. **Maak een nieuw JavaScript-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `api_error_handling.js`.

2. **Basis API-aanroep:**
   - Typ de volgende code in `api_error_handling.js`:
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

3. **Voer het programma uit:**
   - Open de terminal in Visual Studio Code (gebruik `Ctrl + `).
   - Typ `node api_error_handling.js` en druk op Enter.
   - Je zou de gegevens van de eerste post moeten zien in de terminal.

## Uitleg
- **`fetch`:** Een functie die een netwerkverzoek doet en een Promise retourneert.
- **`try...catch`:** Een blok dat wordt gebruikt om fouten af te handelen. De code in het `try`-blok wordt uitgevoerd en als er een fout optreedt, wordt de code in het `catch`-blok uitgevoerd.

## Extra Oefening
1. **Controleer de Netwerkrespons:**
   - Voeg de volgende code toe aan `api_error_handling.js`:
     ```javascript
     async function fetchDataWithCheck() {
       try {
         let response = await fetch('https://jsonplaceholder.typicode.com/posts/1');
         if (!response.ok) {
           throw new Error('Netwerkrespons was niet ok');
         }
         let data = await response.json();
         console.log(data);
       } catch (error) {
         console.log("Er is een fout opgetreden:", error);
       }
     }

     fetchDataWithCheck();
     ```

2. **Gebruik van een Onjuiste URL:**
   - Voeg de volgende code toe aan `api_error_handling.js`:
     ```javascript
     async function fetchInvalidUrl() {
       try {
         let response = await fetch('https://jsonplaceholder.typicode.com/invalid-url');
         if (!response.ok) {
           throw new Error('Netwerkrespons was niet ok');
         }
         let data = await response.json();
         console.log(data);
       } catch (error) {
         console.log("Er is een fout opgetreden:", error);
       }
     }

     fetchInvalidUrl();
     ```

3. **Herstel van Fouten:**
   - Voeg de volgende code toe aan `api_error_handling.js`:
     ```javascript
     async function fetchWithRecovery() {
       try {
         let response = await fetch('https://jsonplaceholder.typicode.com/invalid-url');
         if (!response.ok) {
           throw new Error('Netwerkrespons was niet ok');
         }
         let data = await response.json();
         console.log(data);
       } catch (error) {
         console.log("Er is een fout opgetreden:", error);
         console.log("Probeer opnieuw met een geldige URL...");

         // Herstelactie
         try {
           let response = await fetch('https://jsonplaceholder.typicode.com/posts/1');
           let data = await response.json();
           console.log("Hersteldata:", data);
         } catch (recoveryError) {
           console.log("Herstelactie is mislukt:", recoveryError);
         }
       }
     }

     fetchWithRecovery();
     ```

4. **Gebruik van een API met Parameters:**
   - Voeg de volgende code toe aan `api_error_handling.js`:
     ```javascript
     async function fetchWithParams(userId) {
       try {
         let response = await fetch(`https://jsonplaceholder.typicode.com/posts?userId=${userId}`);
         if (!response.ok) {
           throw new Error('Netwerkrespons was niet ok');
         }
         let data = await response.json();
         console.log(data);
       } catch (error) {
         console.log("Er is een fout opgetreden:", error);
       }
     }

     fetchWithParams(1);
     ```
