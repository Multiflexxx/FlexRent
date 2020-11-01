# Plattformen und Frameworks – Flexrent

<p align="center">
  <img alt="Flexrent Logo" width="30%" height="auto" src="https://raw.githubusercontent.com/Multiflexxx/FlexRent/master/Logo/PNG/HighResolution/Logo_purple_no_background.png"><br><br>
  <img src="https://badgen.net/github/tag/Multiflexxx/client-flex-rent/?color=purple">
  <img src="https://badgen.net/github/release/Multiflexxx/client-flex-rent/?color=pink">
  <img alt="uptime" src="https://badgen.net/uptime-robot/day/m786242203-1d182d7e978c6d1848dd508a"><br>
  <a href="https://flexrent.multiflexxx.de/BuildApp/Releases/flexrent.apk"><img alt="Lade die App herunter" src="https://badgen.net/badge/Download/Lade_die_App_herunter/?color=blue"></a>
</p>

# Inhaltsverzeichnis
1) [Idee](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#idee)
2) [Technologien](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#technologien)<br>
2.1) [Flutter](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#flutter)<br>
2.2) [NestJS](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#nestjs)<br>
2.3) [Typescript](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#typescript)<br>
2.4) [MariaDB](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#mariadb)<br>
2.5) [Docker](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#docker)<br>
2.6) [Google Geocoding API](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#google-geocoding-api)<br>
2.7) [OAuth2](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#oauth2)<br>
3) [Frontend](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#frontend)<br>
3.1) [Repository](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#repository)<br>
3.2) [Verwendete Technologien](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#verwendete-technologien)<br>
4) [Backend](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#backend)<br>
4.1) [Repository](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#repository-1)<br>
4.2) [Verwendete Technologien](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#verwendete-technologien-1)<br>
4.3) [Vorgehen & Erklärungen](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#vorgehen-und-erk%C3%A4rungen)<br>
4.4) [API](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#die-api)<br>
5) [Lizenz](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#lizenz)
6) [CI/CD](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#cicd)
7) [Ausblick für die Zukunft](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#die-zukunft-von-flexrent)
8) [Marketing](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#marketing)
9) [Rechtliches](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#rechtliche-grundlagen)
10) [Functional Requirements](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#functional-requirements)


## Idee:
Du brauchst eine Bohrmaschine oder eine Musikbox aber nur für eine kurze Zeit brauchst sie nur dafür dann bist du auf Flexrent genau richtig. Wir wollen eine Plattform bieten auf der Gegenstände von Privatperson zu Privatperson zu vermietet werden können. Die Mobile App ermöglicht es den Nutzern Gegenstände zu vermieten und Gegenstände zu mieten. Dafür genügt die Erstellung eines Profils. 

FlexRent bietet einen Marktplatz für Privatpersonen, die selten genutzte Gegenstände leihen oder verleihen möchten. Durch FlexRent besteht die Möglichkeit Gegestände, die ansonsten verstauben, zu Geld zu machen. Eine teuere Heckenschere, die nur einmal im Jahr benötigt wird kann hier für andere Menschen angeboten werden. Andererseits können Nutzer Gegenstände die sie für einen bestimmten Zeitpunkt benötigen mieten und sparen sich das Geld für eine Neuanschaffung. 

Die App bietet das eanbieten und das leichte finden von Gegenständen in der Nähe. Die Vermieter können selbst Zeiträume bestimmen, an denen er den Gegenstand nicht benötigt. Zudem hat er die Möglichkeit den Preis, Bilder und eine Beschreibung des Gegenstandes anzufertigen. 

Diese Gegensände können von den Mietern gefunden werden. Vermieter erhalten Bewertungen von den Mietern. So haben Mieter die Möglichkeit zuverlässige Vermieter zu finden. 

Der Mietprozess wird durch die App vereinfacht gestaltet. Der Mieter sucht sich den passenden Gegenstand und startet eine Mietanfrage. Wenn der Vermieter diese Anfrage annimmt kann der Mieter den Gegenstand bei dem Vermieter abholen.  

In Flexrent wird die Kamera als Vorteil einer Mobilenanwendung verwendet, um QR Codes beim Abholen und Zurückbringen des Gegenstandes zu scannen. Damit stellen wir sicher, welche Person im Besitz des Gegenstandes ist, da beide Nutzer mit dem QR Code interagieren müssen. Beim Verleihen wird der QR Code auf der Seite des Mieters erzeugt. Der Vermieter Scannt diesen. Bei der Rückgabe ist es umgekehrt.  


## Technologien

### Flutter 

Flutter ist ein Framework, mit welchem schnell Apps sowohl für Android als auch für iOS erstellt werden können. Flutter wurde von Google entwickelt und basiert auf Googles hauseigener Programmiersprache Dart. Dart ist ähnlich zu Java aber auch zu Javascript, was die Lernkurve für uns stark reduzierte und uns somit eine schnellere Entwicklung bescherte.Flutter ist sehr einfach zu installieren und einzubinden, da Android Studio/IntelliJ sowie Visual Studio Code bereits sehr gute Plugins dafür bestzen. Außerdem ist Flutter besonders auf Apps ausgelegt, da bereits Material und Cupertino Designs eingebunden sind. Weitere Informationen können auf der offiziellen Website von [Flutter](https://flutter.dev/) oder [Dart](https://dart.dev/) gefunden werden.

### NestJs
NestJS ist ein auf Node.js basierendes Framework, dass Javascript und Typescript unterstützt. NestJS nutzt HTTP Server Frameworks wie Express um möglichst robust zu funktionieren. Wir haben uns für NestJS entschieden, da wir die Unterstützung von Objektorientierung und Typsicherheit bevorzugen und der Typescriptsupport von NestJS sehr gut ist. Zusätzlich ist vorallem der Modulare Aufbau von NestJs gut, um ein separation of concerns zu erhalten.
Weitere Informationen finden sich auch der [Webseite von NestJs](https://docs.nestjs.com/).

### TypeScript
Da wir mit der Festlegung auf NestJS bereits die Auswahl der möglichen Programmiersprachen auf Javascript und Typescribt eingrenzten, viel und die finale Festlegung auf Typescript recht leicht. Typescript ist eine auf Javascript basierende Programmiersprache, die im Gegesatz zu Javascript Typsicherheit erlaubt. Das macht es nicht nur einfacher mit der Programmiersprache zu arbeiten (siehe ausgefeilte Vorschläge mit z.B. IntelliSens von VS Code), sondern schützt auch uns Entwickler vor unseren eigenen Fehlern, die bei Javascript gerne mal so lange unter dem Radar fliegen, bis der node Server nur noch 500er Fehler wirft. Typescript schafft es dabei so nah an Javascript zu bleiben, dass die Lernkurve bei einem gewissen Grundlagenwissen in Javascript nach ein paar Minuten bereits erklommen sein kann.

### MariaDB
MariaDB ist ein Open-Source Datenbankmanagementsystem für relationale Datenbanken, welches als Fork aus MySQL entstand.
Der Open-Source-Ansatz ist für unsere Anwendung praktisch, da keine Lizenzgebühren gezahlt werden müssen.
Weitere Informationen finden sich auf der [Webseite der MariaDB Foundation](https://mariadb.org/documentation/).

### Docker
Die Containervirtualisierungssoftware Docker hilft uns dabei mehrere Prozesse isoliert voneinander auf einem Server laufen zu lassen.
So nutzen wir verschiedene Container um unsere API bereitzustellen, neue App Versionen zu kompilieren und den Datenbankserver bereitzustellen.
Weiter Informationen zu Docker finden sich auf der [Webseite von Docker](https://www.docker.com/).

### Google Geocoding API
Die Geocoding API gibt Konvertiert gegebene Daten wie Straße, Hausnummer, Postleitzahl und Stadt in geographische Koordinaten.
Diese Koordinaten können dann verwendet werden, um zum Beispiel die Distanz zwischen zwei Punkten auf der Welt zu bererechnen.
Weitere Informationen finden sich auf der [Webseite von Google](https://developers.google.com/maps/documentation/geocoding/overview).

### OAuth2
Ein User oder Resource Owner kann mit Hilfe des OAuth2 Protokolls einer Anwendung (Client) den Zugriff auf seine Daten erlauben, die von einem anderen Dienst (Resource Server) bereitgestellt werden, ohne geheime Details seiner Zugangsberechtigung dem Client preiszugeben. Beispielsweise kann ein User einem Dritten (in diesem Fall unserer App) erlauben, auf seine/ihre Daten auf Facebook, Google & co. zuzugreifen. Das erfolgt durch manuelle Bestätigung des Users bei der Registrierung (Sign up with Google/Apple/Facebook). Nach erfolgter Bestätigung erhalten wir einen Token, den wir benutzen können, um bei den APIs von Google/Apple/Facebook Informationen über den User aufzurufen, und zwar nur in dem Umfang, den der User vorher freigegeben hat. Bei uns beschränkt sich das auf die Email und den Vor- und Nachnamen des Users, damit wir die Registrierung vereinfachen können und den User schneller und komfortabler einloggen können.

## Frontend
### Repository
[Frontend Repository](https://github.com/Multiflexxx/client-flex-rent)

### Verwendete Technologien
- Flutter für die Appentwicklung
- CI/CD mit GithubActions

## Backend
### Repository
[Backend Repository](https://github.com/Multiflexxx/server-flex-rent)

### Verwendete Technologien
- NestJS für die Businesslogik
- MariaDB als Datenbank
- Docker für die Containervirtualisierung
- CI/CD mit GithubActions
- Google Geocoding API um die Geokoordinaten der Postleitzahlen zu erlangen
- JSON zur Kommunikation mit der APP

### Vorgehen und Erkärungen
Der Backendcode gliedert sich in einzelne Module, die jeweils einen Controller, einen Service und verschiedene Models beinhalten.
Das Backend teilt sich dabei in die Überkategorien `User` und `Offer`.
Das Usermodul kümmert sich um alle Anfragen, die etwas mit Benutzern zu tun haben. Hier können Nutzer erstellt, geupdated, verifiziert und gelöscht werden.
Das Offermodul kümmertsich darum, dass Nutzer Angebote einstellen, ändern, suchen, löschen und buchen können. Zusätzlich kümmert es sich um den kompletten Verleihprozess.
Das Offermodul greift zur verifizierung der Benutzer auf das Usermodul zu. So kann duplicated code vermieden werden und ein separation of concerns erreicht werden.
Beide Module besitzen gemeinsam verwendete Hilfsfunktionen, die die Kommunikation mit der Datenbank und das Schreiben und Lesen von Dateien von Festplattendaten ermöglichen. Die Hilfsfunktionen sind dabei statisch.
Statt Objekten werden Interfaces zum Internen Datenaustausch verwendet, dadurch wird vermieden, dass Objekte bei jeder Benutzung neu instanziiert werden müssen.
Asynchrone Aufrufe werden mit dem Promise-Konzept gehandlet, da dies eine bessere Lesbarkeit bietet als Callbackfunctions.

Eine Besonderheit ist die Handhabung der Lokationen der Angebote:
Um zu gewährleisten, dass Nutzer nur Angebote in ihrer Nähe finden sind die Angebote mit der Postleitzahl des Verleihers verknüpft.
Da es schwierig ist jedes Mal alle Distanzen zum Mieter neu zu berechnen haben wir uns dazu entschieden die Distanz von jeder Stadt zu jeder anderen Stadt vorher zu berechnen und in einer Tabelle abzuspeichern. Mit unseren ~13.000 Postleitzahlen erhalten wir daher eine Tabelle mit Distanzen mit ~169.000.000 Einträgen.
Die Suche durch diese Tabelle ist jedoch deutlich schneller (ein paar Millisekunden) als die Neuberechnung bei jeder Suche.
Um die Geokoordinaten der einzelnen Städte zu erhalten wurde die Google Maps Geocoding API verwendet. Zu jeder Postleitzahl aus unserer Tabelle (die eigentlich zur Verifikation der Nutzereingaben dient) haben wir die Latitude und die Longitude mit der Google API gesucht.

### Die API
Für die verbindung zum Frontend haben wir uns für einen REST-API entschieden.
Die HTTP-Methoden lassen sich optimal auf die CRUD-Methoden für relationale Datenbanken Mappen, was ein einfacheres Verständis der Vorgänge ermöglicht.
NestJs bietet zusätzlich für die Entwicklung von REST-APIs viele nützliche Features wie z.B. die Dekoratoren in den Controllern.
Das Error-Handling von NestJS ermöglicht es zudem leicht HTTP-Fehlercodes auszugeben. Eine ausführlichere Dokumentation der API kann in der [API Dokumentation](https://github.com/Multiflexxx/FlexRent/blob/master/API-Documentation.md) gefunden werden.
Wir haben uns gegen die Verwendung von Swagger in Verwendung mit NestJS entschieden, da bereits ein erster Versuch in Nutzung der Dokumentationsfunktion keine brauchbaren Ergebnisse lieferte.

## CI/CD
Sowohl das Frontend als auch das Backend verwenden verwenden GithubActions für einen automatisierten Deploymentprozess.
Bei einem Push auf unsere `releases`-Branches, wird jeweils eine GithubAction getriggert, die einen Endpoint auf unserem Server aufruft.
Der Server zieht dann einen pull von Github und kompiliert die App mit Flutter, bzw. die API mit NestJS.
Anschließend wird die App unter einem Link bereitgestellt bzw. die API mit den neuen Features bereitgestellt.

## Lizenz

## Die Zukunft von Flexrent
- Chat 
- Lightmode
- Nutzungsbedingungen 
- Rechtliche Absicherung
- Webseite 
	- Werbung
	- Weiterleiten auf die App
- Tutorial beim ersten Starten der App
- Teilen der App durch link in der App

## Marketing:
- Werbung über Youtube, Instagram auf gezielte Zielgruppen:
	- Junge Investoren (Finanzkanäle)
	- Tech begeisterte (MKBHD…)
	-…
- Werbung und Supportstruktur über social media Kanäle
- Sponsoring von YouTube Kanälen

## Rechtliche Grundlagen:
- Mit einem Leihvertrag wird eine Sache (kein Recht) gemäß §§ 598 bis 606 BGB unentgeltlich zum Gebrauch überlassen. Beim Ausleihen einer Sache geht der Verleiher im Alltag davon aus, dass die Sache auch zurückgegeben wird, zu Recht: Nach Ablauf der Leihzeit oder durch vorzeitige Vertragskündigung durch eine der Parteien muss der Entleiher dem Verleiher die entliehene Sache zurückgeben. Während der Leihzeit ist die entliehene Sache vom Entleiher ausschließlich vertragsgemäß zu gebrauchen; eine Weitergabe an Dritte ist nach § 603 BGB untersagt. Der Entleiher haftet nicht für Abnutzungen und Verschlechterungen an der Sache, die durch einen ordnungs- und vertragsgemäßen Gebrauch auftreten; bei einem nicht vertragsgemäßen Gebrauch richtet sich die Haftung jedoch nach dem allgemeinen Schadensersatzrecht. Bei einer Leihe handelt es sich rechtlich um einen unvollkommen zweiseitigen Vertrag; der Verleiher ist zur entgeltfreien Leihgabe über den vereinbarten Zeitraum verpflichtet, der Entleiher zum sachgemäßen Umgang mit der Sache und die fristgemäße Rückgabe derer verpflichtet.
-  Häufig wird der Leihvertrag auch als Gebrauchsüberlassung bezeichnet.
- Es liegt ein Mietvertrag vor, da es eine entgeltliche Verleihung eines Gegenstandes/ Sache ist. -> Mietgebühr
- Als allgemeine zivilrechtliche Rechtsgrundlage dient für Dienstleistungen der Dienstvertrag, bei dem nach § 611 BGB der Dienstverpflichtete gegen Vergütung Dienste jeder Art für den Dienstberechtigten erbringen soll. Es handelt sich um einen individualrechtlichen Austauschvertrag        zwi-schen Auftraggeber und Auftragnehmer über die unabhängige oder abhängige Leis-tung eines Dienstes gegen ein Entgelt. Bei allen Dienstleistungen sind die Dienstleis-tungspflicht und die Vergütungspflicht vertragliche Hauptpflichten. Die Dienstleistung ist vom Dienstverpflichteten im Zweifel persönlich zu erbringen (§ 613 BGB). Diese persönliche Abhängigkeit trifft jedoch nicht auf gattungsmäßig umschriebene Tätigkei-ten im Rahmen freier Dienstnehmer zu.

## Functional Requirements
Unsere Functional Requirements sind [hier](https://github.com/Multiflexxx/FlexRent/blob/master/Functional%20Requirements.md) zu finden.
