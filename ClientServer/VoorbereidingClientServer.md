# Opdracht: Client-Server Architecturen

## Doel
Leer de basisprincipes van client-server architecturen en hoe ze worden toegepast in verschillende scenario's. Deze opdrachten helpen je om inzicht te krijgen in de werking van client-server modellen en hoe je ze kunt implementeren met behulp van JavaScript.

## Instructies

### Theoretische Voorbereiding
1. **Lees de volgende artikelen om bekend te raken met de theorie achter client-server architecturen:**
   - Client-Server Model (https://nl.wikipedia.org/wiki/Client-servermodel)
   - How the Web Works (https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Web_standards/How_the_web_works)
   - Client-Server Architecture (https://medium.com/nerd-for-tech/client-server-architecture-explained-with-examples-diagrams-and-real-world-applications-407e9e04e2d1)

2. **Schrijf een korte pitch (maximaal 300 woorden) van wat je hebt geleerd over client-server architecturen:**
    - Houd voor jezelf als doel dat je dit aan iemand zou kunnen uitleggen. 
    - Schets  een plaatje voor jezelf van deze architectuuraanpak.

### Praktische Opdrachten
1. **Maak een nieuw JavaScript-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `client_server.js`.

2. **Basis Client-Server Model:**
   - Typ de volgende code in `client_server.js` om een eenvoudige server te maken met Node.js:
     ```javascript
     const http = require('http');

     const server = http.createServer((req, res) => {
       res.statusCode = 200;
       res.setHeader('Content-Type', 'text/plain');
       res.end('Hello, World!\n');
     });

     server.listen(3000, '127.0.0.1', () => {
       console.log('Server running at http://127.0.0.1:3000/');
     });
     ```

3. **Voer de server uit:**
   - Open de terminal in Visual Studio Code (gebruik `Ctrl + `).
   - Typ `node client_server.js` en druk op Enter.
   - Open een webbrowser en ga naar `http://127.0.0.1:3000/` om de boodschap "Hello, World!" te zien.

## Uitleg
- **`http`:** Een ingebouwd Node.js-module om HTTP-servers te maken.
- **`createServer`:** Een methode om een nieuwe HTTP-server te maken.
- **`listen`:** Een methode om de server te laten luisteren op een specifieke poort en host.

## Extra Oefening
1. **Client Verzoek:**
   - Voeg de volgende code toe aan `client_server.js` om een client-verzoek te maken:
     ```javascript
     const http = require('http');

     const options = {
       hostname: '127.0.0.1',
       port: 3000,
       path: '/',
       method: 'GET'
     };

     const req = http.request(options, (res) => {
       let data = '';

       res.on('data', (chunk) => {
         data += chunk;
       });

       res.on('end', () => {
         console.log(data);
       });
     });

     req.on('error', (e) => {
       console.error(`Er is een fout opgetreden: ${e.message}`);
     });

     req.end();
     ```

2. **JSON Response:**
   - Pas de servercode aan om een JSON-response te sturen:
     ```javascript
     const http = require('http');

     const server = http.createServer((req, res) => {
       res.statusCode = 200;
       res.setHeader('Content-Type', 'application/json');
       res.end(JSON.stringify({ message: 'Hello, World!' }));
     });

     server.listen(3000, '127.0.0.1', () => {
       console.log('Server running at http://127.0.0.1:3000/');
     });
     ```

3. **Client Verzoek met JSON:**
   - Pas de clientcode aan om de JSON-response te verwerken:
     ```javascript
     const http = require('http');

     const options = {
       hostname: '127.0.0.1',
       port: 3000,
       path: '/',
       method: 'GET'
     };

     const req = http.request(options, (res) => {
       let data = '';

       res.on('data', (chunk) => {
         data += chunk;
       });

       res.on('end', () => {
         console.log(JSON.parse(data));
       });
     });

     req.on('error', (e) => {
       console.error(`Er is een fout opgetreden: ${e.message}`);
     });

     req.end();
     ```

4. **Client-Server Interactie:**
   - Voeg een eenvoudige HTML-pagina toe die een verzoek naar de server stuurt en de response weergeeft:
     ```html
     <!DOCTYPE html>
     <html>
     <head>
       <title>Client-Server Interactie</title>
     </head>
     <body>
       <h1>Client-Server Interactie</h1>
       <button id="fetchData">Fetch Data</button>
       <pre id="responseData"></pre>

       <script>
         document.getElementById('fetchData').addEventListener('click', () => {
           fetch('http://127.0.0.1:3000/')
             .then(response => response.json())
             .then(data => {
               document.getElementById('responseData').textContent = JSON.stringify(data, null, 2);
             })
             .catch(error => console.error('Er is een fout opgetreden:', error));
         });
       </script>
     </body>
     </html>
     ```

Veel succes met de opdrachten! Als je nog vragen hebt, laat het me weten.