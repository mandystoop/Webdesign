# Voorbereidende Opdrachten: Web Security

## Doel
Deze opdrachten helpen studenten om bekend te raken met verschillende aspecten van web security door hands-on oefeningen in JavaScript. Studenten zullen leren over input validatie, injection attacks, encryptie, en authenticatie en autorisatie.

## Opdracht 1: Input Validatie

### Doel
Leer hoe je gebruikersinvoer valideert om kwaadaardige gegevens te voorkomen.

### Instructies
1. **Maak een nieuw JavaScript-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `input_validation.js`.

2. **Schrijf een functie voor input validatie:**
   - Voeg de volgende code toe aan `input_validation.js`:
     ```javascript
     function validateInput(input) {
       const regex = /^[a-zA-Z0-9]+$/;
       return regex.test(input);
     }

     // Test de functie
     console.log(validateInput("ValidInput123")); // true
     console.log(validateInput("Invalid Input!")); // false
     ```

3. **Voer het programma uit:**
   - Open de terminal in Visual Studio Code.
   - Typ `node input_validation.js` en druk op Enter.
   - Controleer de output om te zien of de invoer correct wordt gevalideerd.

4. **Uitbreiding:**
   - Voeg extra validatie toe voor e-mailadressen en telefoonnummers.
     ```javascript
     function validateEmail(email) {
       const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
       return emailRegex.test(email);
     }

     function validatePhoneNumber(phone) {
       const phoneRegex = /^\d{10}$/;
       return phoneRegex.test(phone);
     }

     // Test de functies
     console.log(validateEmail("test@example.com")); // true
     console.log(validateEmail("invalid-email")); // false
     console.log(validatePhoneNumber("1234567890")); // true
     console.log(validatePhoneNumber("123-456-7890")); // false
     ```

5. **Real-World Scenario:**
   - Beschrijf een scenario waarin slechte input validatie leidt tot een beveiligingslek. Laat studenten nadenken over de gevolgen en hoe ze dit kunnen voorkomen.

## Opdracht 2: Injection Attacks

### Doel
Leer over SQL injection en hoe je het kunt voorkomen.

### Instructies
1. **Maak een nieuw JavaScript-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `sql_injection_example.js`.

2. **Schrijf een voorbeeld van een SQL injection aanval:**
   - Voeg de volgende code toe aan `sql_injection_example.js`:
     ```javascript
     const userInput = "'; DROP TABLE users; --";
     const query = `SELECT * FROM users WHERE username = '${userInput}'`;

     console.log("SQL Query:", query);
     ```

3. **Voer het programma uit:**
   - Open de terminal in Visual Studio Code.
   - Typ `node sql_injection_example.js` en druk op Enter.
   - Bekijk de gegenereerde SQL-query en begrijp hoe de injectie werkt.

4. **Voorkom SQL injection:**
   - Voeg de volgende code toe aan `sql_injection_example.js`:
     ```javascript
     const safeUserInput = userInput.replace(/'/g, "''");
     const safeQuery = `SELECT * FROM users WHERE username = '${safeUserInput}'`;

     console.log("Veilige SQL Query:", safeQuery);
     ```

## Opdracht 3: Simpele Encryptie

### Doel
Leer hoe je gegevens kunt versleutelen en ontsleutelen.

### Instructies
1. **Maak een nieuw JavaScript-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `encryption_example.js`.

2. **Schrijf een functie voor eenvoudige encryptie en decryptie:**
   - Voeg de volgende code toe aan `encryption_example.js`:
     ```javascript
     const crypto = require('crypto');

     const algorithm = 'aes-256-cbc';
     const key = crypto.randomBytes(32);
     const iv = crypto.randomBytes(16);

     function encrypt(text) {
       const cipher = crypto.createCipheriv(algorithm, Buffer.from(key), iv);
       let encrypted = cipher.update(text);
       encrypted = Buffer.concat([encrypted, cipher.final()]);
       return iv.toString('hex') + ':' + encrypted.toString('hex');
     }

     function decrypt(text) {
       const textParts = text.split(':');
       const iv = Buffer.from(textParts.shift(), 'hex');
       const encryptedText = Buffer.from(textParts.join(':'), 'hex');
       const decipher = crypto.createDecipheriv(algorithm, Buffer.from(key), iv);
       let decrypted = decipher.update(encryptedText);
       decrypted = Buffer.concat([decrypted, decipher.final()]);
       return decrypted.toString();
     }

     // Test de functies
     const text = "Hello, World!";
     const encryptedText = encrypt(text);
     console.log("Encrypted:", encryptedText);
     console.log("Decrypted:", decrypt(encryptedText));
     ```

3. **Voer het programma uit:**
   - Open de terminal in Visual Studio Code.
   - Typ `node encryption_example.js` en druk op Enter.
   - Bekijk de output om te zien hoe de gegevens worden versleuteld en ontsleuteld.

## Opdracht 4: Authenticatie en Autorisatie

### Doel
Leer hoe je een eenvoudige authenticatie en autorisatie kunt implementeren voor een webapplicatie.

### Instructies
1. **Maak een nieuw project:**
   - Open Visual Studio Code.
   - Maak een nieuw project aan en sla het op als `auth_project`.

2. **Installeer benodigde pakketten:**
   - Open de terminal in Visual Studio Code.
   - Typ `npm init -y` en druk op Enter.
   - Typ `npm install express bcryptjs jsonwebtoken` en druk op Enter.

3. **Schrijf de servercode:**
   - Maak een nieuw bestand aan en sla het op als `server.js`.
   - Voeg de volgende code toe aan `server.js`:
     ```javascript
     const express = require('express');
     const bcrypt = require('bcryptjs');
     const jwt = require('jsonwebtoken');

     const app = express();
     app.use(express.json());

     const users = [];

     app.post('/register', async (req, res) => {
       const { username, password } = req.body;
       const hashedPassword = await bcrypt.hash(password, 10);
       users.push({ username, password: hashedPassword });
       res.status(201).send('User registered');
     });

     app.post('/login', async (req, res) => {
       const { username, password } = req.body;
       const user = users.find(u => u.username === username);
       if (user && await bcrypt.compare(password, user.password)) {
         const token = jwt.sign({ username: user.username }, 'secretkey');
         res.json({ token });
       } else {
         res.status(401).send('Invalid credentials');
       }
     });

     app.get('/protected', (req, res) => {
       const token = req.headers['authorization'];
       if (token) {
         jwt.verify(token, 'secretkey', (err, user) => {
           if (err) {
             return res.status(403).send('Invalid token');
           }
           res.send('Protected content');
         });
       } else {
         res.status(401).send('No token provided');
       }
     });

     app.listen(3000, () => {
       console.log('Server running on port 3000');
     });
     ```

4. **Test de server:**
   - Open de terminal in Visual Studio Code.
   - Typ `node server.js` en druk op Enter.
   - Gebruik een tool zoals Postman om de `/register`, `/login`, en `/protected` endpoints te testen.

## Opdracht 5: OWASP Top 10

### Doel
Leer over de OWASP Top 10 beveiligingsrisico's en hoe je deze kunt mitigeren.

### Instructies
1. **Lees over de OWASP Top 10:**
   - Bezoek de [OWASP Top 10](https://owasp.org/www-project-top-ten/) website en bestudeer de tien meest kritieke beveiligingsrisico's voor webapplicaties(https://owasp.org/www-project-top-ten/).

2. **Schrijf een samenvatting:**
   - Schrijf een samenvatting van elk van de OWASP Top 10 risico's om ermee bekend te raken.

3. **Injection Attack Voorbeeld:**
   - Voeg een voorbeeld van een injection attack toe aan je samenvatting, inclusief hoe je deze kunt voorkomen.