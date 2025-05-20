# Opdracht: Opzetten van een MySQL Database met XAMPP en PHPMyAdmin

## Doel
Leer hoe je een eenvoudige database opzet met MySQL en PHPMyAdmin, en hoe je met behulp van JavaScript data kunt creëren, lezen, updaten en verwijderen (CRUD).

## Instructies

1. **Installeer XAMPP:**
   - Download en installeer XAMPP: https://www.apachefriends.org/download.html
   - Start de Apache en MySQL modules via het XAMPP Control Panel.

2. **Maak een database aan met PHPMyAdmin:**
   - Open PHPMyAdmin door naar `http://localhost/phpmyadmin` te gaan in je webbrowser.
   - Maak een nieuwe database aan genaamd `studenten_db`.
   - Maak een tabel aan genaamd `studenten` met de volgende kolommen:
     - `id` (INT, AUTO_INCREMENT, PRIMARY KEY)
     - `naam` (VARCHAR(100))
     - `leeftijd` (INT)
     - `email` (VARCHAR(100))

3. **Maak een HTML-bestand aan:**
   - Maak een nieuw HTML-bestand aan genaamd `index.html` en voeg de volgende code toe:
     ```html
     <!DOCTYPE html>
     <html lang="en">
     <head>
         <meta charset="UTF-8">
         <meta name="viewport" content="width=device-width, initial-scale=1.0">
         <title>Studenten Database</title>
     </head>
     <body>
         <h1>Studenten Database</h1>
         <form id="studentForm">
             <input type="text" id="naam" placeholder="Naam" required>
             <input type="number" id="leeftijd" placeholder="Leeftijd" required>
             <input type="email" id="email" placeholder="Email" required>
             <button type="submit">Toevoegen</button>
         </form>
         <div id="studentenLijst"></div>
         <script src="script.js"></script>
     </body>
     </html>
     ```

4. **Maak een JavaScript-bestand aan:**
   - Maak een nieuw JavaScript-bestand aan genaamd `script.js` en voeg de volgende code toe:
     ```javascript
     document.getElementById('studentForm').addEventListener('submit', function(e) {
         e.preventDefault();
         const naam = document.getElementById('naam').value;
         const leeftijd = document.getElementById('leeftijd').value;
         const email = document.getElementById('email').value;

         fetch('http://localhost:3000/studenten', {
             method: 'POST',
             headers: {
                 'Content-Type': 'application/json'
             },
             body: JSON.stringify({ naam, leeftijd, email })
         })
         .then(response => response.json())
         .then(data => {
             if (data.success) {
                 alert('Student toegevoegd!');
                 // Voeg code toe om de lijst bij te werken
             } else {
                 alert('Er is iets misgegaan.');
             }
         });
     });

     // Functie om studenten op te halen
     function fetchStudenten() {
         fetch('http://localhost:3000/studenten')
         .then(response => response.json())
         .then(data => {
             const studentenLijst = document.getElementById('studentenLijst');
             studentenLijst.innerHTML = '';
             data.forEach(student => {
                 const studentDiv = document.createElement('div');
                 studentDiv.textContent = `${student.naam} - ${student.leeftijd} - ${student.email}`;
                 studentenLijst.appendChild(studentDiv);
             });
         });
     }

     // Functie om een student te updaten
     function updateStudent(id, naam, leeftijd, email) {
         fetch(`http://localhost:3000/studenten/${id}`, {
             method: 'PUT',
             headers: {
                 'Content-Type': 'application/json'
             },
             body: JSON.stringify({ naam, leeftijd, email })
         })
         .then(response => response.json())
         .then(data => {
             if (data.success) {
                 alert('Student bijgewerkt!');
                 fetchStudenten();
             } else {
                 alert('Er is iets misgegaan.');
             }
         });
     }

     // Functie om een student te verwijderen
     function deleteStudent(id) {
         fetch(`http://localhost:3000/studenten/${id}`, {
             method: 'DELETE'
         })
         .then(response => response.json())
         .then(data => {
             if (data.success) {
                 alert('Student verwijderd!');
                 fetchStudenten();
             } else {
                 alert('Er is iets misgegaan.');
             }
         });
     }

     // Initialiseer de lijst met studenten
     fetchStudenten();
     ```

5. **Maak een JSON-server aan:**
   - Installeer de JSON-server door het volgende commando in je terminal uit te voeren:
     ```bash
     npm install -g json-server
     ```
   - Maak een nieuw bestand aan genaamd `db.json` en voeg de volgende code toe:
     ```json
     {
       "studenten": []
     }
     ```
   - Start de JSON-server door het volgende commando in je terminal uit te voeren:
     ```bash
     json-server --watch db.json --port 3000
     ```

## Uitleg
- **MySQL**: Een relationeel databasebeheersysteem dat wordt gebruikt om data op te slaan en te beheren.
- **PHPMyAdmin**: Een gratis tool waarmee je MySQL-databases kunt beheren via een webinterface.
- **JavaScript**: Een programmeertaal die wordt gebruikt om interactieve elementen op webpagina's te maken.
- **CRUD**: Standaardoperaties voor het maken, lezen, updaten en verwijderen van data in een database.

## Extra Oefening

1. **Lees data uit de database:**
   - Voeg code toe aan `script.js` om alle studenten uit de database op te halen en weer te geven in de HTML-pagina.
```javascript
// Voeg deze code toe onderaan je script.js bestand om studenten weer te geven
function fetchStudenten() {
    fetch('http://localhost:3000/studenten')
    .then(response => response.json())
    .then(data => {
        const studentenLijst = document.getElementById('studentenLijst');
        studentenLijst.innerHTML = '';
        data.forEach(student => {
            const studentDiv = document.createElement('div');
            studentDiv.textContent = `${student.naam} - ${student.leeftijd} - ${student.email}`;
            studentenLijst.appendChild(studentDiv);
        });
    });
}

// Roep de functie aan om de studenten direct te tonen bij het laden van de pagina
fetchStudenten();
```

2. **Update data in de database:**
   - Voeg een functie toe om de gegevens van een student te updaten.

3. **Verwijder data uit de database:**
   - Voeg een functie toe om een student uit de database te verwijderen.