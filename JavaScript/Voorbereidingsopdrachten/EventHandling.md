# Opdracht: Interactieve Quiz

## Doel
Leer hoe je event handling gebruikt in JavaScript door een interactieve quiz te maken waarbij gebruikers vragen kunnen beantwoorden en feedback krijgen.

## Instructies
1. **Maak een nieuw HTML-bestand:**
   - Open Visual Studio Code.
   - Maak een nieuw bestand aan en sla het op als `quiz.html`.

2. **Schrijf de HTML-structuur:**
   - Typ de volgende code in `quiz.html`:
   ````html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Interactie Quiz</title>
   </head>
   <body>
       <h1>Quiz</h1>
       <div id="quizContainer">
           <p>Wat is de hoofdstad van Nederland?</p>
           <button class="answerButton">Amsterdam</button>
           <button class="answerButton">Rotterdam</button>
           <button class="answerButton">Den Haag</button>
           <button class="answerButton">Utrecht</button>
       </div>
       <p id="feedback"></p>
   </body>
   </html>
   `````

3. **Voeg JavaScript-functionaliteit toe:**
   - Voeg de volgende code toe aan `quiz.html` onderaan de `<body>` sectie:
     ```html
     <script>
         const correctAnswer = "Amsterdam";
         const buttons = document.querySelectorAll('.answerButton');
         const feedback = document.getElementById('feedback');

         buttons.forEach(button => {
             button.addEventListener('click', function() {
                 if (button.textContent === correctAnswer) {
                     feedback.textContent = "Correct!";
                     feedback.style.color = "green";
                 } else {
                     feedback.textContent = "Fout, probeer het opnieuw.";
                     feedback.style.color = "red";
                 }
             });
         });
     </script>
     ```

4. **Open het bestand in een browser:**
   - Open `quiz.html` in een webbrowser om de interactieve quiz te zien en te testen.

## Uitleg
- **Event Handling:** Het proces waarbij JavaScript reageert op gebruikersacties zoals klikken, invoeren van tekst, etc.
- **Event Listeners:** Functies die wachten op een specifieke gebeurtenis (zoals een klik) en dan een actie uitvoeren.

## Extra Oefening
1. **Voeg meer vragen toe:**
   - Breid de quiz uit met meerdere vragen en geef feedback voor elke vraag.

2. **Houd de score bij:**
   - Voeg functionaliteit toe om de score van de gebruiker bij te houden en weer te geven aan het einde van de quiz.

3. **Voeg een timer toe:**
   - Voeg een timer toe die bijhoudt hoe lang de gebruiker over de quiz doet en geef deze tijd weer aan het einde.

4. **Voeg een voortgangsbalk toe:**
   - Voeg een voortgangsbalk toe die laat zien hoeveel vragen de gebruiker al heeft beantwoord en hoeveel er nog over zijn.
