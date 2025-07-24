
---

### @flyoutOnly 1

# Mehrspieler-Schaltungen

```template
player.onItemInteracted(BLAZE_ROD, function () {

})
```

## Schritt 1

Bevor du beginnst, ist es wichtig, dass ein Freund im Raum neben dir ist,
um dir bei dieser Aufgabe zu helfen, da sie 2 Spieler erfordert!
Es wird außerdem empfohlen, dass du die Einzelspieler-Aufgabe zum Reparieren von Schaltungen abgeschlossen hast,
bevor du diese versuchst.
Sobald du bereit bist, klicke auf die „Weiter“-Taste.

## Schritt 2

In dieser Aufgabe müsst ihr gemeinsam einige Schaltungen im großen Maßstab reparieren.
Schau in den Schaltungsbereich hinunter. Es gibt 4 Quadranten, von denen du 2 reparieren musst
und dein Freund die anderen 2. Sie sind über die Mittellinie miteinander verbunden.
Der Redstone-Strom verläuft durch die mittleren Goldblöcke.
Beachte, dass du Redstone **nur** auf **grüne Smaragdblöcke** platzieren kannst.

## Schritt 3

Auch wenn du ein Programm schreiben könntest, das Anweisungen für jeden einzelnen Block enthält,
warum nicht einfach ein Programm bauen, das alle Smaragdblöcke scannt und dann Redstone platziert?
Beginnen wir damit, den Agenten mithilfe von `||agent:agent move left/right||`
in eine Ecke zu bewegen, um zu starten.

```blocks
agent.move(LEFT, 1)
```

## Schritt 4

Als Nächstes prüfen wir, ob sich unter dem Agenten ein Smaragdblock befindet.
Füge zunächst ein `||logic:if then||`-Element mit einem `||logic:0 = 0||`-Block darin hinzu.
Verwende im ersten Slot ein `||agent: agent inspect block down||`, um zu erkennen, welcher Block sich unter dem Agenten befindet.
Vergleiche diesen rechts mit einem Smaragdblock.

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
    agent.move(LEFT, 1)
    if (agent.inspect(AgentInspection.Block, DOWN) == EMERALD_BLOCK) {

    }
})
```

## Schritt 5

Innerhalb dieser If-Anweisung, wenn korrekt ein Smaragdblock erkannt wird,
soll der Agent mithilfe von `||agent:agent place down||` Redstone platzieren.
Nach der If-Anweisung soll sich der Agent dann 1 Block mit `||agent:agent move forward by 1||` vorwärts bewegen.

```blocks
player.onItemInteracted(BLAZE_ROD, function () {
    agent.move(LEFT, 1)
    if (agent.inspect(AgentInspection.Block, DOWN) == EMERALD_BLOCK) {
        agent.place(DOWN)
    }
    agent.move(FORWARD, 1)
})
```

## Schritt 6

Du hast jetzt alle grundlegenden Bausteine, die du brauchst, um diese Aufgabe abzuschließen.
Um die Menge an Code, die du schreiben musst, zu reduzieren, solltest du unbedingt `||loops:repeat X times||` ausprobieren –
das macht vieles einfacher.
Viel Erfolg!

```ghost
player.onItemInteracted(BLAZE_ROD, function () {
    agent.move(LEFT, 1)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 5; index++) {
            if (agent.inspect(AgentInspection.Block, DOWN) == EMERALD_BLOCK) {
                agent.place(DOWN)
            }
            agent.move(FORWARD, 1)
        }
        agent.move(BACK, 5)
        agent.move(RIGHT, 1)
    }
})
```

```package
seymour=github:gbaman/minecraft-ee-seymour-island
```
