
---

### @flyoutOnly 1

# Teppichbauer

```template
player.onItemInteracted(BLAZE_ROD, function () {
})

```

# 8. Teppich bauen

## Einleitungsschritt @unplugged

# Teppich bauen

![Meet-Agent](https://github.com/gbaman/minecraft-ee-seymour-island/raw/master/media/carpet.gif)

## Schritt 2

In dieser Aufgabe musst du deinen Agenten benutzen, um einen Teppich zu bauen, der den Mustern in jedem der 4 vorgegebenen Bereiche folgt.
Dazu verwenden wir Listen/Arrays, um eine Kopie des Teppichs zu "speichern" und diese dann Zeile für Zeile abzuspielen, um das gewünschte Design zu erstellen.
Drücke den Weiter-Button, um zu starten!

## Schritt 3

Zuerst erstellen wir eine leere Liste/ein leeres Array. Verwende den Befehl `||Arrays:set list to||` und entferne mit dem Minus-Button die Standardinhalte (1 und 2) aus der Liste/dem Array.
Du kannst den Namen der Liste auch jetzt von `list` in einen anderen Namen ändern.
Zum Beispiel könntest du `floor` verwenden.
Denk daran, dass du jederzeit den **Reset Agent and Task**-Knopf an der Wand drücken kannst.

## Schritt 4

Da wir jetzt einen Ort haben, um die Block-IDs unter dem Agenten zu speichern, fangen wir an, die Liste/das Array zu füllen.
Benutze den Befehl `||Agent: agent inspect block below||`, damit der Agent den Block unter sich überprüft. Dann füge mit `||Arrays: add value to end||` die Block-ID am Ende der Liste an.

## Schritt 5

Wir können jetzt zum nächsten Block wechseln, indem wir uns mit `||Agent:agent move left by 1||` nach links bewegen.

## Schritt 6

Kannst du jetzt eine `||Loops:repeat times do||`-Schleife hinzufügen, um alle 5 Blöcke zu scannen, ohne den Code mehrfach kopieren/einfügen zu müssen?
Achte darauf, das Array nicht bei jeder Wiederholung zurückzusetzen, es sollte nur einmal am Anfang als leeres Array eingerichtet werden!
Vergiss auch nicht, den Agenten nach dem Scannen aller Blöcke wieder an die Startposition zurückzubringen.

## Schritt 7

Jetzt ist es Zeit, die Blöcke zu platzieren. Du kannst den Befehl `||Agent:place floor block with||` benutzen, um einen Block abzulegen, aber zuerst brauchen wir die Block-IDs. Um sie einzeln zu bekommen, verwende die `||Loops:for element in value of list||`-Schleife nach all dem, was wir bisher gemacht haben.
Dann kannst du `value` innerhalb von `||Agent:place floor block with||` verwenden.

Vergiss nicht, innerhalb der Schleife auch `||Agent:agent move left by 1||` zu setzen, damit der Agent zum nächsten Feld geht!

## Schritt 8

Jetzt, wo du ein Programm zum Bodenbauen hast, solltest du es mit einer weiteren `||Loops:repeat times do||`-Schleife erweitern, um das Viertel fertigzustellen.
Anschließend positioniere deinen Agenten mit den Befehlen `||Agent:agent move||` und `||Agent:agent turn||` am Anfang des nächsten Viertels, um den Code erneut auszuführen.

---

```package
seymour=github:gbaman/minecraft-ee-seymour-island
```
