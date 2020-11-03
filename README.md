# Countdown
## ~avatar avatar @unplugged
Einen Countdown oder Sanduhr mit dem @boardname@ programmieren lernen.


## ~ @unplugged
Lerne wie du Schleifen am @boardname@ nutzen kannst indem du einen einfachen Countdown programmierst.
Nachdem der Knopf A gedückt wurde soll ein Counddown ablaufen und sich die Anzeige auf dem @boardname@ nach und nach füllen.

## Schrit 1: Die LED Matrix ansteuern
Beginnen wir mit dem Block ``|input: wenn Knopf A gedrückt|`` welcher den Countdown Starten soll. Bevor der Countdown wirklich startet ist es gut den erstmal den  ``|basic: Bildschirminhalt löschen|`` diesen Block gibt es auch unter ``|basic: Grundlagen|``
Als nächstest nehmen wir aus dem Bereich ``|loops:Schleifen|`` den Block mit ``|loops: für Index von 0 bis 4 |`` Dieser kommt unter den Block ``|basic: Bildschirminhalt löschen|`` in diese Schlaufe können wir aus dem Bereich ``|led: Led|`` den Block ``|led: zeichne x 0 y 0|`` 
Schiebe jetzt noch die Variable ``|variables:Index|`` an die Stelle für den x-Wert. <br>
Hinweis eine ``|basic:pause|`` am Ende der Schleife lässt diese langsamer durchlaufen, damit unser Auge dem folgen kann.

```blocks
input.onButtonPressed(Button.A, function () {
    basic.clearScreen()
    for (let Index = 0; Index <= 4; Index++) {
        
            led.plot(Index, 0)
            basic.pause(1000)
        
    }
  
})
```

## Schritt 2: Die LED Matrix auch in y-Richtung ansteuern
Versuche nun in die Bisherige Schleife eine Weitere schleife zu schieben. Nehme ab jetzt die ``|variables:Variablen|`` ``|variables:x-Index|`` und ``|variables:y-Index|`` 
```blocks
input.onButtonPressed(Button.A, function () {
    basic.clearScreen()
    for (let xIndex = 0; xIndex <= 4; xIndex++) {
        for (let yIndex = 0; yIndex <= 4; yIndex++) {
            led.plot(xIndex, yIndex)
            basic.pause(1000)
        }
    }

})
```

## Schritt 3: Einen Signalton zum Schluss
Zum Abschluss kannst du noch aus dem Bereich ``|music:Musik|`` einen Ton abspielen lassen. Wenn du diesen Block unter die Schleifen schiebst sollte der Ton abgespielt werden wenn der Countdown komplett abgelaufen ist.

```blocks

input.onButtonPressed(Button.A, function () {
    basic.clearScreen()
    for (let xIndex = 0; xIndex <= 4; xIndex++) {
        for (let yIndex = 0; yIndex <= 4; yIndex++) {
            led.plot(xIndex, yIndex)
            basic.pause(1000)
        }
    }
    music.playTone(262, music.beat(BeatFraction.Whole))
})

```


> Diese Seite bei [https://r00b1nh00d.github.io/countdown/](https://r00b1nh00d.github.io/countdown/) öffnen

## Als Erweiterung verwenden

Dieses Repository kann als **Erweiterung** in MakeCode hinzugefügt werden.

* öffne [https://makecode.calliope.cc/](https://makecode.calliope.cc/)
* klicke auf **Neues Projekt**
* klicke auf **Erweiterungen** unter dem Zahnrad-Menü
* nach **https://github.com/r00b1nh00d/countdown** suchen und importieren

## Dieses Projekt bearbeiten ![Build Status Abzeichen](https://github.com/r00b1nh00d/countdown/workflows/MakeCode/badge.svg)

Um dieses Repository in MakeCode zu bearbeiten.

* öffne [https://makecode.calliope.cc/](https://makecode.calliope.cc/)
* klicke auf **Importieren** und dann auf **Importiere URL**
* füge **https://github.com/r00b1nh00d/countdown** ein und klicke auf Importieren

## Blockvorschau

Dieses Bild zeigt den Blockcode vom letzten Commit im Master an.
Die Aktualisierung dieses Bildes kann einige Minuten dauern.

![Eine gerenderte Ansicht der Blöcke](https://github.com/r00b1nh00d/countdown/raw/master/.github/makecode/blocks.png)

#### Metadaten (verwendet für Suche, Rendering)

* for PXT/calliopemini
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>