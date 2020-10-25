# Funktionen FlexRent

## Mieter-Funktionalitäten
### Funktion 1
Hauptfunktionalität: Einsehen der Angebote
Beschreibung: Es sollen Angebote eingesehen werden können. Dafür soll ein Produkt mit einem Bild angezeigt werden können. Beim anklicken einer Übersicht soll auf eine Detailproduktseite weitergeleitet werden. Auf dieser soll nicht nur das Titelbild, sondern auch weitere Bilder angezeigt werden können, sowie weitere Informationen zu dem Produkt. Diese sind:
* Vollständiger Titel des Produkts
* Kategorie des Produkts
* Bilder des Produkts
* Standort des Produkts + Distanz zum Produkt
* Preis des Produkts (pro Tag)
* Verfügbarkeit des Produkts
* Beschreibung des Produkts
* Vermieter des Produkts
* Verifizierungsstatus des Vermieters
* Durchschnittliche Bewertung des Vermieters (siehe Vermieter spezifikationen)
* Ähnliche Produkte
* Versicherungsinformationen zu diesem Produkt

Der Ort des Produkts soll aus Datenschutzgründen nur grob angezeigt werden.
In der Übersicht/ in der Liste der Produkte sollte dabei jedoch nur diese Informationen angezeigt werden:

* Gekürzter Titel des Produkts
* (Kategorie des Produkts)
* Vermieter des Produkts
* Verifizierungsstatus des Vermieters
* Standort des Produkts
* Preis des Produkts (pro Tag)

### Funktion 2
Hauptfuntkionalität: Suchen nach einem Produkt/ einer Kategorie
Beschreibung: Auf der Hauptseite und der Kategorieseite sollte eine Suchleiste sein, mit der gesucht werden kann. Bei Eingabe eines Suchbegriffes sollen relevante Artikel angezeigt werden. Die Suche sollte dabei auf einen Suchradius begrenzt sein, der oben unter der Suchleiste eingestellt werden kann. Wird ein passender Artikel nicht gefunden, so soll nach ähnlichen Produkten gesucht werden oder eine Kategorie vorgeschlagen werden. Bereits gesuchte Begriffe sollen gespeichert und bei erneuter Eingabe vorgeschlagen werden. Auch sollen Vorschläge für noch nicht beendete Suchbegriffe angezeigt werden. Außerdem soll es eine Kategorieseite geben, auf welcher verschiedene Kategorien angezeigt werden. Wenn auf eine Kategorie geklickt wird, sollen nur Produkte dieser Kategorie angezeigt werden in einem Festgelegten umkreis, den der Benutzer oben festlegen kann.

### Funtkion 3
Hautpfunktionalität: Vorschläge / Home Seite
Beschreibung: Auf der Home/ Hauptseite der App sollen Vorschläge von Produkten zu finden sein. Dabei soll es mindestens 3 Kategorien geben. "Hot Right Now": Produkte aus Kategorien, in denen gerade viel gemietet wird. Diese Kategorie sollte nicht angezeigt werden, wenn nur wenig gemietet wird. "Featured": Hier werden Produkte angezeigt, dessen Anbieter eine besondere Markierung für ihr Produkt erworben haben. "Vorschläge": Hier sollen Produkte auf Kategorien vorgeschlagen werden, die auf Produkten basieren, die der Kunde bereits gemietet hat. Hat der Kunde noch nichts gemietet, so soll diese Kategorie nicht angezeigt werden. Es kann über weitere Kategorien nachgedacht werden, wie gesponserte Deals/ Rabatte/ Aktionen, oder eine Kategorie für neu hinzugefügte Produkte.

### Funktion 4
Hauptfunktionalität: Anfragestellung zur Miete eines Produkts
Beschreibung: Wenn ein Produkt ausgewählt wurde und man auf der Produktdetailseite ist, soll neben dem Preis eine Buchungsanfrage getätigt werden können. Hier soll ein Verfügbarkeitskalender präsentiert werden, in welchem der Kunde sehen kann, wann das Produkt verfügbar ist. Wenn der Benutzer einen Bereich ausgewählt hat, soll der insgesamte Preis unten angezeigt werden. Zum Kalender kann der Kunde nur kommen, wenn er angemeldet ist. Ein Produkt muss mindestens einen Tag gemietet werden, eine höchstgrenze gibt es nicht. Wenn der Kunde ein Datum gewählt und auf Buchen geklickt hat, muss der Kunde eine Zahlungsart angeben. Es kann nur digital bezahlt werden. Wenn alle informationen gesammelt sind, soll an den Vermieter eine Anfrage geschickt werden. Die Anfragen sollten für den Kunden einsehbar sein. Hier sollten dann auch weitere Informationen zu der Anfrage stehen.

### Funktion 5
Hauptfunktionalität: Mieten eines Produktes
Beschreibung: Wenn eine Mietanfrage eines Mieters vom Vermieter bestätigt wurde, soll eine Pop-Up Nachricht erscheinen. Außerdem soll eine bestätigte Buchungsanfrage angezeigt werden und eine Buchung erscheinen. (bzw. das soll umkonvertiert werden). Bei dieser Buchung sollen dann folgende Informationen stehen:
* Produktname
* Produktbeschreibung
* Produktbilder
* Genauer standort des Produkts, auf einer Karte sichtbar mit anbindung zu google maps/ apple maps
* Buchungsdauer, genaue daten
* Buchungspreis und Zahlungsart
* Vermieter mit Möglichkeit, ihn zu kontaktieren.
* Ein Button, mit dem man zur QR Code sektion kommt. 

### Funktion 6
Hauptfunktionalität: Abholung und Bezahlung eines Produkts
Beschreibung: Wenn ein Mieter eine Buchung durchgeführt hat, dann kann der Mieter zum Vermieter fahren, um das Produkt abzuholen und den Mietbetrag zu bezahlen. Wenn der Mieter vor Ort ist (oder auch vorher), kann der Mieter über die App bezahlen und somit einen QR Code freischalten. Dieser QR Code kann bei der Abholung benutzt werden, um dem Vermieter zu bestätigen, dass der Mieter bezahlt hat. Dieser QR Code kann als bestätigung vom Vermieter gescannt werden, um damit im System einzutragen, dass der Mieter den Gegenstand abgeholt hat und somit er in dem besitz des Mieters ist. Beide Teilnehmer erhalten eine Bestätigung, dass alles geklappt hat. Die Zahlung findet über PayPal oder ein anderes Online-Zahlungsmittel statt, eine Bargeldzahlung ist aus Betrugszwecken nicht erlaubt.

### Funktion 7
Hauptfunktionalität: Zurückgabe eines Produkts
Beschreibung: Nachdem die Mietdauer abgeschlossen ist, soll der Mieter eine Push Benachrichtigung bekommen, dass es Zeit ist, den Gegenstand zurück zu geben. Hier soll dem Mieter dann wieder in seiner Buchungsübersicht angezeigt werden, dass es Zeit ist, das Produkt zurückzugeben. Auch soll hier nochmal die Addresse angezeigt werden, an die zurück gegeben werden soll. Bei der Rückgabe treffen sich beide Teilnehmer noch einmal und der Mieter kann einen QR Code vom Vermieter scannen, um zu bestätigen, dass das Produkt zurück gegeben wurde. Erst dann ist die Buchung beendet und die Buchung wird in der Historie angezeigt. Von der historie aus kann man ggf nochmal auf die Produktseite zurück und seine ausgaben im überblick behalten.

### Funktion 8
Hauptfunktionalität: Bewertungsfunktion
Beschreibung: Nach einer Buchung kann der Mieter seine Erfahrungen zur Miete Bewerten. Einerseits wird diese Bewertung von Multiflexxx eingesehen anhand einiger platformspezifischer fragen, andererseits wird auch eine Bewertung für den Vermieter abgegeben. Diese summiert sich dann zu der gesamtbewertung. Auch der Vermieter kann dem Mieter eine Bewertung geben, was die durchschnittsbewertung/karma score des Mieters beeinflusst.

### Funktion 10
Hauptfunktionalität: Einstellungen treffen
Beschreibung: Der Benutzer soll einige Einstellungen treffen können. Diese Beinhalten:
* Meine Informationen
    * Profilbild
    * Name, Adresse
    * E-Mail, Passwort ändern
    * Handynummer
* Zahlungsinformationen
    * Zahlungsinformationen
* App-Einstellungen
    * Light-Mode/Dark-Mode
* Abmelden
    * Abmelden
    * Profil löschen
    
### Funktion 11
Hauptfunktionalität: Registrierung
Beschreibung: Ein Benutzer soll sich registrieren können. Dabei muss ein Benutzer seinen
* Vornamen
* Nachnamen
* Adresse
    * Straße
    * Hausnummer
    * Postleitzahl
    * Ort
    * Land (Nur Deutschland möglich)
* Telefonnummer
* E-Mail adresse
* Passwort

angeben. Anschließend kriegt er eine E-Mail, womit er seinen Account bestätigen kann. Um Buchen zu können, muss erst die Telefonnummer über SMS Bestätigt werden. Auch muss für eine Buchung ein Zahlungsmittel eingerichtet werden. Nach der Registrierung kann auch ein Profilbild hinzugefügt werden.

### Funktion 12
Hauptfunktionalität: Login
Beschreibung: Ein Benutzer soll sich einloggen können. Dabei muss er seine
* E-Mail oder Telefonnummer
* Passwort
* (optional) Passwort speichern

angegeben werden. Danach sollte der Nutzer eingeloggt bleiben.
