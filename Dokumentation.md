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
2.8) [SMS-Gateway und SMS-Validierung](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#oauth2)<br>
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
11) [Das Logo](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#das-logo)


## Idee:
Du brauchst eine Bohrmaschine oder eine Musikbox aber nur für eine kurze Zeit? Dann bist du auf FlexRent genau richtig! Wir wollen eine Plattform bieten, auf der Gegenstände von Privatperson zu Privatperson vermietet werden können. Die Mobile App ermöglicht es den Nutzern Gegenstände zu vermieten und Gegenstände zu mieten. Dafür genügt die Erstellung eines Profils. 

FlexRent bietet einen Marktplatz für Privatpersonen, die selten genutzte Gegenstände leihen oder verleihen möchten. Durch FlexRent besteht die Möglichkeit Gegestände, die ansonsten verstauben, zu Geld zu machen. Eine teuere Heckenschere, die nur einmal im Jahr benötigt wird, kann hier für andere Menschen angeboten werden. Andererseits können Nutzer Gegenstände, die sie für einen bestimmten Zeitpunkt benötigen, mieten und sparen sich das Geld für eine Neuanschaffung. 

Die App bietet das Anbieten und das leichte Finden von Gegenständen in der Nähe. Der Vermieter kann selbst Zeiträume bestimmen, an denen er den Gegenstand nicht benötigt. Zudem hat er die Möglichkeit, den Preis, Bilder und eine Beschreibung des Gegenstandes anzufertigen. 

Diese Gegenstände können von den Mietern gefunden werden. Vermieter erhalten Bewertungen von den Mietern. So haben Mieter die Möglichkeit zuverlässige Vermieter zu finden. 

Der Mietprozess wird durch die App vereinfacht gestaltet. Der Mieter sucht sich den passenden Gegenstand und startet eine Mietanfrage. Wenn der Vermieter diese Anfrage annimmt, kann der Mieter den Gegenstand bei dem Vermieter abholen.  

In FlexRent wird die Kamera als Vorteil einer mobilen Anwendung verwendet, um QR Codes beim Abholen und Zurückbringen des Gegenstandes zu scannen. Damit stellen wir sicher, welche Person im Besitz des Gegenstandes ist, da beide Nutzer mit dem QR Code interagieren müssen. Beim Verleihen wird der QR Code auf der Seite des Mieters erzeugt. Der Vermieter scannt diesen. Bei der Rückgabe ist es umgekehrt.  


## Technologien

### Flutter 

Flutter ist ein Framework, mit welchem schnell Apps sowohl für Android als auch für iOS erstellt werden können. Flutter wurde von Google entwickelt und basiert auf Googles hauseigener Programmiersprache Dart. Dart ist ähnlich zu Java aber auch zu Javascript, was die Lernkurve für uns stark reduzierte und uns somit eine schnellere Entwicklung bescherte. Flutter ist sehr einfach zu installieren und einzubinden, da Android Studio/IntelliJ sowie Visual Studio Code bereits sehr gute Plugins dafür besetzen. Außerdem ist Flutter besonders auf Apps ausgelegt, da bereits Material und Cupertino Designs eingebunden sind. Weitere Informationen können auf der offiziellen Website von [Flutter](https://flutter.dev/) oder [Dart](https://dart.dev/) gefunden werden.

### NestJs
NestJS ist ein auf Node.js basierendes Framework, dass Javascript und Typescript unterstützt. NestJS nutzt HTTP Server Frameworks wie Express, um möglichst robust zu funktionieren. Wir haben uns für NestJS entschieden, da wir die Unterstützung von Objektorientierung und Typsicherheit bevorzugen und der Typescriptsupport von NestJS sehr gut ist. Zusätzlich ist vor allem der Modulare Aufbau von NestJs gut, um ein separation of concerns zu erhalten.
Weitere Informationen finden sich auch der [Webseite von NestJS](https://docs.nestjs.com/).

### TypeScript
Da wir mit der Festlegung auf NestJS bereits die Auswahl der möglichen Programmiersprachen auf Javascript und Typescript eingrenzten, viel und die finale Festlegung auf Typescript recht leicht. Typescript ist eine auf Javascript basierende Programmiersprache, die im Gegesatz zu Javascript Typsicherheit erlaubt. Das macht es nicht nur einfacher mit der Programmiersprache zu arbeiten (siehe ausgefeilte Vorschläge mit z.B. IntelliSens von VS Code), sondern schützt auch uns Entwickler vor unseren eigenen Fehlern, die bei Javascript gerne mal so lange unter dem Radar fliegen, bis der node Server nur noch 500er Fehler wirft. Typescript schafft es dabei so nah an Javascript zu bleiben, dass die Lernkurve bei einem gewissen Grundlagenwissen in Javascript nach ein paar Minuten bereits erklommen sein kann.

### MariaDB
MariaDB ist ein Open-Source Datenbankmanagementsystem für relationale Datenbanken, welches als Fork aus MySQL entstand.
Der Open-Source-Ansatz ist für unsere Anwendung praktisch, da keine Lizenzgebühren gezahlt werden müssen.
Weitere Informationen finden sich auf der [Webseite der MariaDB Foundation](https://mariadb.org/documentation/).

### Docker
Die Containervirtualisierungssoftware Docker hilft uns dabei mehrere Prozesse isoliert voneinander auf einem Server laufen zu lassen.
So nutzen wir verschiedene Container, um unsere API bereitzustellen, neue App Versionen zu kompilieren und den Datenbankserver bereitzustellen.
Weiter Informationen zu Docker finden sich auf der [Webseite von Docker](https://www.docker.com/).

### Verwendete APIs

#### Google Geocoding API
Die Geocoding API konvertiert gegebene Daten wie Straße, Hausnummer, Postleitzahl und Stadt in geografische Koordinaten.
Diese Koordinaten können dann verwendet werden, um zum Beispiel die Distanz zwischen zwei Punkten auf der Welt zu berechnen.
Weitere Informationen finden sich auf der [Webseite von Google](https://developers.google.com/maps/documentation/geocoding/overview).

#### openGTIN API
Mit der [openGTIN Datenbank](https://opengtindb.org/index.php) (Ehemals openEAN Datenbank) kann anhand einer [GTIN](https://www.gs1-germany.de/gs1-standards/identifikation/artikel-gtin-sgtin/) ein Produkt Identifiziert werden. Die API dieser Datenbank wird beim hinzufügen eines Produkts über den QR Code benutzt, um automatische Informationen zu erlangen. Momentan wird nur der kostenlose Testzugriff genutzt. Im weiteren Entwicklungsverlauf der App sollte jedoch eine Lizenz erworben werden.

#### Google Maps API
Die [Google Maps API](https://developers.google.com/maps/documentation?hl=de) wird benutzt, um die Adresse des Vermieters im Mietverlauf darzustellen. Momentan ist die Auslastung des Limits noch niedrig genug, um keine Gebühren zahlen zu müssen, hier müsste jedoch auch im späteren Entwicklungsverlauf eine kostenpflichtige Version erworben werden.

### OAuth2
Ein User oder Resource Owner kann mit Hilfe des OAuth2 Protokolls einer Anwendung (Client) den Zugriff auf seine Daten erlauben, die von einem anderen Dienst (Resource Server) bereitgestellt werden, ohne geheime Details seiner Zugangsberechtigung dem Client preiszugeben. Beispielsweise kann ein User einem Dritten (in diesem Fall unserer App) erlauben, auf seine/ihre Daten auf Facebook, Google & Co. zuzugreifen. Das erfolgt durch manuelle Bestätigung des Users bei der Registrierung (Sign up with Google/Apple/Facebook). Nach erfolgter Bestätigung erhalten wir einen Token, den wir benutzen können, um bei den APIs von Google/Apple/Facebook Informationen über den User aufzurufen, und zwar nur in dem Umfang, den der User vorher freigegeben hat. Bei uns beschränkt sich das auf die Email und den Vor- und Nachnamen des Users, damit wir die Registrierung vereinfachen können und den User schneller und komfortabler einloggen können.

### SMS-Gateway und SMS-Validierung
"Ein SMS-Gateway erlaubt das Senden und den Empfang von SMS-Nachrichten mittels anderer Geräte als Mobiltelefonen."([Wikipedia](https://de.wikipedia.org/wiki/SMS-Gateway))
Um die Telefonnummern unserer Nutzer zu verifizieren wird ein sechstelliger Code per SMS an die Benutzer versendet.
Dieser Code wird von uns generiert und für die Validierung zusammen mit einer eindeutigen NutzerID wieder an den Server versendet.
Für das versenden von SMS gibt es verschiedene Möglichkeiten:
- Nutzen eines SMS-Gateway-Anbieters
- Eigene SMS-Gateway Hardware
- Nutzen des eigenen Mobiltelefons

Wird ein externer Anbieter verwendet, fallen pro gesendeter SMS gebühren zwischen 7 und 15 Cent an.
Meist muss dazu noch eine monatliche Grundgebühr bezahlt werden.
Wenn keine Finanziellen hinter einer Anwendung stehen, sind dies zusätzliche Kosten, die bezahlt werden müssen.
Auch teilen sich die Nutzer des Anbieters verschiedene Nummern. Wenn eine eigene Nummer genutzt werden soll, kostet dies meist extra.
Eine weitere Möglichkeit ist der Kauf von SMS-Gateway-Hardware und der Betrieb eines eigenen Gateway-Dienstes.
Dafür kann im einfachsten Fall einfach ein SIM-USB-Stick mit einem Rechner verwendet werden.
Mobilfunkanbieter verbieten jedoch meist den "missbrauch" des Vertrags zum senden von vielen SMS, zudem kann keine Garantie über eine zuverlässige Funktionsweise gegeben werden. Es gibt jedoch auch Anbieter, die SIM-Karten dafür bereitstellen.
Dann muss nur für die SIM-Karte, den Rechner und den SIM-Kartenadapter bezahlt werden.
Auch hier können die Kosten für einen einfachen Test sehr hoch sein, weshalb die Anschaffung der Hardware unter Umständen nicht rentabel ist.

Für einfache Tests kann auch ein Mobiltelefon verwendet werden. Dazu kann eine App installiert werden, die einen HTTP-Server startet, der Anfragen entgegen nimmt. Die SMS werden dann über die SIM-Karte des Handys versendet.
Diese Option bietet sich für das Testen von SMS-Validierungsfunktionen an, da viele Nutzer in ihren Mobilfunkverträgen hunderte oder unbegrenzt viele freie SMS pro Monat haben. Der Nachteil ist hierbei jedoch, dass die eigene Mobilfunknummer für die Benutzer sichtbar ist. Zudem muss bei der Nutzung mit einem externen ein dynDNS-Eintrag auf dem Router erstellt werden oder eine statische IP-Adresse gekauft werden. Zudem wird eine Port-Weiterleitung auf das Mobilgerät benötigt. Es kann auch hier keine Garantie gegeben werden, dass SMS verschickt werden. Zudem verbieten die meisten Anbieter das Ausnutzen der unbegrenzten Nachrichten für diese Zwecke in ihren Verträgen. Für kleinere Tests sollte dies jedoch kein Problem darstellen.
Für unsere App verwenden wir die Gateway APP ["Traccar SMS Gateway"](https://www.traccar.org/sms-gateway/). Diese muss als Standard SMS-App gesetzt sein, um das SMS-Gateway nutzen zu können. Ein kostenloser DynDNS-Anbieter den wir verwenden ist [NoIP](https://www.noip.com).

Die Doku für die SMS-Gateway-App findet sich [hier](https://www.traccar.org/http-sms-api/).
Für die Nutzung muss ein `POST` auf die IP und den Port des Mobiltelefons gemacht werden (Die Daten werden in der App angezeigt, wenn das Gateway in den Einstellunge aktiviert wurde).
Der Body der HTTP-Anfrage sieht so aus:
```javascript
{
  "to": "{phone}",
  "message": "{message}"
}
```
Wichtig ist, dass in Header der Anfrage der API-Token aus der App mitgegeben wird. Das entsprechende Headerfeld heißt `authorization` und ist vom Typ API Key!

## Frontend
### Repository
[Frontend Repository](https://github.com/Multiflexxx/client-flex-rent)

### Verwendete Technologien
- Flutter für die Appentwicklung
- CI/CD mit GithubActions
- BLoC Pattern für Separations of Concern

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

### Vorgehen und Erklärungen
Der Backendcode gliedert sich in einzelne Module, die jeweils einen Controller, einen Service und verschiedene Models beinhalten.
Das Backend teilt sich dabei in die Überkategorien `User` und `Offer`.
Das Usermodul kümmert sich um alle Anfragen, die etwas mit Benutzern zu tun haben. Hier können Nutzer erstellt, geupdated, verifiziert und gelöscht werden.
Das Offermodul kümmert sich darum, dass Nutzer Angebote einstellen, ändern, suchen, löschen und buchen können. Zusätzlich kümmert es sich um den kompletten Verleihprozess.
Das Offermodul greift zur Verifizierung der Benutzer auf das Usermodul zu. So kann duplicated code vermieden werden und ein separation of concerns erreicht werden.
Beide Module besitzen gemeinsam verwendete Hilfsfunktionen, die die Kommunikation mit der Datenbank und das Schreiben und Lesen von Dateien von Festplattendaten ermöglichen. Die Hilfsfunktionen sind dabei statisch.
Statt Objekten werden Interfaces zum internen Datenaustausch verwendet, dadurch wird vermieden, dass Objekte bei jeder Benutzung neu instanziiert werden müssen.
Asynchrone Aufrufe werden mit dem Promise-Konzept gehandlet, da dies eine bessere Lesbarkeit bietet als Callbackfunctions.

Eine Besonderheit ist die Handhabung der Lokationen der Angebote:
Um zu gewährleisten, dass Nutzer nur Angebote in ihrer Nähe finden, sind die Angebote mit der Postleitzahl des Verleihers verknüpft.
Da es schwierig ist jedes Mal alle Distanzen zum Mieter neu zu berechnen, haben wir uns dazu entschieden, die Distanz von jeder Stadt zu jeder anderen Stadt vorher zu berechnen und in einer Tabelle abzuspeichern. Mit unseren ~13.000 Postleitzahlen erhalten wir daher eine Tabelle mit Distanzen mit ~169.000.000 Einträgen.
Die Suche durch diese Tabelle ist jedoch deutlich schneller (ein paar Millisekunden) als die Neuberechnung bei jeder Suche.
Um die Geokoordinaten der einzelnen Städte zu erhalten, wurde die Google Maps Geocoding API verwendet. Zu jeder Postleitzahl aus unserer Tabelle (die eigentlich zur Verifikation der Nutzereingaben dient) haben wir die Latitude und die Longitude mit der Google API gesucht.

### Die API
Für die Verbindung zum Frontend haben wir uns für einen REST-API entschieden.
Die HTTP-Methoden lassen sich optimal auf die CRUD-Methoden für relationale Datenbanken mappen, was ein einfacheres Verständnis der Vorgänge ermöglicht.
NestJs bietet zusätzlich für die Entwicklung von REST-APIs viele nützliche Features wie z.B. die Dekoratoren in den Controllern.
Das Error-Handling von NestJS ermöglicht es zudem leicht HTTP-Fehlercodes auszugeben. Eine ausführlichere Dokumentation der API kann in der [API Dokumentation](https://github.com/Multiflexxx/FlexRent/blob/master/API-Documentation.md) gefunden werden.
Wir haben uns gegen die Verwendung von Swagger in Verwendung mit NestJS entschieden, da bereits ein erster Versuch in Nutzung der Dokumentationsfunktion keine brauchbaren Ergebnisse lieferte.

## CI/CD
Sowohl das Frontend als auch das Backend verwenden GithubActions für einen automatisierten Deploymentprozess.
Bei einem Push auf unsere `releases`-Branches, wird jeweils eine GithubAction getriggert, die einen Endpoint auf unserem Server aufruft.
Der Server zieht dann einen pull von Github und kompiliert die App mit Flutter, bzw. die API mit NestJS.
Anschließend wird die App unter einem Link bereitgestellt bzw. die API mit den neuen Features bereitgestellt.

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
- Häufig wird der Leihvertrag auch als Gebrauchsüberlassung bezeichnet.
- Es liegt ein Mietvertrag vor, da es eine entgeltliche Verleihung eines Gegenstandes/ Sache ist. -> Mietgebühr
- Als allgemeine zivilrechtliche Rechtsgrundlage dient für Dienstleistungen der Dienstvertrag, bei dem nach § 611 BGB der Dienstverpflichtete gegen Vergütung Dienste jeder Art für den Dienstberechtigten erbringen soll. Es handelt sich um einen individualrechtlichen Austauschvertrag zwischen Auftraggeber und Auftragnehmer über die unabhängige oder abhängige Leistung eines Dienstes gegen ein Entgelt. Bei allen Dienstleistungen sind die Dienstleistungspflicht und die Vergütungspflicht vertragliche Hauptpflichten. Die Dienstleistung ist vom Dienstverpflichteten im Zweifel persönlich zu erbringen (§ 613 BGB). Diese persönliche Abhängigkeit trifft jedoch nicht auf gattungsmäßig umschriebene Tätigkeiten im Rahmen freier Dienstnehmer zu.

## Functional Requirements
Unsere Functional Requirements sind [hier](https://github.com/Multiflexxx/FlexRent/blob/master/Functional%20Requirements.md) zu finden.

## Das Logo
Unser Logo zeigt einen [Amethystglanzstar](https://de.wikipedia.org/wiki/Amethystglanzstar). Amethystglanzstare leben in Kolonien zusammen und sind gesellig.
Das Zusammenleben in der Kolonie beschreibt gut unser Appmodell. Damit repräsentiert unser Logo perfekt eine Gemeinschaft.
Zudem kann die Farbe Lila als Vereinigung der Gegensätze Blau und Rot verstanden werden ([Weitere Infos](https://alpina-farben.de/artikel/farbsymbolik-bedeutung-violett-lila/)). Unsere App bringt Mieter und Vermieter zusammen, welche sich auch gegensätzlich sind.
