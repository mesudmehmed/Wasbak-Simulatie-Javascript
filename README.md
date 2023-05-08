
# Wasbak Simulatie

Dit is een Wasbak simulatie waarbij de demo live gegevens toont van de waterstand, vulsnelheid, error(de verschill) en andere relevante informatie. De gebruiker kan ook een ingestelde waarde invoeren om het waterniveau te regelen via de MQTT-broker. De pagina bevat ook een grafiek van de trendgegevens van het waterpeil. Het geheel is geprogrammeerd in JavaScript met behulp van de Eclipse Paho MQTT JavaScript-bibliotheek en SVG-graphics en ook een stukje Bootstrap.


## Gebruik
Zet de style.css & de index.html in een folder en open de index.html in uw browser, als het goed is zou alles moeten werken.

## Variabelen
- setpoint: de gewenste waterstand in de wasbak.
- waterLevel: de huidige waterstand in de wasbak.
- error: het verschil tussen het gewenste waterpeil en het huidige waterpeil.
- fillRate: de snelheid waarmee water aan de wasbak wordt toegevoegd.
- maxFillRate: de maximale snelheid waarmee water aan de wasbak kan worden toegevoegd (in liters per minuut).
- lastFillTimestamp: de tijdstempel van het laatste vulgebeurtenis.
- fillVolume: het totale volume water dat aan de wasbak is toegevoegd (in liters).
- trendData: een array van trendgegevenspunten voor de vullingsnelheid.
- logInterval: het interval (in milliseconden) waarop gegevens worden gelogd naar de console.
- lastLogTime: de tijdstempel van de laatste console-log gebeurtenis.
- drainTrendData: een array van trendgegevenspunten voor de afvoersnelheid.
- drainRate: de snelheid waarmee water uit de wasbak wordt afgevoerd.
- maxDrainRate: de maximale snelheid waarmee water uit de wasbak kan worden afgevoerd (in liters per minuut).

## Functies
- function updateSimulation() - Deze functie berekent de huidige fout tussen het ingestelde punt en het huidige waterpeil, beperkt de vullingsgraad tot het maximaal toegestane vullingspercentage, berekent het vullingsnelheid waarmee water aan de wasbak wordt toegevoegd en bijhoudt de toegevoegde waterhoeveelheid. Vervolgens wordt het waterpeil bijgewerkt, worden de fout- en vullingsgraadwaarden op de webpagina bijgewerkt en worden de MQTT-berichten verzonden die deze waarden en trendgegevens bevatten.
- function connectToMQTTBroker() - Deze functie verbindt de MQTT-client met de broker en abonneert zich op bepaalde topics om te ontvangen.
- function onMessageArrived(message) - Deze functie wordt aangeroepen wanneer er een MQTT-bericht binnenkomt. Het bijwerken van de ingestelde waarde, het waterpeil, de vullingsgraad, het vullingssnelheid en de trendgegevens van de berichten worden bijgehouden en de webpagina wordt hiermee bijgewerkt.
- function sendMessage() - Deze functie stuurt de ingestelde waarde naar de MQTT-broker als een nieuw MQTT-bericht. Het verzenden van het bericht en de status van het verzenden worden bijgehouden.
- function simulate() - Deze functie roept de updateSimulation()-functie aan om de simulatie bij te werken en de resultaten te loggen en roept zichzelf daarna opnieuw aan na 100 milliseconden om de simulatie voort te zetten.


## Tutorials die ik gevolgd heb om dit simulatie te maken

 - [MQTT from Javascript](https://www.youtube.com/watch?v=scgt9qK8xvU)
 - [JavaScript-based MQTT #1: Mosca Broker & MQTT.js Client](https://www.youtube.com/watch?v=HRrqF8ISQJs&t=35s)
 - [Making Shapes With CSS](https://www.youtube.com/watch?v=IhbSuNXNnnU)
 - [Bootstrap tutorial 11 - Buttons](https://www.youtube.com/watch?v=VBKD5q7ohG4)
 - [JavaScript Functions](https://www.youtube.com/watch?v=N8ap4k_1QEQ)
 - [JavaScript for Beginners — Console Logging](https://www.youtube.com/watch?v=RLCpvCTiDRo)
 - [data visualization using HTML, CSS and JavaScript | create line graph | create chart javascript](https://www.youtube.com/watch?v=RTUZ1VftA5o)
