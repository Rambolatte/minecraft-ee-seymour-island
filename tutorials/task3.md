
---

### @flyoutOnly 1

# Automatischer Bergbau – Stufe 2

## Schritt 1

```template
player.onItemInteracted(BLAZE_ROD, function () {
})
```

In dieser Aufgabe musst du deinen Agenten verwenden, um **nur** das Eisenerz abzubauen!
Du musst vorsichtig sein – wenn du die umliegenden Steine abbaust, könnte die Mine einstürzen...

Wenn du bereit bist zu starten, klicke auf „Weiter“.

## Schritt 2

Der erste Schritt ist das Erkennen von Eisenerz. Wir beginnen damit, den Block unter dem Agenten zu überprüfen.
Füge zunächst ein `||logic:if then||`-Element hinzu, mit einem `||logic:0 = 0||`-Block darin.
Setze in den ersten Slot ein `||agent: agent inspect block down||`, um zu erkennen, welcher Block sich darunter befindet.
Vergleiche diesen auf der rechten Seite mit einem Eisenerzblock.
Füge innerhalb dieser If-Anweisung ein `||agent:agent destroy down||` hinzu.
Probiere nun deinen Code aus. Du kannst die Aufgabe jederzeit mit den Tasten rechts zurücksetzen.

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
if (agent.inspect(AgentInspection.Block, DOWN) == IRON_ORE) {
            agent.destroy(DOWN)
        }
})
```

## Schritt 3

Mit dem Code aus der vorherigen Übung – kannst du jetzt auch rechts prüfen und abbauen?
Platziere diesen Abschnitt in einem `||loops:repeat 3 times||`-Block und bewege den Agenten jedes Mal 1 Block nach oben.
Vergiss nicht, den Agenten anschließend wieder nach unten zu bringen.
Probiere deinen Code aus. Du kannst die Aufgabe jederzeit mit den Tasten rechts zurücksetzen.

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
        if (agent.inspect(AgentInspection.Block, DOWN) == IRON_ORE) {
            agent.destroy(DOWN)
        }
        for (let index = 0; index < 3; index++) {
            if (agent.inspect(AgentInspection.Block, RIGHT) == IRON_ORE) {
                agent.destroy(RIGHT)
            }
            agent.move(UP, 1)
        }
        agent.move(DOWN, 2)
})
```

## Schritt 4

Abschließend sollst du den gesamten Code in einen weiteren `||loops:repeat X times||`-Block einfügen.
Du musst zählen, wie viele Blöcke der Agent sich vorwärts bewegen muss.
Jetzt bist du auf dich allein gestellt – viel Erfolg!

(Denk daran: Du kannst jederzeit im Spiel die „Agent zurücksetzen“-Taste drücken, um es erneut zu versuchen.)

```ghost
player.onItemInteracted(BLAZE_ROD, function () {
    for (let index = 0; index < 8; index++) {
        if (agent.inspect(AgentInspection.Block, DOWN) == IRON_ORE) {
            agent.destroy(DOWN)
        }
        for (let index = 0; index < 3; index++) {
            if (agent.inspect(AgentInspection.Block, RIGHT) == IRON_ORE) {
                agent.destroy(RIGHT)
            }
            agent.move(UP, 1)
        }
        agent.move(DOWN, 2)
        agent.move(FORWARD, 1)
    }
})
```

```package
seymour=github:gbaman/minecraft-ee-seymour-island
```
