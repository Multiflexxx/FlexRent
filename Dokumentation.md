 # Plattformen und Frameworks – Flexrent
 
# Inhaltsverzeichnis
1) [Idee](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#idee)
2) [Technologien](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#technologien)<br>
2.1) [Flutter](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#flutter)<br>
2.2) [Typescript](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#typescript)<br>
2.3) [NestJs](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#nestjs)<br>
2.4) [MariaDB](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#mariadb)<br>
2.5) [Google Geolocations API](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#google-geo-locations-api)<br>
3) [Frontend](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#frontend)<br>
3.1) [Repository](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#repository)<br>
4) [Backend](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#backend)<br>
4.1) [Repository](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#repository-1)<br>
4.2) [Verwendete Technologien](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#verwendete-technologien)<br>
4.3) [Vorgehen & Erklärungen](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#vorgehen-und-erk%C3%A4rungen)<br>
5) [Lizenz](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#lizenz)
6) [Ausblick für die Zukunft](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#die-zukunft-von-flexrent)
7) [Marketing](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#marketing)
8) [Rechtliches](https://github.com/Multiflexxx/FlexRent/blob/master/Dokumentation.md#rechtliche-grundlagen)


## Idee:
Du brauchst eine Bohrmaschine oder eine Musikbox aber nur für eine kurze Zeit brauchst sie nur dafür dann bist du auf Flexrent genau richtig. Wir wollen eine Plattform bieten auf der Gegenstände von Privatperson zu Privatperson zu vermietet werden können. Die Mobile App ermöglicht es den Nutzern Gegenstände zu vermieten und Gegenstände zu mieten. Dafür genügt die Erstellung eines Profils. 

FlexRent bietet einen Marktplatz für Privatpersonen, die selten genutzte Gegenstände leihen oder verleihen möchten. Durch FlexRent besteht die Möglichkeit Gegestände, die ansonsten verstauben, zu Geld zu machen. Eine teuere Heckenschere, die nur einmal im Jahr benötigt wird kann hier für andere Menschen angeboten werden. Andererseits können Nutzer Gegenstände die sie für einen bestimmten Zeitpunkt benötigen mieten und sparen sich das Geld für eine Neuanschaffung. 

Die App bietet das eanbieten und das leichte finden von Gegenständen in der Nähe. Die Vermieter können selbst Zeiträume bestimmen, an denen er den Gegenstand nicht benötigt. Zudem hat er die Möglichkeit den Preis, Bilder und eine Beschreibung des Gegenstandes anzufertigen. 

Diese Gegensände können von den Mietern gefunden werden. Vermieter erhalten Bewertungen von den Mietern. So haben Mieter die Möglichkeit zuverlässige Vermieter zu finden. 

Der Mietprozess wird durch die App vereinfacht gestaltet. Der Mieter sucht sich den passenden Gegenstand und startet eine Mietanfrage. Wenn der Vermieter diese Anfrage annimmt kann der Mieter den Gegenstand bei dem Vermieter abholen.  

In Flexrent wird die Kamera als Vorteil einer Mobilenanwendung verwendet, um QR Codes beim Abholen und Zurückbringen des Gegenstandes zu scannen. Damit stellen wir sicher, welche Person im Besitz des Gegenstandes ist, da beide Nutzer mit dem QR Code interagieren müssen. Beim Verleihen wird der QR Code auf der Seite des Mieters erzeugt. Der Vermieter Scannt diesen. Bei der Rückgabe ist es umgekehrt.  


## Technologien 
### Flutter 
### Typescript
### NestJs
### MariaDB
### Google Geo Locations API

## Frontend
### Repository
[Frontend Repository](https://github.com/Multiflexxx/client-flex-rent)

## Backend
### Repository
[Backend Repository](https://github.com/Multiflexxx/server-flex-rent)

### Verwendete Technologien
- NestJS für die Businesslogik
- MariaDB als Datenbank
- Google Geolocations API um die geokoordinaten der Postleitzahlen zu erlangen
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
Um die Geokoordinaten der einzelnen Städte zu erhalten wurde die Google Maps Geolocation API verwendet. Zu jeder Postleitzahl aus unserer Tabelle (die eigentlich zur Verifikation der Nutzereingaben dient) haben wir die Latitude und die Longitude mit der Google API gesucht.

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
