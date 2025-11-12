# ML Stop

Starte einen [Ereignis-Handler](/reference/event-handler) (den Teil des Programms, der ausgeführt wird, wenn etwas passiert). Dieser Handler wird ausgeführt, wenn sich die bevorzugte Aktion des ML-Modells zu der von Ihnen ausgewählten Aktion ändert.

```sig
ml.onStop(ml.event.Unknown, function () {
})
```

Wenn sich eine Aktion ändert, wird zunächst der Stopp-Ereignis-Handler für die vorherige Aktion ausgeführt, gefolgt vom Start-Ereignis-Handler für die nächste Aktion.

Wenn beispielsweise der Start-Ereignis-Handler Ihrer Aktion die Wiedergabe von Musik im Hintergrund startet, kannst du einen Stopp-Ereignis-Handler verwenden, um diese zu beenden.

## Parameter

- **Ereignis**: Eine der Aktionen, mit denen das maschinelle Lernmodell trainiert wurde. Der Sonderwert „unbekannt” steht für den Fall, dass keine Aktion eine Sicherheit über dem Erkennungsschwellenwert aufweist.

## Beispiel

In diesem Beispiel wird die Wiedergabe einer Melodie beendet, wenn die bevorzugte Aktion von „Klatschen“ zu einer anderen Aktion wechselt.

```blocks
ml.onStop(ml.event.Clapping, function () {
    music.stopMelody(MelodyStopOptions.All)
})
```

```package
machine-learning-help-stubs=github:calliope-edu/pxt-ml-help-stubs
machine-learning=github:calliope-edu/pxt-ml
```
