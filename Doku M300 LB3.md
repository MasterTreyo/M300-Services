<h1> Dokumentation M300
<h2> LB3 - Tobias Schmitz


### Inhaltsverzeichnis
- [1. Auftrag](#1-auftrag)
- [2. Aktueller Wissensstand](#2-aktueller-wissensstand)
  - [2.1 Docker](#21-docker)
  - [2.2 Microservice](#22-microservice)
- [3. Gelerntes](#3-gelerntes)
  - [3.1 Docker](#31-docker)
  - [3.2 Microservices](#32-microservices)
- [4. Dockereinrichtung](#4-dockereinrichtung)
  - [4.1 Volumes](#41-volumes)
- [5. Dockerbefehle](#5-dockerbefehle)
- [6. Sicherhetisaspekte](#6-sicherhetisaspekte)
- [7. Testfälle](#7-testf%C3%A4lle)
- [8. Reflexion](#8-reflexion)

## 1. Auftrag
Eine Dockerumgebung installieren und nach Vorgaben einrichten. 

## 2. Aktueller Wissensstand 
Der aktuelle Wissenstand zu unten aufgeführten Themen wird erklärt:

### 2.1 Docker
Docker ist etwas, um nur applikationen (Microservices) laufen zu lassen. 

### 2.2 Microservice
Architekturstil für die Erstellung von Applikationen.

## 3. Gelerntes
Das dazu gelernte Wissen wird hier dokumentiert.

### 3.1 Docker 
Containisierungstechnologie um unabhängige, leichtgewichtige VM's zu erstellen, welche ohne grossen Aufwanf kopiert und zwischen Umgebungen bewegt werden kann. 

### 3.2 Microservices
Hier wird ein Programm auf die kleinsten Komponenten runtergebrochen und kann somit z.B. von Docker einfach verwaltet und verwendet werden. Microservices können besser getestet und verstanden werden.

## 4. Dockereinrichtung
Docker heruntergeladen und direkt auf Windowsumgebung eingerichtet.  

### 4.1 Volumes
Volume ./php/www erstellt, damit ich das index.html live bearbeiten kann. Ein zusätzliches Volume "volume1" für die Datenablage wurde erstellt.


## 5. Dockerbefehle
Häufig verwendete Dockerbefehle:

    + docker run = führt einen Befehl aus
    + docker pull/push = lädt ein image herunter/hoch
    + docker images = listet alle vorhandenen images auf
    + docker restart = startet container neu
    + docker volume = verwaltung von volumen
    + docker container = zur verwaltung von containern
    + docker container ls --all = zeigt alle laufenden Container an
    + docker config = verwaltet Docker konfiguration
    + docker deploy =  deployed/aktualisiert einen stack
    + docker stats = container auslastung anzeige

## 6. Sicherhetisaspekte
Folgende Sicherheitsaspekte wurden implementiert und berücksichtigt: 

    - Memory Limitierung

## 7. Testfälle
Folgende Tests wurden gemacht:

  | Testfall  | Ergebnis |
| ------------- | -------------|
| Zugriff auf localhost  | Erfolgreich
| Zugriff auf phpMyAdmin  | Erfolgreich


## 8. Reflexion
Ich nahm mir nicht viel Zeit für diese Aufgabe, da ich mir die Zeit nicht gut eingeteilt habe. Dies ist auch der Grund, weshalb ich nicht viel für LB3 machen konnte. Ich werde daraus lernen und mir beim nächsten Mal noch mehr Gedanken dazu machen, wie ich mir die Zeit einteilen werde. Ich war bei LB2 so genau, dass mir zu wenig Zeit für LB3 blieb. Ich finde Docker eine gute Sache, vorallem weil es schnell und Einfach erstellt ist und wenig Performance braucht, um viele Container betreiben zu können.

In einem griffigen Satz gefasst ist Docker eine Virtualisierung ohne Virtualisierung. Die Technik dahinter heißt Containerisierung. Docker ist eine Implementierung der Container-Technologie, die sich durch besonders benutzerfreundliche Eigenschaften auszeichnet und den Begriff Container als Alternative zu virtuellen Maschinen überhaupt erst populär gemacht hat.

Ein Container fasst eine einzelne Anwendung mitsamt aller Abhängigkeiten wie Bibliotheken, Hilfsprogrammen und statischer Daten in einer Image-Datei zusammen, ohne aber ein komplettes Betriebssystem zu beinhalten. Daher lassen sich Container mit einer leichtgewichtigen Virtualisierung vergleichen.
