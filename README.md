# Countdown
## ~avatar avatar @unplugged
![Sanduhr](https://github.com/r00b1nh00d/Sanduhr/blob/master/Sanduhr.gif?raw=true) <br>
Lerne in diesem Tutorial einen Countdown oder eine Sanduhr mit dem Calliope zu programmieren.


## ~ @unplugged
Lerne, wie du Schleifen am @boardname@ nutzen kannst, indem du einen einfachen Countdown programmierst.
Nachdem der Knopf A gedrückt wurde, soll ein Counddown ablaufen und sich die Anzeige auf dem @boardname@ nach und nach füllen.

## Schritt 1: Die LED Matrix ansteuern
Beginnen wir mit dem Block ``||input: wenn Knopf A gedrückt||``, welcher den Countdown starten soll. Bevor der Countdown wirklich startet, ist es gut, erstmal den  ``||basic: Bildschirminhalt zu löschen||``. Diesen Block gibt es auch unter ``||basic: Grundlagen||``.
Als nächstes nehmen wir aus dem Bereich ``||loops:Schleifen||`` den Block ``||loops: für Index von 0 bis 4 ||``. Dieser kommt unter den Block ``|basic: Bildschirminhalt löschen|``. In die For-Schleife können wir aus dem Bereich ``||led: LED||`` den Block ``||led: zeichne x 0 y 0||`` schieben.
Schiebe jetzt noch die Variable ``||variables:Index||`` an die Stelle für den x-Wert. <br>
**Hinweis:** Eine ``||basic:Pause||`` am Ende der Schleife lässt diese langsamer durchlaufen, damit unser Auge dem folgen kann.

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
Versuche nun in die bisherige Schleife eine weitere Schleife zu schieben. Nehme ab jetzt die ``||variables:Variablen||`` ``||variables:x-Index||`` und ``||variables:y-Index||``. 
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
Zum Abschluss kannst du noch aus dem Bereich ``||music:Musik||`` einen Ton abspielen lassen. Wenn du diesen Block unter die Schleifen schiebst, sollte der Ton abgespielt werden, wenn der Countdown komplett abgelaufen ist.

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

## ~ @unplugged 

Es ist geschafft, dein Countdown sollte nun jede Sekunde eine weitere LED auf der Anzeige am Calliope anschalten und am Ende einen Ton abspielen, der signalisiert, dass der Countdown abgelaufen ist.



#### Dieses Tutorial verwenden
Um dieses Tutorial zu verwenden, muss der Link [https://makecode.calliope.cc/#tutorial:https://github.com/r00b1nh00d/Countdown] in das Adressfeld des Browsers kopiert werden.

#### Metadaten (verwendet für Suche, Rendering)

* for PXT/calliopemini
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>

