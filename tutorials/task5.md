
---

### @flyoutOnly 1

# Fischsammler

## Schritt 1

```template
player.onItemInteracted(BLAZE_ROD, function () {
})
```

In dieser Aufgabe müssen wir Clownfische und Kugelfische vom Schiff auf den Steg bringen.
Zuerst aber wollen wir ein paar Fische einsammeln. Verwende den Befehl `||agent:agent move forward 2||`,
um deinen Agenten über einen Fischsammelpunkt zu bewegen.
Benutze dann den Befehl `||agent:agent collect CLOWNFISH||`, um zunächst nur Clownfische einzusammeln.
Füge deinen Code in den Abschnitt `||player: on item used||` ein und klicke dann mit deinem **Blaze Rod**, wenn du den Code ausführen möchtest.

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
agent.move(LEFT, 1)
agent.move(FORWARD, 2)
agent.collect(CLOWNFISH)
})
```

## Schritt 2

Nachdem nun einige Clownfische gesammelt wurden, wollen wir auch Clownfische von den anderen Sammelpunkten holen.
Warum versuchst du nicht, deinen Code in eine `||loops:Repeat 3 times loop||` (oder `||loops:for loop||` in Python) zu setzen?

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
agent.move(LEFT, 1)
for (let index = 0; index < 3; index++) {
    agent.move(FORWARD, 2)
    agent.collect(CLOWNFISH)
}
})
```

## Schritt 3

Da du nun alle Clownfische gesammelt hast, schreibe als Nächstes ein Programm, das deinen Agenten
zum richtigen Abgabeort auf dem Steg bringt, und verwende den Befehl `||agent:agent drop all down||`,
um alle Fische in den Eimer zu werfen.

```ghost
agent.dropAll(FORWARD)
```

## Schritt 4

Versuche, das Ganze in eine `||loops:Repeat times loop||` zu setzen,
damit dein Agent Fische wiederholt sammelt und abliefert.

## Schritt 5

Zum Schluss: Wiederhole denselben Vorgang für Kugelfische.
Es wird empfohlen, dies separat durchzuführen.

```package
seymour=github:gbaman/minecraft-ee-seymour-island
```
