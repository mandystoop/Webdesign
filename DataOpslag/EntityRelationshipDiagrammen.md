# Opdracht: Conceptueel Denken over Databases met Entity Relationship Diagrams (ERD)

## Doel
Leer hoe je conceptueel kunt denken over databases door het maken van Entity Relationship Diagrams (ERD). Dit helpt je om de structuur en relaties binnen een database te visualiseren en te begrijpen.

## Instructies

1. **Lees over Entity Relationship Diagrams:**
   - Lees je in over ERD's. Bekijk bijvoorbeeld de volgende pagina's:
     - Entity-Relationship Model
     - ER Diagrams

2. **Identificeer entiteiten en relaties:**
   - Voor deze opdracht ga je een database ontwerpen voor een vliegveld. Denk hierbij aan entiteiten zoals inkomende vluchten, uitgaande vluchten, passagiers, airlines, gates, en bagage.
   - Identificeer de belangrijkste entiteiten en de relaties tussen deze entiteiten.

3. **Maak een ERD:**
   - Gebruik een tool zoals Lucidchart of Draw.io om een ERD te maken voor het vliegveld scenario.
   - Zorg ervoor dat je de entiteiten, attributen en relaties duidelijk weergeeft.

4. **Voeg cardinaliteit toe:**
   - Voeg cardinaliteit toe aan je ERD om de aard van de relaties tussen entiteiten te specificeren (bijv. één-op-veel, veel-op-veel).

5. **Koppeltabellen:**
   - Identificeer waar koppeltabellen nodig zijn om veel-op-veel relaties te beheren (bijv. een koppeltabel tussen passagiers en vluchten).

6. **Presenteer je ERD:**
   - Maak een korte presentatie (ongeveer 5 minuten) waarin je je ERD uitlegt en de keuzes die je hebt gemaakt bespreekt.

## Uitleg
- **Entity Relationship Diagram (ERD)**: Een visuele weergave van de entiteiten binnen een systeem en de relaties tussen deze entiteiten.
- **Entiteit**: Een object of concept dat gegevens moet worden opgeslagen (bijv. een persoon, plaats, ding of gebeurtenis).
- **Relatie**: De associatie tussen twee of meer entiteiten.
- **Cardinaliteit**: Geeft de hoeveelheid van een entiteit die kan worden geassocieerd met een enkele instantie van een andere entiteit (bijv. één-op-veel, veel-op-veel).
- **Koppeltabel**: Een tabel die wordt gebruikt om veel-op-veel relaties tussen entiteiten te beheren.

## Implementatie

1. **Database implementatie:**
   - Gebruik je ERD als basis om een daadwerkelijke database te implementeren in MySQL.
   - Maak de benodigde tabellen en koppeltabellen aan in MySQL.
   - Voeg enkele voorbeeldgegevens toe aan je database.