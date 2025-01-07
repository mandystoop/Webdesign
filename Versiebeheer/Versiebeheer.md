# Opdracht: Oefenen met Git en GitHub

## Doel
Leer de basisprincipes van Git en GitHub door een eenvoudig project te maken, wijzigingen bij te houden, en deze naar een GitHub-repository te pushen. Oefen ook met het oplossen van merge conflicts.

## Instructies

1. **Installeer Git:**
   - Download en installeer Git vanaf git-scm.com.

2. **Maak een nieuw project:**
   - Open Visual Studio Code.
   - Maak een nieuwe map aan voor je project en open deze in Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `index.js`.

3. **Schrijf een eenvoudig JavaScript-programma:**
   - Typ de volgende code in `index.js`:
     ```javascript
     console.log("Hallo, wereld!");
     ```

4. **Initialiseer een Git-repository:**
   - Open de terminal in Visual Studio Code (gebruik `Ctrl + `).
   - Typ de volgende commando's:
     ```bash
     git init
     git add index.js
     git commit -m "Eerste commit"
     ```

5. **Maak een nieuwe repository op GitHub:**
   - Ga naar GitHub en log in.
   - Klik op de knop "New" om een nieuwe repository aan te maken.
   - Geef de repository een naam (bijv. `oefenproject`) en klik op "Create repository".

6. **Verbind de lokale repository met GitHub:**
   - Kopieer de URL van de nieuwe GitHub-repository.
   - Typ de volgende commando's in de terminal van Visual Studio Code:
     ```bash
     git remote add origin <URL>
     git branch -M main
     git push -u origin main
     ```

7. **Wijzig het JavaScript-programma:**
   - Voeg de volgende code toe aan `index.js`:
     ```javascript
     function begroet(naam) {
       console.log("Hallo, " + naam + "!");
     }

     begroet("student");
     ```

8. **Commit en push de wijzigingen:**
   - Typ de volgende commando's in de terminal:
     ```bash
     git add index.js
     git commit -m "Voeg begroet functie toe"
     git push
     ```

## Uitleg
- **`git init`**: Initialiseert een nieuwe Git-repository.
- **`git add`**: Voegt bestanden toe aan de staging area.
- **`git commit`**: Maakt een snapshot van de huidige bestanden in de repository.
- **`git remote add origin`**: Verbindt de lokale repository met een externe repository op GitHub.
- **`git push`**: Stuurt de commits naar de externe repository.

## Extra Oefening

1. **Maak een nieuwe branch:**
   - Typ de volgende commando's in de terminal:
     ```bash
     git checkout -b nieuwe-feature
     ```

2. **Wijzig het JavaScript-programma op de nieuwe branch:**
   - Voeg de volgende code toe aan `index.js`:
     ```javascript
     function afscheid(naam) {
       console.log("Tot ziens, " + naam + "!");
     }

     afscheid("student");
     ```

3. **Commit en push de wijzigingen op de nieuwe branch:**
   - Typ de volgende commando's in de terminal:
     ```bash
     git add index.js
     git commit -m "Voeg afscheid functie toe"
     git push --set-upstream origin nieuwe-feature
     ```

4. **Maak een pull request op GitHub:**
   - Ga naar de repository op GitHub.
   - Klik op de knop "Compare & pull request" en volg de instructies om de wijzigingen samen te voegen.

5. **Oefen met een merge conflict:**
   - Ga terug naar de `main` branch:
     ```bash
     git checkout main
     ```

   - Wijzig het JavaScript-programma op de `main` branch:
     ```javascript
     function begroet(naam) {
       console.log("Hallo, " + naam + "! Welkom terug.");
     }

     begroet("student");
     ```

   - Commit en push de wijzigingen:
     ```bash
     git add index.js
     git commit -m "Wijzig begroet functie"
     git push
     ```

   - Ga terug naar de `nieuwe-feature` branch:
     ```bash
     git checkout nieuwe-feature
     ```

   - Probeer de `main` branch te mergen in `nieuwe-feature`:
     ```bash
     git merge main
     ```

   - Er zal een merge conflict optreden. Open `index.js` in Visual Studio Code en los het conflict op door de code te combineren:
     ```javascript
     function begroet(naam) {
       console.log("Hallo, " + naam + "! Welkom terug.");
     }

     function afscheid(naam) {
       console.log("Tot ziens, " + naam + "!");
     }

     begroet("student");
     afscheid("student");
     ```

   - Voeg de opgeloste bestanden toe en commit de wijzigingen:
     ```bash
     git add index.js
     git commit -m "Los merge conflict op"
     git push
     ```