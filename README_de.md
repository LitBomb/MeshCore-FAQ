# MeshCore-FAQ
Eine Liste häufig gestellter Fragen und Antworten zu MeshCore

Die aktuelle Version dieser MeshCore-FAQ findest du unter https://github.com/ripplebiz/MeshCore/blob/main/docs/faq.md.

Diese MeshCore-FAQ ist auch unter https://github.com/LitBomb/MeshCore-FAQ abrufbar und kann aktualisiert werden, falls Pull Requests für Scotts MeshCore-Repo noch nicht genehmigt wurden.

Autor: https://github.com/LitBomb
---

## F: Was ist MeshCore?

**A:** MeshCore ist kostenlos und Open Source.
* MeshCore umfasst das Routing, die Firmware usw. und ist auf GitHub unter der MIT-Lizenz verfügbar.
* Es gibt von der Community entwickelte Clients, wie z. B. die Web-Clients. Diese sind kostenlos nutzbar, einige davon sind ebenfalls Open Source.
* Die plattformübergreifende mobile App von [Liam Cottle](https://liamcottle.net) für Android/iOS/PC usw. kann kostenlos heruntergeladen und genutzt werden.
* Die T-Deck-Firmware wurde von Scott von Ripple Radios, dem Entwickler von MeshCore, entwickelt und kann ebenfalls kostenlos auf deine Geräte geflasht und genutzt werden.

Einige erweiterte, aber optionale Funktionen sind auf dem T-Deck verfügbar, wenn du dein Gerät für einen Entsperrschlüssel registrierst. Auf den MeshCore-Smartphone-Clients für Android und iOS/iPadOS kannst du die Wartezeit für die Fernverwaltung von Repeatern und Raumservern über Funk abschalten.

Diese Funktionen sind völlig optional und für das grundlegende Messaging-Erlebnis nicht erforderlich. Diese Funktionen sind wie tolle Bonusfunktionen. Um die Entwickler bei der Weiterentwicklung dieser fantastischen Funktionen zu unterstützen, erheben sie möglicherweise eine geringe Gebühr für einen Freischaltcode zur Nutzung der erweiterten Funktionen.

Jeder kann auf MeshCore kostenlos beliebige Software erstellen.

## F: Was benötigst du für MeshCore?
**A:** Alles, was du für MeshCore benötigst, findest du hier:

Hauptwebsite: [https://meshcore.co.uk/](https://meshcore.co.uk/)

Firmware-Flasher: https://flasher.meshcore.co.uk/

Telefon-Client-Anwendungen: https://meshcore.co.uk/apps.html

MeshCore Firmware Github: https://github.com/ripplebiz/MeshCore

HINWEIS: Andy Kirby bietet ein sehr nützliches [Einführungsvideo](https://www.youtube.com/watch?v=t1qne8uJBAc) für Anfänger an.

Du benötigst LoRa-Hardware, um MeshCore-Firmware als Client oder Server (Repeater und Raumserver) auszuführen.

### Hardware
Um MeshCore ohne ein Telefon als Client-Schnittstelle zu nutzen, kannst due MeshCore auf einem T-Deck oder T-Deck Plus ausführen. Es ist eine umfassende, sichere Kommunikationslösung für netzunabhängige Anwendungen.

MeshCore ist auch auf verschiedenen 868-MHz- und 915-MHz-LoRa-Geräten verfügbar. Zum Beispiel RAK4631-Geräte (19003, 19007, 19026), Heltec V3, Xiao S3 WIO, Xiao C3, Heltec T114, Station G2 und Seeed Studio T1000-E. Weitere Geräte werden später unterstützt.

### Firmware
MeshCore bietet vier Firmware-Typen, die auf anderen LoRa-Systemen so nicht verfügbar sind. MeshCore bietet Folgendes:

#### Companion Radio Firmware
Companion Radios dienen zur Verbindung mit der Android-App oder Web-App als Messenger-Client. Es gibt zwei verschiedene Firmware-Versionen:

1. **BLE Companion**
Die BLE Companion-Firmware läuft auf einem unterstützten LoRa-Gerät und verbindet sich über BLE mit einem Smartgerät, auf dem der Android MeshCore-Client läuft (der iOS MeshCore-Client ist in Kürze verfügbar).
<https://meshcore.co.uk/apps.html>

2. **USB Serial Companion**
Die USB Serial Companion-Firmware läuft auf einem unterstützten LoRa-Gerät und verbindet sich über USB Serial mit einem Smartgerät oder Computer, auf dem der MeshCore-Webclient läuft.
<https://meshcore.liamcottle.net/#/>
<https://client.meshcore.co.uk/tabs/devices>

#### Repeater
Repeater dienen zur Erweiterung der Reichweite eines MeshCore-Netzwerks. Die Repeater-Firmware läuft auf denselben Geräten wie die Client-Firmware. Die Aufgabe eines Repeaters besteht darin, MeshCore-Pakete an das Zielgerät weiterzuleiten. Im Gegensatz zu anderen LoRa-Mesh-Systemen leitet er **nicht** jedes empfangene Paket weiter oder sendet es erneut. Ein Repeater kann über ein T-Deck mit MeshCore-Firmware und freigeschalteten Fernverwaltungsfunktionen oder über einen BLE Companion-Client, der mit einem Smartphone mit MeshCore-App verbunden ist, ferngesteuert werden.

#### Room server
Ein Room Server ist ein einfacher BBS-Server zum Teilen von Beiträgen. T-Deck-Geräte mit MeshCore-Firmware oder ein BLE Companion-Client, der mit einem Smartphone mit MeshCore-App verbunden ist, können sich mit einem Raumserver verbinden.

Raumserver speichern den Nachrichtenverlauf und senden ihn an die Nutzer. Nutzer, die sich nicht im Raum befinden, können später auf den Nachrichtenverlauf zugreifen. Anders als bei den Kanälen werden die Nachrichten gespeichert. Room-Server kannst du dir wie E-Mail-Server vorstellen, auf denen du später deine E-Mails abrufen kannst.

Ein Raumserver kann per Fernzugriff über ein T-Deck mit MeshCore-Firmware und freigeschalteten Fernverwaltungsfunktionen oder über einen BLE Companion Client, der mit einem Smartphone mit MeshCore-App verbunden ist, verwaltet werden.

Wenn sich ein Client bei einem Raumserver anmeldet, erhält er die zuvor nicht angezeigten 16 Nachrichten.

Ein Raumserver kann auch die Repeater-Funktion übernehmen. Um die Repeater-Funktion auf einem Raumserver zu aktivieren, verwende diesen Befehl 

`set repeat {on|off}`

## Ersteinrichtung

### F: Wie viele Geräte benötige ich für MeshCore?
**A:** Wenn du ein unterstütztes Gerät hast, aktualisiere die BLE Companion-Firmware und verwende das Gerät als Client. Du kanst dich über den Smartphone Client per Bluetooth mit dem Gerät verbinden. So kannst du mit anderen MeshCore-Nutzern in deiner Nähe kommunizieren.

Wenn du zwei unterstützte Geräte hast und sich nicht viele MeshCore-Nutzer in deiner Nähe befinden, aktualisiere beide auf die BLE Companion-Firmware, damit du mit deinen Freunden und deiner Familie in der Nähe kommunizieren kannst.

Wenn du zwei unterstützte Geräte haben und sich andere MeshCore-Nutzer in der Nähe befinden, kannst du eines deiner Geräte mit der BLE Companion-Firmware und das andere unterstützte Gerät mit der Repeater-Firmware aktualisieren. Platziere den Repeater hoch über dem Boden, um die Reichweite deines MeshCore-Netzwerks zu erweitern.

Nachdem du die neueste Firmware auf deinen Repeater geladen hast, lasse das Gerät sich über USB mit deinem Computer verbunden. Nutze die Konsolenfunktion des Web-Flashers und stelle die Frequenz für deine Region oder dein Land ein, damit dein Client den Repeater oder Raumserver per Funk fernsteuern kann:

`set freq {frequency}`

Die CLI-Referenz für Repeater und Raumserver findest du hier: https://github.com/ripplebiz/MeshCore/wiki/Repeater-&-Room-Server-CLI-Reference

Wenn du über weitere unterstützte Geräte verfügst, kannst du diese mit der Raumserver-Firmware nutzen.

### F: Kostet MeshCore etwas?

**A:** Alle Radio-Firmware-Versionen (z. B. für Heltec V3, RAK, T-1000E usw.) sind kostenlos und Open Source und wurden von Scott bei Ripple Radios entwickelt.

Der native Android- und iOS-Client nutzt das Freemium-Modell und wurde von Liam Cottle, dem Entwickler der meshtastic-Karte unter [meshtastic.liamcottle.net](https://meshtastic.liamcottle.net) auf [github ](https://github.com/liamcottle/meshtastic-map) und [reticulum-meshchat auf github](https://github.com/liamcottle/reticulum-meshchat), entwickelt.

Die T-Deck-Firmware kann kostenlos heruntergeladen werden, und die meisten Funktionen sind kostenlos verfügbar. Um den Firmware-Entwickler zu unterstützen, kannst du einen Registrierungsschlüssel erwerben, um dein T-Deck für tiefere Kartenzooms und die Remote-Serververwaltung über Funk freizuschalten.Eine Registrierung ist nicht erforderlich, um dein T-Deck für Direktnachrichten und die Verbindung mit Repeatern und Raumservern zu nutzen.

### F: Welche Frequenzen werden von MeshCore unterstützt?
**A:** Es unterstützt den 868-MHz-Bereich in Großbritannien / der EU und den 915-MHz-Bereich in Neuseeland, Australien und den USA. Länder und Regionen in diesen beiden Frequenzbereichen werden ebenfalls unterstützt. Die Firmware und der Client ermöglichen es Nutzern, ihre bevorzugte Frequenz einzustellen.

In Großbritannien und der EU ist die Nutzung der 250-kHz-Bandbreite auf 867,5 MHz nicht gestattet und es ist nur ein Arbeitszyklus von 2,5 % für Clients zulässig. 869,525 MHz ermöglicht eine Sendezeit von 10 %, eine Bandbreite von 250 kHz und eine höhere EIRP (Electronical Reach Rate), wodurch MeshCore-Knoten häufiger und mit mehr Leistung senden können. Deshalb wurde diese Frequenz für Großbritannien und die EU gewählt. Aus diesem Grund nutzt auch Meshtastic diese Frequenz. 

Empfehlung der Entwickler für Netze bis zu 40 Teilnehmern: 
Frequenz: `869,525 MHz, Bandbreite 250 kHz, Spreizfaktor 11, Coding Rate 5`. Bei Netzen über 40 Teilnehmer kann der Spreizfaktor dann bei allen (!) Teilnehmern auf 10 heruntergesetzt werden.


[Quelle](https://discord.com/channels/826570251612323860/1330643963501351004/1356540643853209641)
 
– Australien und Neuseeland nutzen **915,8 MHz**
– Großbritannien und die EU nutzen **869,525 MHz**
– Kanada und die USA nutzen **910,525 MHz**
– Für andere Regionen und Länder überprüfe bitte deine lokale LoRa-Frequenz.

Die restlichen Funkeinstellungen sind für alle Frequenzen gleich:
– Spread-Faktor (SF): 11
– Kodierungsrate (CR): 5
– Bandbreite (BW): 250,00

(Ursprünglich startete MeshCore mit SF 10. Seit Ende April 2025 empfiehlt die Community auch SF 11 als praktikable Option für Übertragungen mit größerer Reichweite, aber etwas langsameren Frequenzen. Aktuell gibt es MeshCore-Netze mit SF 10 und SF 11. Die Voreinstellungen der Smartphone-App empfehlen nun SF 10 für Australien und SF 11 für alle anderen Regionen und Länder. In der EU und Großbritannien gibt es Voreinstellungen für SF 10 und SF 11. Zukünftig könnte es Brückenknoten geben, die SF 10- und SF 11-Verkehr (oder sogar auf unterschiedlichen Frequenzen) überbrücken können.)

### F: Was ist ein „Advert“ in MeshCore?

**A:**
Advert bedeutet, sich im Netzwerk bekannt zu machen. Im Reticulum-Bereich bedeutet es eine Ankündigung. Im Meshtastic-Bereich bedeutet es, dass der Knoten seine Knoteninformationen sendet. MeshCore ermöglicht die manuelle Übertragung deines Namens, deiner Position und deines öffentlichen Verschlüsselungs Keys. Dieser ist zudem signiert, um Spoofing zu verhindern. Wenn du auf die Schaltfläche „Anzeige“ klickst, werden diese Daten über LoRa übertragen. MeshCore nennt dies advert. Es gibt zwei Möglichkeiten des advert: „Zero Hop“ und „Flood“.

* Zero Hop bedeutet, dass sie an alle Hörer gesendet wird.
* Flooded bedeutet, dass sie gesendet und anschließend von allen Repeatern, die sie hören, wiederholt wird.

MeshCore-Clients melden sich nur dann selbst an, wenn der Benutzer dies initiiert. Ein Repeater (und Raumserver?) meldet seine Anwesenheit alle 240 Minuten. Dieses Intervall kann mit folgendem Befehl konfiguriert werden:

`set advert.interval {minutes}`

### F: Gibt es ein Hop-Limit?

**A:** Die Firmware hat intern ein maximales Limit von 64 Hops. In der Praxis wird es aufgrund der Umgebung und des Timings schwierig sein, an das Limit heranzukommen, da Pakete immer größere Entfernungen zurücklegen. Wir möchten wissen, wie weit deine MeshCore-Kommunikation reicht.

---

## Serververwaltung

### F: Wie konfiguriert man einen Repeater oder einen Raumserver?
**A:** Einer dieser Server kann mit einer der folgenden Optionen verwaltet werden:
- Nachdem die Firmware eines Repeaters oder Raumservers auf ein LoRa-Gerät übertragen wurde, rufe <https://config.meshcore.dev> mit Chrome auf und verbinde dich über die Weboberfläche per USB-Seriell mit dem LoRa-Gerät. Dort kannst du den Namen des Servers, seine Frequenz und weitere zugehörige Einstellungen, Standort, Passwörter usw. festlegen.

![444798777-4c888b61-4f60-49f3-bef8-81592cd660c3](https://github.com/user-attachments/assets/ed3910ba-5110-4f72-ab98-a603cbbf134b)

- Wenn MeshCore zum ersten Mal auf ein LoRa-Gerät geflasht wird, muss die Frequenz des Servergeräts eingestellt werden, damit es die in deinem Land oder deiner Region zulässige Frequenz nutzt. Dies ist erforderlich, um die Frequenz des Servergeräts einzustellen, falls diese nicht mit der Frequenz deiner Region oder deines Landes übereinstimmt.
- MeshCore-Smart-Device-Clients können Server fernverwalten.
- Ein T-Deck mit freigeschalteter/registrierter MeshCore-Firmware. Die Fernverwaltung des Servers wird durch die Registrierung deines T-Decks bei Ripple Radios ermöglicht. Dies ist eine Möglichkeit, die MeshCore-Entwicklung zu unterstützen. Du kannst dein T-Deck hier registrieren:
<https://buymeacoffee.com/ripplebiz/e/249834>

### F: Muss ich den Standort eines Repeaters festlegen?
**A:** Wenn der Standort eines Repeaters festgelegt ist, kann dieser zukünftig auf einer MeshCore-Karte angezeigt werden. Lege den Standort mit den folgenden Befehlen fest:

`set lat <GPS Lat> set long <GPS Lon>`

Du kanst den Breiten- und Längengrad von Google Maps abrufen, indem du mit der rechten Maustaste auf deinen Standort auf der Karte klicken.

### F: Wie lautet das Passwort für die Verwaltung eines Repeaters oder Raumservers?
**A:** Das Standard-Administratorpasswort für einen Repeater und einen Raumserver lautet „password“. Verwende den folgenden Befehl, um das Administratorpasswort zu ändern:

`password {new-password}`

### F: Wie lautet das Passwort für den Beitritt zu einem Raumserver?
**A:** Das Standard-Gastpasswort für einen Raumserver lautet „hello“. Verwende den folgenden Befehl, um das Gastpasswort zu ändern:

`set guest.password {guest-password}`

---

## T-Deck

### F: Wie versetze ich ein T-Deck in den DFU-Modus (Device Firmware Update)?
**A:**
1. Gerät ausschalten
2. USB-Kabel an Gerät anschließen
3. Trackball gedrückt halten
4. Gerät einschalten
5. USB-Verbindungston hören
6. Trackball loslassen
7. Das T-Deck ist jetzt im DFU-Modus
8. Jetzt kannst du mit dem Flashen über <https://flasher.meshcore.co.uk/> beginnen.

### F: Warum empfängt mein T-Deck Plus keine Satellitenverbindung?
**A:** Beim T-Deck Plus sollte die GPS-Baudrate auf **38400** eingestellt sein. Außerdem wurde bei einigen T-Deck Plus-Geräten festgestellt, dass das GPS-Modul verkehrt herum eingebaut war, d. h. die GPS-Antenne zeigte nach unten statt nach oben. Wenn dein T-Deck Plus nach dem Einstellen der Baudrate auf 38400 immer noch keine Satellitenverbindung empfängt, mustt du das Gerät möglicherweise öffnen, um die GPS-Ausrichtung zu überprüfen.

GPS ist auf dem T-Deck immer aktiviert. Du kannst die GPS-Zeitsynchronisierung überspringen, und das T-Deck versucht weiterhin, eine GPS-Verbindung herzustellen. Gehe zum Bildschirm „GPS-Info“. Dort sollte der Zähler „Sätze:“ ansteigen, wenn die Baudrate korrekt ist.

[Quelle](https://discord.com/channels/826570251612323860/1330643963501351004/1356609240302616689)

### F: Warum empfängt mein OG (nicht Plus) T-Deck keine Satellitenverbindung?
**A:** Das OG (nicht Plus) T-Deck wird ohne GPS geliefert. Wenn du deinem OG T-Deck ein GPS hinzugefügt hast, lese bitte in der Bedienungsanleitung deines GPS nach, welche Baudrate erforderlich ist. Alternativ kannst du versuchen, eine Baudrate von 9600, 19200 usw. bis 115200 einzustellen, um zu sehen, welche funktioniert.

### F: Welche SD-Kartengröße unterstützt das T-Deck?
**A:** Nutzer hatten keine Probleme mit 16-GB- oder 32-GB-SD-Karten. Formatiere die SD-Karte im **FAT32**-Format.

### F: Wie erhalte ich Karten auf dem T-Deck?
**A:** Du benötigst Kartenkacheln (Tiles). Hier kannst du vorab heruntergeladene Kartenkacheln herunterladen (eine gute Möglichkeit, die Entwicklung zu unterstützen):
- <https://buymeacoffee.com/ripplebiz/e/342543> (Europa)
- <https://buymeacoffee.com/ripplebiz/e/342542> (USA)

Eine weitere Möglichkeit zum Herunterladen von Kartenkacheln ist die Verwendung dieses Python-Skripts, um die Kacheln in den gewünschten Gebieten zu platzieren:
<https://github.com/fistulareffigy/MTD-Script>

Es gibt auch ein modifiziertes Skript, das zusätzliche Fehlerbehandlung und parallele Downloads ermöglicht:
<https://discord.com/channels/826570251612323860/1330643963501351004/1338775811548905572>

Kartenkacheln für Großbritannien sind separat von Andy Kirby auf seinem Discord-Server erhältlich:
<https://discord.com/channels/826570251612323860/1330643963501351004/1331346597367386224>

### F: Wohin werden die Kartenkacheln verschoben?
Nachdem du die Kacheln heruntergeladen hast, kopiere den Ordner „\tiles“ in das Stammverzeichnis der SD-Karte deines T-Decks.

### F: Wie schalte ich den erweiterten Kartenzoom und die Serververwaltungsfunktionen auf dem T-Deck frei?
**A:** Du kannst die T-Deck-Firmware kostenlos herunterladen, installieren und nutzen. Einige Funktionen (Kartenzoom, Serververwaltung) werden jedoch erst nach dem Kauf eines Freischaltcodes für 10 $ pro T-Deck-Gerät freigeschaltet.
Freischaltseite: <https://buymeacoffee.com/ripplebiz/e/249834>

### F: Wie entziffert man den Diagnosebildschirm auf dem T-Deck?
 
**A:** Der Platz auf dem T-Deck-Bildschirm ist begrenzt, daher sind die Informationen etwas kryptisch. Format:
 
`{hops} l:{packet-length}({payload-len}) t:{packet-type} snr:{n} rssi:{n}`
 
Den Pakettyp findest du hier: [https://github.com/ripplebiz/MeshCore/blob/main/src/Packet.h#L19](https://github.com/ripplebiz/MeshCore/blob/main/src/Packet.h#L19 "https://github.com/ripplebiz/MeshCore/blob/main/src/Packet.h#L19")
 
    #define PAYLOAD_TYPE_REQ 0x00 // request (prefixed with dest/src hashes, MAC) (enc data: timestamp, blob) 
    #define PAYLOAD_TYPE_RESPONSE 0x01 // response to REQ or ANON_REQ (prefixed with dest/src hashes, MAC) (enc data: timestamp, blob) 
    #define PAYLOAD_TYPE_TXT_MSG 0x02 // a plain text message (prefixed with dest/src hashes, MAC) (enc data: timestamp, text) 
    #define PAYLOAD_TYPE_ACK 0x03 // a simple ack #define PAYLOAD_TYPE_ADVERT 0x04 // a node advertising its Identity 
    #define PAYLOAD_TYPE_GRP_TXT 0x05 // an (unverified) group text message (prefixed with channel hash, MAC) (enc data: timestamp, "name: msg") 
    #define PAYLOAD_TYPE_GRP_DATA 0x06 // an (unverified) group datagram (prefixed with channel hash, MAC) (enc data: timestamp, blob) 
    #define PAYLOAD_TYPE_ANON_REQ 0x07 // generic request (prefixed with dest_hash, ephemeral pub_key, MAC) (enc data: ...) 
    #define PAYLOAD_TYPE_PATH 0x08 // returned path (prefixed with dest/src hashes, MAC) (enc data: path, extra)
 
[Quelle](https://discord.com/channels/1343693475589263471/1343693475589263474/1350611321040932966)

### F: Der Ton des T-Decks ist zu laut?
### F: Kann man den Sound anpassen?

**A:** Man kann die Sounds des T-Decks anpassen, indem man einfach MP3-Dateien im Stammverzeichnis der SD-Karte ablegt. Dazu gehören beispielsweise „startup.mp3“, „alert.mp3“ und „new-advert.mp3“.

### F: Was ist die Funktion „Aus Zwischenablage importieren“ des T-Decks und gibt es eine Möglichkeit, Knoten manuell hinzuzufügen, ohne Werbung zu erhalten?

**A:** „Aus Zwischenablage importieren“ dient zum Importieren eines Kontakts über eine Datei namens „clipboard.txt“ auf der SD-Karte. Umgekehrt befindet sich die Funktion im Identitätsbildschirm, im Menü „Karte in Zwischenablage“. Diese schreibt in die Datei „clipboard.txt“, damit man sich selbst teilen kann (nennen wir diese „Biz-Karten“, die mit „meshcore://...“ beginnen).

---

## Allgemein

### F: Was sind BW, SF und CR?

**A:**

**BW steht für Bandbreite** – Breite des für die Übertragung genutzten Frequenzspektrums.

**SF steht für Spreizfaktor** – Wie weit soll sich die Kommunikation zeitlich ausbreiten?

**CR steht für Codierungsrate** – https://www.thethingsnetwork.org/docs/lorawan/fec-and-code-rate/
Eine Verdoppelung der Bandbreite (von BW125 auf BW250) ermöglicht die Übertragung von doppelt so vielen Bytes in der gleichen Zeit. Eine Verringerung des Spreizfaktors um eine Stufe (von SF10 auf SF9) ermöglicht die Übertragung von doppelt so vielen Bytes in der gleichen Zeit.

Ein niedrigerer Spreizfaktor erschwert dem Gateway den Empfang einer Übertragung, da es empfindlicher auf Rauschen reagiert. Vergleichbar ist dies mit zwei Personen, die sich an einem lauten Ort (z. B. einer Bar) unterhalten. Bei großer Entfernung muss man langsam sprechen (SF10), bei geringer Entfernung kann man jedoch schneller sprechen (SF7).

Es ist also ein Balanceakt zwischen Übertragungsgeschwindigkeit und Störfestigkeit.

### F: Leiten die MeshCore-Clients Nachrichten weiter?

**A:** Nein, MeshCore-Clients leiten keine Nachrichten weiter. Dies ist der Kern des Messaging-orientierten MeshCore-Designs. Dadurch wird verhindert, dass Geräte das Netz überlasten und endlose Kollisionen verursachen, sodass gesendete Nachrichten nicht empfangen werden.

Bei MeshCore leiten nur Repeater und Raumserver mit der Einstellung „Repeat on“ die Nachrichten weiter.
 

### F: Was passiert, wenn ein Knoten eine Route über einen mobilen Repeater lernt und dieser nicht mehr erreichbar ist?

**A:** Wenn du einen Knoten bisher über einen Repeater erreicht hast und dieser nicht mehr erreichbar ist, sendet der Client die Nachricht über den bestehenden (aber nun unterbrochenen) bekannten Pfad. Die Nachricht schlägt nach drei Versuchen fehl, und die App setzt den Pfad zurück und sendet die Nachricht beim letzten Versuch standardmäßig als Flood. Diese Funktion kann in den Einstellungen deaktiviert werden. Ist das Ziel direkt oder über einen anderen Repeater erreichbar, wird der neue Pfad verwendet. Alternativannst du den Pfad manuell festlegen, wenn du einen bestimmten Repeater kennst, der zum Erreichen des Ziels verwendet werden soll.

Wenn Benutzer häufig unterwegs sind und die Pfade unterbrochen werden, sehen sie lediglich, dass der Telefonclient erneut versucht, den Pfad wiederherzustellen, und greifen auf Flood zurück, um den Pfad wiederherzustellen.

### F: Wie findet ein Knoten einen Pfad zu seinem Ziel und verwendet ihn dann, um in Zukunft Nachrichten zu senden, anstatt jede gesendete Nachricht wie Meshtastic zu "flooden"?

Routen werden in der Kontaktliste des Absenders gespeichert. Wenn du eine Nachricht zum ersten Mal sendest, erreicht diese Ihr Ziel zunächst per Flood-Routing. Sobald dein Zielknoten die Nachricht empfängt, sendet er einen Zustellbericht mit allen Repeatern, die die ursprüngliche Nachricht durchlaufen hat, an den Absender zurück. Dieser Zustellbericht wird per Flood-Routing an dich, dem Absender, zurückgesendet und dient als Grundlage für zukünftige direkte Pfade. Beim Senden der nächsten Nachricht wird der Pfad in das Paket eingebettet und von Repeatern ausgewertet. Stimmen Hop und Adresse des Repeaters überein, wird die Nachricht erneut gesendet, andernfalls nicht, wodurch die Auslastung minimiert wird. 

[Quelle](https://discord.com/channels/826570251612323860/1330643963501351004/1351279141630119996)
 
### F: Senden öffentliche Kanäle immer im Flood-Modus? Senden private Kanäle immer im Flood-Modus?
 
**A:** Ja, Gruppenkanäle verlaufen von A nach B, es gibt also keinen definierten Pfad. Sie müssen fluten. Repeater können jedoch den Flood-Verkehr bis zu einem bestimmten Hop-Limit mit dem CLI-Befehl „set flood.max“ unterbinden. Repeater-Administratoren können die Regeln ihrer Repeater festlegen.
 
[Quelle](https://discord.com/channels/1343693475589263471/1343693475589263474/1350023009527664672)
 
### F: Wie lautet der öffentliche Schlüssel für den standardmäßigen öffentlichen Kanal?
 
**A:** Der Schlüssel der Smartphone-App ist im Hexadezimalformat:
 
` 8b3387e9c5cdea6ac9e5edbaa115cd72`
 
T-Deck verwendet den gleichen Schlüssel, aber in Base64
 
`izOH6cXN6mrJ5e26oRXNcg==`
 
Das dritte Zeichen ist der Großbuchstabe „O“, nicht die Null „0“.
 

[Quelle](https://discord.com/channels/826570251612323860/1330643963501351004/1354194409213792388)


### F: Ist MeshCore Open Source?
**A:** Der Großteil der Firmware ist kostenlos verfügbar. Bis auf die T-Deck-Firmware und Liams native mobile Apps ist alles Open Source.
- Firmware-Repository: <https://github.com/ripplebiz/MeshCore>

### F: Wie kann ich MeshCore unterstützen?
**A:** Gebe dein ehrliches Feedback auf GitHub und auf AndyKirbys Discord-Server <http://discord.com/invite/H62Re4DCeD>. Erzähle deinen Freunden und Communitys von MeshCore und helfe ihnen beim Einstieg in MeshCore. Unterstütze Scotts MeshCore-Entwicklung unter <https://buymeacoffee.com/ripplebiz>.

Unterstütze Liam Cottle bei der Entwicklung seines Smartphone-Clients, indem du die Warteschleife für die Serveradministration per In-App-Kauf freischalten.

Unterstütze Rastislav Vysoky (recrof) bei der Entwicklung seiner Flasher-Website und der Kartenwebsite über [PayPal](https://www.paypal.com/donate/?business=DREHF5HM265ES&no_recurring=0&item_name=If+you+enjoy+my+work%2C+you+can+support+me+here%3A&currency_code=EUR) oder [Revolut](https://revolut.me/recrof)

### F: Wie erstelle ich MeshCore-Firmware aus dem Quellcode?
**A:** Anleitungen findest du hier:
https://discord.com/channels/826570251612323860/1330643963501351004/1341826372120608769

Anleitung für MeshCore:

Installiere für Windows zuerst WSL und Python+pip über: https://plainenglish.io/blog/setting-up-python-on-windows-subsystem-for-linux-wsl-26510f1b2d80

(Linux, Windows+WSL) Im Terminal/Shell:

```
sudo apt update
sudo apt install libpython3-dev
sudo apt install python3-venv

```
Mac: python3 sollte bereits installiert sein.

Dann sollte es für alle Plattformen gleich sein:

```
python3 -m venv meshcore
cd meshcore && source bin/activate
pip install -U platformio
git clone https://github.com/ripplebiz/MeshCore.git 
cd MeshCore

```
Öffne die Datei platformio.ini und in `[arduino_base]` editiere die `LORA_FREQ=867.5`
speicher, und dann:

```
pio run -e RAK_4631_Repeater
```
dann findest du die Firmware unter `firmware.zip` in `.pio/build/RAK_4631_Repeater`

Andy hat auch ein Video zur Erstellung mit VS Code:
*Wie man Meshcore-Repeater-Firmware erstellt und flasht | Heltec V3*
<https://www.youtube.com/watch?v=WJvg6dt13hk> *(Link im Discord-Beitrag)*

### F: Gibt es weitere Open-Source-Projekte im Zusammenhang mit MeshCore?

**A:** Der MeshCore-Webclient und die MeshCore-JavaScript-Bibliothek von [Liam Cottle](https://liamcottle.net) sind Open Source und stehen unter der MIT-Lizenz.

Webclient: https://github.com/liamcottle/meshcore-web
Javascript: https://github.com/liamcottle/meshcore.js

### F: Unterstützt MeshCore ATAK?
**A:** ATAK ist derzeit nicht in MeshCores Roadmap enthalten.

Meshcore wäre für ATAK nicht optimal geeignet, da MeshCore-Clients keine Repeater-Funktion haben und für ATAK ein Repeater-Netzwerk benötigt wird.

Es gibt keinen stabilen Pfad, da alle Clients ständig zwischen Repeatern wechseln.

MeshCore-Clients müssten ihren Pfad ständig neu konfigurieren und den Datenverkehr im Netzwerk überfluten, was zu zahlreichen Kollisionen mit einem so gesprächigen System wie ATAK führen könnte.

Dies könnte sich in Zukunft ändern, wenn MeshCore eine Client-Firmware mit Repeatern entwickelt.

[Quelle](https://discord.com/channels/826570251612323860/1330643963501351004/1354780032140054659)

### F: Wie füge ich einen Knoten zur [MeshCore-Karte]([url](https://meshcore.co.uk/map.html)) hinzu?
**A:** Verbinde dich über die Smartphone-App mit einem BLE-Begleitfunkgerät.
- Um das mit deinem Smartphone verbundene BLE-Begleitfunkgerät zur Karte hinzuzufügen, tippe auf das Werbesymbol und anschließend auf „Anzeigen (In die Zwischenablage)“.
- Um einen Repeater oder Raumserver zur Karte hinzuzufügen, tippe auf die drei Punkte neben dem gewünschten Repeater oder Raumserver und anschließend auf „Teilen (In die Zwischenablage)“.
- Rufe die [MeshCore Map-Website]([url](https://meshcore.co.uk/map.html)) auf, tippe auf das Pluszeichen unten rechts und füge den meshcore://...-Blob ein. Tippe anschließend auf „Knoten hinzufügen“.

### F: Kann ich ein MeshCore-Device mit einem Raspberry Pi aktualisieren?
**A:** Ja.

Du musst Picocom auf dem Pi installieren.

`sudo apt install picocom`

Führe dann die folgenden Befehle aus, um den Repeater einzurichten.

```

picocom -b 115200 /dev/ttyUSB0 --imap lfcrlf

set name your_repeater_name
time epoch_time
password your_unique_password
set advert.interval 240
advert

```
Hinweis: Bei Verwendung eines RAK ist der Pfad höchstwahrscheinlich /dev/ttyACM0

Epochenzeiten findest du auf https://www.epochconverter.com/

Du kannst den Repeater auch mit esptool flashen. Dazu musst du esptool mit dem folgenden Befehl installieren:

`pip install esptool --break-system-packages`
 
Um die Firmware dann auf Heltec zu flashen, nutze das  .bin File from https://flasher.meshcore.co.uk/ (Link zum Herunterladen aller Firmware)
 
Für den Heltec:
`esptool.py -p /dev/ttyUSB0 --chip esp32-s3 write_flash 0x00000 firmware.bin`

Wenn du eine Visual Studio Code Build-Bin-Datei flashst, flashe mit dem folgenden Offset:

`esptool.py -p /dev/ttyUSB0 --chip esp32-s3 write_flash 0x10000 firmware.bin`

Für den Pi
Lade die Zip-Datei von der Online-Flasher-Website herunter und verwende den folgenden Befehl:

Hinweis: Erfordert den Befehl adafruit-nrfutil, der wie folgt installiert werden kann.
 
`pip install adafruit-nrfutil --break-system-packages`

```
adafruit-nrfutil --verbose dfu serial --package t1000_e_bootloader-0.9.1-5-g488711a_s140_7.3.0.zip -p /dev/ttyACM0 -b 115200 --singlebank --touch 1200
```
[Quelle](https://discord.com/channels/826570251612323860/1330643963501351004/1342120825251299388)
 
### F: Gibt es Projekte, die auf MeshCore basieren?
 
**A:** Ja. Siehe Folgendes:
 
#### meshcoremqtt
 
Ein Python-basiertes Skript zum Senden von Meshor-Debug- und Paketerfassungsdaten zur Analyse an MQTT
https://github.com/Andrew-a-g/meshcoretomqtt

#### MeshCore für Home Assistant
Eine benutzerdefinierte Home Assistant-Integration für MeshCore-Mesh-Funkknoten. Sie ermöglicht die Überwachung und Steuerung von MeshCore-Knoten über USB-, BLE- oder TCP-Verbindungen.
https://github.com/awolden/meshcore-ha
 
#### Python MeshCore
Bindings für den Zugriff auf Ihre MeshCore-Begleitfunkknoten in Python. 
https://github.com/fdlamotte/meshcore_py

#### meshcore-cli  
CLI-Schnittstelle zum MeshCore-Begleitradio über BLE, TCP oder seriell. Verwendet Pyton MeshCore (siehe oben).
https://github.com/fdlamotte/meshcore-cli
 
#### meshcore.js
Eine Javascript-Bibliothek zur Interaktion mit einem MeshCore-Gerät, auf dem die Companion-Radio-Firmware läuft
https://github.com/liamcottle/meshcore.js

---

## Fehlerbehebung

### F: Mein Client meldet, dass ein anderer Client, Repeater oder Raumserver zuletzt vor vielen Tagen gesehen wurde.
### F: Ein Repeater, Client oder Raumserver, den ich in meiner Erkennungsliste (auf dem T-Deck) oder Kontaktliste (auf einem Smart-Device-Client) erwarte, ist nicht aufgeführt.
**A:**
- Wenn dein Client ein T-Deck ist, ist möglicherweise die Uhrzeit nicht eingestellt (kein GPS installiert, keine GPS-Verbindung oder falsche GPS-Baudrate).
- Wenn du den Android- oder iOS-Client verwenden, zeigt der andere Client, Repeater oder Raumserver möglicherweise die falsche Uhrzeit an.

Du kannst die Epoch-Zeit unter <https://www.epochconverter.com/> abrufen und damit deine T-Deck-Uhr einstellen. Bei Repeatern und Raumservern kann der Administrator die Uhr über ein T-Deck fernsteuern (Uhrsynchronisierung) oder den Befehl „time“ in der seriellen USB-Konsole verwenden, während das Servergerät angeschlossen ist.

### F: Wie verbinde ich mich per BLE (Bluetooth) mit einem Repeater?
**A:** Du kannst keine Bluetooth-Verbindung zu einem Gerät mit Repeater-Firmware herstellen. Geräte mit der BLE-Companion-Firmware können über die Android-App per Bluetooth verbunden werden.

### F: Ich kann keine Bluetooth-Verbindung herstellen. Wie lautet der Bluetooth-Kopplungscode?

**A:** Der Standard-Bluetooth-Kopplungscode lautet „123456“.

### F: Mein Heltec V3 trennt ständig die Verbindung zu meinem Smartphone. Die Bluetooth-Verbindung kann nicht stabil gehalten werden.

**A:** Heltec V3 verfügt über eine sehr kleine Spulenantenne auf der Platine für WLAN- und Bluetooth-Verbindungen. Die Reichweite beträgt nur wenige Meter. Die Spulenantenne kann entfernt und durch ein 31-mm-Kabel ersetzt werden. Die Bluetooth-Reichweite wird durch diese Modifikation deutlich verbessert.

---
## Weitere Fragen:
### F: Wie aktualisiere ich die Firmware von Repeater und Room-Server drahtlos?

**A:** ONur nRF-basierte RAK4631- und Heltec T114-OTA-Firmware-Updates werden mit der nRF-Smartphone-App verifiziert. Lilygo T-Echo funktioniert derzeit nicht.
Du kannst die Firmware der Repeater und Room-Server über eine Bluetooth-Verbindung zwischen deinem Smartphone und deinem LoRa-Radio mithilfe der nRF-App aktualisieren.

1. Lade die ZIP-Datei für den jeweiligen Knoten vom Web-Flasher auf dein Smartphone herunter.
2. Melde dich im Telefon-Client als Administrator am Repeater an (Standardkennwort: „password“), um den Befehl „start ota“ an den Repeater oder Room-Server zu senden und das Gerät in den OTA-DFU-Modus zu versetzen.

![image](https://github.com/user-attachments/assets/889bb81b-7214-4a1c-955a-396b5a05d8ad)
1. „start ota“ kann über die USB-Seriell-Konsole auf der Web-Flasher-Seite oder über ein T-Deck gestartet werden.
4. Lade die nRF-App auf deinem Smartphone herunter, starte sie und suchen nach Bluetooth-Geräten.
5. Verbinde dich mit dem zu aktualisierenden Repeater / Room-Serverknoten.
1. Die nRF-App ist sowohl für Android als auch für iOS verfügbar.

**Android fährt nach dem iOS-Abschnitt fort:**

**iOS fährt hier fort:**
5. Nach erfolgreicher Verbindung wird ein „DFU“-Symbol angezeigt. ![Eingefügtes Bild 20250309173039](https://github.com/user-attachments/assets/af7a9f78-8739-4946-b734-02bade9c8e71)
erscheint oben rechts in der App

![Eingefügtes Bild 20250309171919](https://github.com/user-attachments/assets/08007ec8-4924-49c1-989f-ca2611e78793)

6. Scrolle nach unten, um die PRN-Nummer(n) zu ändern:

![Eingefügtes Bild 20250309190158](https://github.com/user-attachments/assets/11f69cdd-12f3-4696-a6fc-14a78c85fe32)

- Für T114 ändere die Anzahl der Pakete (PRN(s)) auf 8.
- Für RAK können es 10 sein, es funktioniert aber auch mit 8.

7. Klicke auf das DFU-Symbol ![Bild eingefügt 20250309173039](https://github.com/user-attachments/assets/af7a9f78-8739-4946-b734-02bade9c8e71), wähle den Dateityp zum Hochladen (ZIP) und wähle anschließend die ZIP-Datei aus, die du zuvor vom Web Flasher heruntergeladen haben.
8. Der Upload-Vorgang wird nun gestartet. Wenn alles gut geht, wird der Knoten zurückgesetzt und erfolgreich geflasht.

![Bild eingefügt 20250309190342](https://github.com/user-attachments/assets/a60e25d0-33b8-46cf-af90-20a7d8ac2adb)

**Die Android-Anleitung wird hier fortgesetzt:**
1. Tippe oben links in der **nRF Connect App** (Version 4.24.3 von der [Nordic Semiconductor GitHub Seite](https://github.com/NordicSemiconductor/Android-nRF-Connect/releases/tag/v4.24.3)) auf das 3-Balken-Hamburger-Menü, dann auf „Einstellungen“ und dann auf „nRF5 DFU-Optionen“.

![Android nRF Hamburger](https://github.com/user-attachments/assets/ea6dfeef-9367-4830-bd70-1441d517c706)

![Android nRF Einstellungen](https://github.com/user-attachments/assets/c63726bf-cecd-4987-be68-afb6358c7190)

![Android nRF DFU-Optionen](https://github.com/user-attachments/assets/b20e872f-5122-41d9-90df-0215cff5fbc9)

2. Ändere die Paketanzahl auf „10“ für RAK und „8“ für Heltec T114.

![Android nRF Paketanzahl](https://github.com/user-attachments/assets/c092adaf-4cb3-460b-b7ef-8d7f450d602b)

3. Kehre zum Hauptbildschirm zurück.
4. Dein LoRa-Gerät sollte sich bereits im DFU-Modus befinden.
5. Tippe auf Klicke auf „SCANNER“ und anschließend auf „SCANNEN“, um das zu aktualisierende Gerät zu finden. Tippe anschließend auf „VERBINDEN“.

![Android nRF Scanner Scan Connect](https://github.com/user-attachments/assets/37218717-f167-48b6-a6ca-93d132ef77ca)

6. Tippe oben links in der nRF Connect App auf das DFU-Symbol neben den drei Punkten.

![Android nRF DFU](https://github.com/user-attachments/assets/1ec3b818-bf0c-461f-8fdf-37c41a63cafa)

7. Wähle „Distributionspaket (ZIP)“ und klicke auf „OK“.

![Android nRF Distributionspaket (ZIP)](https://github.com/user-attachments/assets/e65f5616-9793-44f5-95c0-a3eb15aa7152)

8. Wähle die Firmware-Datei im ZIP-Format aus, die du zuvor vom MeshCore Web Flasher heruntergeladen haben. Das Update startet, sobald du auf die Datei tippst.

![Android nRF FW-Aktualisierung](https://github.com/user-attachments/assets/0814d123-85ce-4c87-90a7-e1a25dc71900)

9. Nach Abschluss des Aktualisierungsvorgangs wird die Verbindung des Geräts zur nRF-App getrennt und das LoRa-Gerät aktualisiert.

---
