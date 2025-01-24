# Groepsopdracht: Penetration Testing met Kali Linux

## Doel
Het doel van deze opdracht is om studenten praktische ervaring te laten opdoen met penetration testing en het identificeren van beveiligingsproblemen door gebruik te maken van Kali Linux. Studenten zullen in groepen werken om een specifiek beveiligingsprobleem te testen en op te lossen.

## Opdrachtomschrijving
### Project Context
Elke groep kiest een beveiligingsprobleem of -oplossing om te testen met behulp van Kali Linux. Voorbeelden van mogelijke projecten zijn het hacken van een WPA WiFi-wachtwoord, het testen van de beveiliging van een webapplicatie, of het uitvoeren van een SQL-injectie aanval op een database. Neem hiervoor als voorbeeld de opdracht die in een voorgaand onderwerp is behandeld.

### Planning
Maak een eigen planning voor de uitvoering van deze opdracht. Verdeel de taken en stel deadlines vast om ervoor te zorgen dat het project binnen twee weken wordt voltooid.

### Analyse en Voorbereiding
1. **Kies een project:**
   - Bespreek in de groep welk beveiligingsprobleem of welke oplossing jullie willen testen.
   - Voorbeelden:
     - Hacking van een WPA WiFi-wachtwoord(https://www.youtube.com/watch?v=WfYxrLaqlN8).
     - Testen van de beveiliging van een webapplicatie.
     - Uitvoeren van een SQL-injectie aanval op een database(https://github.com/bhavesh-pardhi/KALI-CMDs/blob/main/100%20Kali%20linux%20Commands%20for%20Hackers.md).
     - Eigen opdracht (bespreek met docent).

2. **Voorbereiding:**
   - Installeer Kali Linux op een virtuele machine of een fysieke machine.
   - Zorg ervoor dat alle benodigde tools en pakketten zijn geïnstalleerd (bijv. aircrack-ng, sqlmap, Burp Suite).

### Implementatie en Testen
 **Uitvoeren van de aanval/test:**
   - **WPA WiFi-wachtwoord hacken:**
     - Gebruik tools zoals `airmon-ng`, `airodump-ng`, `aireplay-ng`, en `aircrack-ng` om een WPA-handshake te vangen en het wachtwoord te kraken(https://www.wikihow.com/Hack-WPA/WPA2-Wi-Fi-with-Kali-Linux).
   - **Beveiliging van een webapplicatie testen:**
     - Gebruik tools zoals Burp Suite en OWASP ZAP om kwetsbaarheden in de webapplicatie te identificeren en te exploiteren[4](https://www.kali.org/).
   - **SQL-injectie aanval:**
     - Gebruik `sqlmap` om een SQL-injectie aanval uit te voeren op een kwetsbare database en de impact te analyseren[2](https://github.com/bhavesh-pardhi/KALI-CMDs/blob/main/100%20Kali%20linux%20Commands%20for%20Hackers.md).

### Analyse en Verbetering
1. **Analyseer de resultaten:**
   - Bespreek de bevindingen binnen de groep en identificeer de belangrijkste kwetsbaarheden en beveiligingsproblemen.
   - Documenteer de analyse in een markdown-bestand genaamd `vulnerability_analysis.md`.

2. **Voorstel voor verbeteringen:**
   - Schrijf een voorstel voor beveiligingsverbeteringen op basis van de bevindingen.
   - Documenteer het voorstel.

### Eindpresentatie
Aan het einde van de opdracht presenteren de studenten hun werk aan elkaar en aan de docenten. Elke groep presenteert hun gekozen project, de uitgevoerde tests, de bevindingen en de voorgestelde verbeteringen.