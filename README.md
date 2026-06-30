# Audi E-Tron GT HV Reset
In diesem Repository habe ich alle Schritte zusammengefasst, die nötig waren, um meinen Audi E-Tron GT nach einem Unfall wieder vollständig freizuschalten und in Betrieb zu nehmen. Von der ersten Fehlerdiagnose über die Arbeit mit ODIS, der Rückstellung der Airbag- und Hochvoltsysteme bis hin zur finalen Freigabe durch das Fahrzeug.

Dies ist nur ein Bericht meiner erfahrung er kann fehler enthalten und jeder der keine Sachkundige ausbild oder schulung besitzt sollte keine Reperaturen am HV System oder E-Fahrzeugen im Allgemeinen druchführen. Handeln auf eigene Gefahr.<!--Hier besserer Rechtsschutz-->


## Audi E-Tron GT / Porsche Taycan
Beide Stehen auf der J1 Plattform, die von Porsche entwickelt wurde.
Falls ihr Bauteile für euer Projekt benötigt es sind viele Teile unter den modellen austauschbar. (Hier kommt noch mehr)

## Bestandausnahme
Kurz zu meinem Fahrzeug, das Fahrzeug ist ein audi erton gt von 2022. Es hatte einen rechtsseitigen frontal crash (was genau passiert ist weiß ich noch nicht).
Ausgelöst wurden alle ffrontairbags und die Seitlichen Kopfairbags.
Laut den technischen daten von audi ist dieser Crash nicht durhc einen Klemme 15 reset (Batterie abklemmen und wieder anklemmen) behebbar.

Beschädigt war somit:
- die ganze rechte Front.
- Der Laderegler 
- Die Hochvoltheizung
- Der Scheinwerfer 
- usw.


# HV Reset
Kurz zum aufbau des Schaltkasten der Hochvoltbatterie SX6 inklusive Zünder für Hochvoltbatterieunterbrechung N563, in diesem Befinden sich **KEINE Pyrotrechnischen Sicherungen** in manchen Foren im Internet wird dies behauptet, dies ist aber nicht richtig.
  - (Anders zum Audi E-Tron 55, Q8, Q4 diese besitzen eine Pyrotechnische Sicherungen die bei einem Crash ausgelöst werden kann)
![image alt](https://github.com/Marco-Polo20/Audi-E-Tron-GT-HV-Reset/blob/main/HV-Crash-N563.png)

Im SX6 befinden sich aber 2 Schütze (große Relais) und 2 Sicherungen (die sehr stark an NH Sicheurngen erinnern). Eine für die Positive Seite und eine für die negative Seite.

![image alt]() <!--Hier bild aus Video vom Inneren der SX6-->

Es kann sein das bei einem Crash mit einem Körperschluss des HV Systems diese Sicherungen auslösen. 
Falls dies der Fall sein sollte, sollten beide Schütze und beide Sicherungen getauscht werden egal ob diese Defekt sind oder nicht (wenn sie es jetzt noch nicht sind werden sie es bald sein).
## 1. Benötigte Werkzeuge
- Messgerät
- 1000V Handschuhe
- ODIS 25 und neuer (bei älteren Versionen kann es sein das manche fehlercodes nicht richtig interpretiert werden können, dann steht dort soetwas wie P00001 Entickelungscode 1 oder so)
  - **KEINE Internet verbindung**
  - VX Diag Paththrou Device J.... (XXX)
- Werkzeugkasten


- **Interessantes**
    - Woher Dokumentation
  
## 2. Airbag-Steuergerät fehler beheben

Das Steuergerät 0015 Airbag darf keine Statischen fehler enthalten. Der Crash-Reset in diesem Steuergerät kann nur mit einer Odis Online Version erfolgen oder der Service wird bei einschlägigen Anbietern im Internet erworben (~120€).
Alle anderen fehler die zusammenhängen mit den nicht mehr funktionsfähigen Airbags und Sicherheitsgurten können mit einer offline Version von Odis zurückgesetzt werden. 

Die Sicherheitsgurte müssen über die Grundeinstellung im Geführten funktrionen menue neu angelernt werden. Danach sind diese Fehler Passiv und können gelöscht werden.
 - 0015 Airbag -> Geführte Funktionen -> Grundeinstellung Sicherhheitsgurt Li, Re usw.
   
![image alt]() <!--Bild Airbag Odis Grundeisntllung-->


Alle anderen Airbag Fehler werden von Aktiv/Statisch zu Passiv wenn die Airbags durch neue ersetzt wurden. Und die Sensoren/ Sensorleitungen repariert wurden.
Danach können alle gelöscht werden.

## 3. Initialisierung HV System
<!--War das wirklich der 3. Punkt?-->
Kann sein das fehlschlägt wegen <20V nach den Schützen

![image alt]() <!--Bild Odis Sonderfunktionen-->

## 4. Grundeinstellung HV System
<!--Fehlercode Thematisieren (HV contaktor defekt oder so inklusive bild)-->

![image alt]() <!--Bild Odis Conector fehler-->

<!-- Technische Sachen zum vorladewiderstand und den schützen bezug zu oben -->

Zu guter letzt muss via eigendiagnose der Crash wert im HV Sytem zurückgesetzt werden. Dazu eigendiagnose HV Hybrid managment 008C Batteriemanagment/ Hybrid Battery Energy Managment J840. USW
Code 20103










