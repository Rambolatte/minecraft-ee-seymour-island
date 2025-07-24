
---

### @flyoutOnly 1

# Automatischer Bergbau – Stufe 1

## Schritt 1

```template
player.onItemInteracted(BLAZE_ROD, function () {
})
```

Lass uns den Agenten verwenden, um einen Minenschacht nach vorne zu graben.
Versuche zunächst, den Block vor dem Agenten mit `||agent:agent destroy forward||` zu zerstören.
Füge deinen Code in den Abschnitt `||player: on item used||` ein und klicke dann mit deinem **Blaze Rod**, wenn du den Code ausführen möchtest.

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
agent.destroy(FORWARD)
})
```

## Schritt 2

Kombiniere das nun mit einem `||agent:agent move up||`-Befehl, gefolgt von einem weiteren
`||agent:agent destroy forward||`.
Kannst du deinen Agenten dazu bringen, die erste Spalte aus 3 Steinblöcken zu zerstören?

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
agent.destroy(FORWARD)
agent.move(UP, 1)
agent.destroy(FORWARD)
agent.move(UP, 1)
agent.destroy(FORWARD)
agent.move(UP, 1)
})
```

## Schritt 3

Es muss doch sicher eine bessere Möglichkeit geben, die gleiche Aktion 3-mal auszuführen,
anstatt denselben Code 3-mal zu schreiben?
Die Lösung: Schleifen!
Du kannst den Befehl `||loops:Repeat 3 times do||` (oder `||loops:for||` in Python) verwenden, um die enthaltenen Befehle
3-mal zu wiederholen.
Warum also nicht `||agent:agent destroy forward||` und `||agent:agent move up||`
in eine `||loops:Repeat 3 times do||`-Schleife einfügen?

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
for (let index = 0; index < 3; index++) {
    agent.destroy(FORWARD)
    agent.move(UP, 1)
}
})
```

## Schritt 4

Schließlich – kannst du mit dem, was du bisher gelernt hast, eine weitere `||loops:Repeat 7 times do||`-Schleife
(oder `||loops:for||` in Python) verwenden, um den restlichen Minenschacht bis zum
Goldblock am Ende auszugraben? Sobald du fertig bist, stelle sicher, dass dein Agent auf der Druckplatte
des Goldblocks zum Stehen kommt.

```package
seymour=github:gbaman/minecraft-ee-seymour-island
```
