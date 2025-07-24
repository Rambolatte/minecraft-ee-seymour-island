
---

### @flyoutOnly 1

# Automatischer Bergbau – Stufe 3

## Schritt 1

```template
player.onItemInteracted(BLAZE_ROD, function () {
})
```

In dieser Aufgabe musst du deinen Agenten verwenden, um **nur** die Erze abzubauen!
Du musst vorsichtig sein – wenn du die umliegenden Steine abbaust, könnte die Mine einstürzen...

Diese Aufgabe ist eine **fortgeschrittene** Aufgabe – es wird dringend empfohlen, dass du zuerst Autominer 1 und 2 abgeschlossen hast!

WARNUNG – Diese Aufgabe enthält einen 50-Sekunden-Timer, der deinen Agenten nach 50 Sekunden zum Start zurücksetzt.

## Schritt 2

In dieser Aufgabe gibt es verschiedene Möglichkeiten, die Erzblöcke zu überprüfen.
Eine Möglichkeit ist die Verwendung einer Sammlung von `||logic: or ||`-Befehlen, die ineinander verschachtelt sind.
Alternativ dazu könnten wir dem Agenten anstelle der Blöcke, die er **abbauen soll**, mithilfe von `||logic: not ||` sagen, welche Blöcke er **nicht** abbauen soll.

Abgesehen davon liegt der Rest der Aufgabe bei dir. Das endgültige Programm wird dem aus Autominer 2 ähnlich sein.

```ghost
let bob = 0
player.onItemInteracted(BLAZE_ROD, function () {
if (false || false) {
    	
    }
bob = 2
    for (let index = 0; index < 8; index++) {
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
