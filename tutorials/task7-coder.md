
---

### @flyoutOnly 1

# Labyrinth-Coder

## Schritt 1

```template
player.onItemInteracted(BLAZE_ROD, function () {
})
```

In dieser Aufgabe musst du deinen Agenten zur goldenen Druckplatte bringen. Klingt einfach, oder?...
Der Haken daran: Du kannst die Hindernisse auf dem Weg nicht sehen!
Dafür brauchst du einen Freund, der sich über dem Labyrinth positioniert –
mit dem Vorteil, unsichtbare Blöcke sehen zu können. Dieser wird dich führen.
Wenn du und dein Partner bereit seid, klickt auf „Weiter“.

## Schritt 2

Um deinen Agenten zu bewegen, kannst du den Befehl `||agent:agent move FORWARD||` verwenden.
Du kannst auch den Befehl `||agent:agent turn LEFT||` nutzen, wenn du möchtest.

Füge deinen Code in den Abschnitt `||player: on item used||` ein und klicke dann mit deinem
**Blaze Rod**, wenn du den Code ausführen möchtest.

Viel Glück!

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
agent.move(FORWARD, 1)
})
```

```ghost
agent.turn(LEFT)
```

```package
seymour=github:gbaman/minecraft-ee-seymour-island
```
