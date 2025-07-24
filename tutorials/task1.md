
---

### @flyoutOnly 1

# Reparatur der Schaltung

## Schritt 1

```template
player.onItemInteracted(BLAZE_ROD, function () {
})
```

In dieser Aufgabe musst du die Redstone-Schaltung reparieren. Die fehlenden Teile sind unten mit grünen Blöcken markiert.
Dein Agent hat genug Redstone zur Verfügung, um diese Reparatur durchzuführen.
Füge deinen Code in den Abschnitt `||player: on item used||` ein und klicke dann mit deinem **Blaze Rod**, wenn du den Code ausführen möchtest.
Drücke die **Weiter**-Taste, um fortzufahren.

## Schritt 2

Zuerst müssen wir unseren Agenten zu den beschädigten Bereichen bringen (markiert mit grün).
Versuche, mit den Befehlen `||agent:agent move forward||` und `||agent:agent turn left/right||` den Agenten über einen der grünen Blöcke zu bewegen.

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 2)
})
```

## Schritt 3

Jetzt platziere Redstone mit `||agent:agent place down||` auf einem grünen Block, um diesen Teil der Schaltung zu reparieren.

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
    agent.place(DOWN)
})
```

## Schritt 4

Bewege jetzt deinen Agenten rückwärts und platziere Redstone auf den anderen grün markierten Blöcken.
Wenn du feststeckst oder neu starten möchtest, drücke die Reset-Taste an der Wand.

```package
seymour=github:gbaman/minecraft-ee-seymour-island
```
