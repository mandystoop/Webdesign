# Introductieopdrachten: React

## Doel
Deze opdrachten helpen studenten om bekend te raken met de basisprincipes van React, inclusief componenten, JSX, hooks, en het maken van API-aanroepen met Axios. Studenten zullen leren hoe ze eenvoudige React-applicaties kunnen bouwen en beheren.

## Opdracht 1: Basiscomponenten en JSX

### Doel
Leer hoe je eenvoudige React-componenten maakt en JSX gebruikt om elementen te renderen.

### Instructies
1. **Maak een nieuw React-project:**
   - Open de terminal in Visual Studio Code.
   - Typ `npx create-react-app my-react-app` en druk op Enter.
   - Navigeer naar de projectmap met `cd my-react-app`.

2. **Maak een eenvoudige component:**
   - Open het bestand `src/App.js` in Visual Studio Code.
   - Voeg de volgende code toe om een eenvoudige React-component te maken:
     ```javascript
     import React from 'react';

     function Welcome(props) {
       return <h1>Hello, {props.name}</h1>;
     }

     function App() {
       return (
         <div>
           <Welcome name="Student" />
         </div>
       );
     }

     export default App;
     ```

3. **Voer de applicatie uit:**
   - Typ `npm start` in de terminal en druk op Enter.
   - Open je webbrowser en ga naar `http://localhost:3000` om je wijzigingen te zien.

## Opdracht 2: State en Props

### Doel
Leer hoe je state en props gebruikt om gegevens in je componenten te beheren.

### Instructies
1. **Maak een stateful component:**
   - Open het bestand `src/App.js` in Visual Studio Code.
   - Voeg de volgende code toe om een component met state te maken:
     ```javascript
     import React, { useState } from 'react';

     function Counter() {
       const [count, setCount] = useState(0);

       return (
         <div>
           <p>You clicked {count} times</p>
           <button onClick={() => setCount(count + 1)}>
             Click me
           </button>
         </div>
       );
     }

     function App() {
       return (
         <div>
           <Counter />
        >
       );
     }

     export default App;
     ```

2. **Voer de applicatie uit:**
   - Zorg ervoor dat de ontwikkelserver nog steeds draait.
   - Open je webbrowser en ga naar `http://localhost:3000` om je wijzigingen te zien.

## Opdracht 3: Gebruik van Hooks

### Doel
Leer hoe je React hooks gebruikt om functionaliteit aan je componenten toe te voegen.

### Instructies
1. **Gebruik de `useEffect` hook:**
   - Open het bestand `src/App.js` in Visual Studio Code.
   - Voeg de volgende code toe om de `useEffect` hook te gebruiken:
     ```javascript
     import React, { useState, useEffect } from 'react';

     function Timer() {
       const [count, setCount] = useState(0);

       useEffect(() => {
         const timer = setInterval(() => {
           setCount(prevCount => prevCount + 1);
         }, 1000);

         return () => clearInterval(timer);
       }, []);

       return (
         <div>
           <p>Timer: {count} seconds</p>
         </div>
       );
     }

     function App() {
       return (
         <div>
           <Timer />
         </div>
       );
     }

     export default App;
     ```

2. **Voer de applicatie uit:**
   - Zorg ervoor dat de ontwikkelserver nog steeds draait.
   - Open je webbrowser en ga naar `http://localhost:3000` om je wijzigingen te zien.

## Opdracht 4: Componenten en Props

### Doel
Leer hoe je componenten kunt hergebruiken en props kunt doorgeven.

### Instructies
1. **Maak herbruikbare componenten:**
   - Open het bestand `src/App.js` in Visual Studio Code.
   - Voeg de volgende code toe om herbruikbare componenten te maken:
     ```javascript
     import React from 'react';

     function Greeting(props) {
       return <h1>Hello, {props.name}</h1>;
     }

     function App() {
       return (
         <div>
           <Greeting name="Alice" />
           <Greeting name="Bob" />
           <Greeting name="Charlie" />
         </div>
       );
     }

     export default App;
     ```

2. **Voer de applicatie uit:**
   - Zorg ervoor dat de ontwikkelserver nog steeds draait.
   - Open je webbrowser en ga naar `http://localhost:3000` om je wijzigingen te zien.

## Opdracht 5: Formulieren en Gebeurtenissen

### Doel
Leer hoe je formulieren en gebeurtenissen in React kunt beheren.

### Instructies
1. **Maak een formuliercomponent:**
   - Open het bestand `src/App.js` in Visual Studio Code.
   - Voeg de volgende code toe om een formuliercomponent te maken:
     ```javascript
     import React, { useState } from 'react';

     function NameForm() {
       const [name, setName] = useState('');

       const handleChange = (event) => {
         setName(event.target.value);
       };

       const handleSubmit = (event) => {
         alert('A name was submitted: ' + name);
         event.preventDefault();
       };

       return (
         <form onSubmit={handleSubmit}>
           <label>
             Name:
             <input type="text" value={name} onChange={handleChange} />
           </label>
           <button type="submit">Submit</button>
         </form>
       );
     }

     function App() {
       return (
         <div>
           <NameForm />
         </div>
       );
     }

     export default App;
     ```

2. **Voer de applicatie uit:**
   - Zorg ervoor dat de ontwikkelserver nog steeds draait.
   - Open je webbrowser en ga naar `http://localhost:3000` om je wijzigingen te zien.

## Opdracht 6: API-aanroep met Axios

### Doel
Leer hoe je API-aanroepen kunt maken met behulp van Axios in een React-applicatie.

### Instructies
1. **Installeer Axios:**
   - Open de terminal in Visual Studio Code.
   - Typ `npm install axios` en druk op Enter.

2. **Maak een component voor API-aanroepen:**
   - Open het bestand `src/App.js` in Visual Studio Code.
   - Voeg de volgende code toe om een component te maken die gegevens ophaalt van een API:
     ```javascript
     import React, { useState, useEffect } from 'react';
     import axios from 'axios';

     function DataFetcher() {
       const [data, setData] = useState(null);

       useEffect(() => {
         axios.get('https://jsonplaceholder.typicode.com/posts/1')
           .then(response => {
             setData(response.data);
           })
           .catch(error => {
             console.error('Error fetching data:', error);
           });
       }, []);

       return (
         <div>
           {data ? (
             <div>
               <h2>{data.title}</h2>
               <p>{data.body}</p>
             </div>
           ) : (
             <p>Loading...</p>
           )}
         </div>
       );
     }

     function App() {
       return (
         <div>
           <DataFetcher />
         </div>
       );
     }

     export default App;
     ```

3. **Voer de applicatie uit:**
   - Zorg ervoor dat de ontwikkelserver nog steeds draait.
   - Open je webbrowser en ga naar `http://localhost:3000` om je wijzigingen te zien.