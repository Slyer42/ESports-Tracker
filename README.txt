Daniel Isufaj Matrikelnummer: 29707
Dokumentation: https://developers.pandascore.co/docs

Api-Key= MX17ghiwqUduAdt__Ency9hu2Bqne1tsm1YAqBiyVrDAnF83oTQ

Cloud URL: https://laughing-bassi-9a92ac.netlify.app/#/

Architektur: Im Home View werden nur die Komponenten aufgerufen, sowie Zwei Buttons welche jeweils eine Komponente anzeigen lassen.

Die liveInformation Komponente zeigt aktuelle Spiele aus jeder League of Legends Liga. 
Wenn aktuell kein Spiel gespielt wird, wird auch nichts ausgegeben.
UpcomingInformation Komponente macht etwas ähnliches und zeigt die nächsten 6 Spiele an die gespielt werden
Die ausgegeben Daten kann man anklicken und und kommt dann zu der Website welche die Spiele anzeigt.


Wenn man auf den Serien anzeigen Button drückt wird die seriesTracker Komponente aufgerufen. 
Diese gibt einem die Auswahl zwischen 3 Optionen welche verschiedene Api Calls aufrufen.

Wenn man auf nach Teams suchen drückt wird die searchTeams Komponente aufgerufen. 
Diese enthält ein Input Feld und einen Such Button.
Die Such Funktion wird nur dann aufgerufen wenn das Input Feld einen String enthält.
Leider hab ich es nicht hinbekommen den search[name] paramter zu übergeben weswegen diese Komponente nicht funktioniert


Schritte zum starten.

npm install axios
npm run serve

  