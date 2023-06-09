# ATLAB - Use Case - Klient Gerald
erstellt von Milena Marjanovic

## Aufgabenstellung 
Gerald lebt mit einer starken körperlichen Behinderung und einer Hörschädigung, die ihm eine gewisse Pflegebedürftigkeit aufbürdet. Trotzdem möchte er gerne ein Stück Autonomie in seinem Leben zurückgewinnen, indem er seine Umgebung selbstständig steuern kann. Dazu zählen beispielsweise das Licht in seiner Wohnung, die Jalousien oder auch Musik hören.


## Vorhandene Funktionen
- rechter Arm leicht heben/senken (keine Handfunktion)
- Kopf
- Augen
- Non-Verbal
- Wahrnehmung von Klängen
- Mund, Lippen, Saugen, Pusten
- große Zehe links

## Wunsch
### Umgebungssteuerung
- Steuerung Licht
- Steuerung Jalousien
- Webradio

## Lösung
Gerald kann durch die Steuerung mithilfe der Kameramaus seinen Computer bedienen. Dadurch kann er seine Umgebung steuern und sich über das Webradio entertainern lassen.

## Verwendete Komponenten 
### Asterics Runtime Environment(ARE)  
Das Asterics Environment erlaubt es dem Asterics Grid, auf OpenHab zuzugreifen, um die Umgebungssteuerung zu übernehmen.

### Asterics Configuration Suit(ACS)
Hier verbindet man die notwendigen Komponenten und findet unter Suche auch vorgefertigte Modelle.

### Asterics Grid
Dient zur Umgebungssteuerung

Ein visuelles Bedienpult ermöglicht den Zugriff auf die Bereiche:

- Licht an/aus
- Jalousien rauf/runter
- Musik (Webradio)

### OpenHab (open Home Automation Bus)
Die Plattform  dient als zentraler Hub, und ermöglicht die Steuerung der Geräte wie Lampen und Jalousien, die im OpenHab-Server des Labors integriert sind. Dank der Integration in das Aserics Grid und der ARE ist es möglich, die Umgebung unkompliziert zu regeln. 


## Eingabegeräte
 - Kamera Steuerung
 
  Wie die Steuerung funktioniert findet man unter dem Link:https://www.asterics.eu/customize/model/Model-Creation.html#camera-mouse-simple
  Wenn man länger auf ein Feld bleibt wird die Aktion ausgeführt und die Sprachassistentin ist ebenso zu hören.Zusätzlich habe ich beim Radio die Möglichkeit die Lautstärke zu ändern.
 
## Vorbereitung
- Runterladen von den für die Aufgabe benötigten Programme laut Anleitung auf Moodle : Asterics Grid, Asterics Configuration Suite und ARE sowie OpenHab.

##  Durchführung 
### ARE und ACS
Mein erster Schritt war es für die Webcam-Steuerung ein ARE-Modell zu bauen. Im Suchfeld findet man die dafür benötigten Components und verbindet diese.
Man öffnet das ARE und connected diese anschließend drückt man den Button "Start Model".


![Bild verkleinert ARE UND ASC](https://user-images.githubusercontent.com/119931993/227784594-197697e2-58d9-4f24-842f-b98922c23810.png)



![Screenshot ARE und ACS-min](https://user-images.githubusercontent.com/119931993/227783977-2da875d2-8cb2-4cc9-afd7-f930010e60b1.png)


Damit man im Anschluss problemlos das Asterics Grid bedienen kann, muss man in ACS den richtigen Hostname eingeben (FH:openhabian, port 8080) des Weiteren muss ACS und ARE im Hintergrund laufen. Man gibt auch im Webbrowser openhabian 8080 ein, um zur Website zu gelangen.


ARE ermöglicht uns Befehle vom Asterics Grid an die verarbeitenden Endstellen ( hier:OpenHab Server).Es ist die Schnittstelle zwischen Nutzer und dem verarbeitenden Programm.


### Asterics Grid 
Ein personalisiertes Asterics -Grid kann Gerald über ein visuelles Bedieninpult mit Bildern die Lichter ein- und ausschalten, Jalousien rauf und runter fahren sowie bei 40% lassen. Zur Unterhaltung kann er zum Webradio wechseln und dort zu unterschiedlichen Sendern wechseln.Die Sprachassistentin wird ebenso aktiv beim aktivieren eines Feldes gesteuert durch die Webcam. 


![Asterics Grid](https://user-images.githubusercontent.com/119931993/227795141-904cad2d-e6a6-4fcb-b9fb-c5f33458d231.png)


Mit einem Rechtsklick auf das leere Feld habe ich zum bereits bestehenden Grid navigiert.



![Navigation zum readio](https://user-images.githubusercontent.com/119931993/227804687-a97b7746-9f54-4c71-b50c-d9aaf09f098c.png)


Man wählt eins aus und drückt auf ok.


![image](https://user-images.githubusercontent.com/119931993/227795614-9a1d5389-ed34-40a7-9db1-e7b879f3ea3c.png)
(Optionale Möglichkeit:Sprachänderung)


![asterics  Aktionen](https://user-images.githubusercontent.com/119931993/227800151-418b8f5a-564a-4206-9e5d-0fde9dd32139.png)


Nachdem man Download von ARE gedrückt hat gibt man dem Port "Action String "ein und dann das gewünschte Ziel zb.:mit @openhabian:Kueche1_KNX_Licht_Schalten, ON  oder OFF für aus.

Die Liste der verwendeten Parameter sieht für die Küche folgendermaße aus:
- Licht

 Esstisch Licht (Switch): Kueche1_KNX_Licht_Schalten

- Jalousien

Küchen Jalousien hoch, runter (Rollershutter, UP, DOWN, 40): Kueche_Jalousien 

Nachdem man diese Einstellungen vorgenommen hat erscheinen die in der ACS in Properties unter item 1,item 2 usw.


### Video zu HCI:siehe Workspace

