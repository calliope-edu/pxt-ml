# eine ML-Unterbrechung

Initialisiere einen Ereignis-Handler (Teil des Programms, der ausgeführt wird, wenn etwas passiert). Dieser Handler wird ausgeführt, wenn sich die vom ML-Modell vorhergesagte Aktion zu der von dir ausgewählten Aktion ändert.

```sig
ml.onStopDetailed(ml.event.Unknown, function (duration) {
})
```

Wenn sich eine Aktion ändert, wird zunächst der Stopp-Ereignis-Handler für die vorherige Aktion ausgeführt, gefolgt vom Start-Ereignis-Handler für die nächste Aktion.

Wenn beispielsweise der Start-Ereignis-Handler der Aktion die Wiedergabe von Musik im Hintergrund startet, kannst du einen Stopp-Ereignis-Handler verwenden, um diese zu beenden.

Der Ereignis-Handler erhält einen Parameter „Dauer”. Die Dauer ist die [Anzahl](/types/Anzahl der Millisekunden, seit diese Aktion zur bevorzugten Aktion geworden ist. Du kannst den Parameter „Dauer” in dem Programm verwenden, indem du ihn beispielsweise anzeigst oder eine Variable verwendest, um eine kumulierte Summe zu speichern.

## Parameter

- **Ereignis**: Eine der Aktionen, mit denen das maschinelle Lernmodell trainiert wurde. Der Sonderwert „unbekannt” steht für den Fall, dass keine Aktion eine Sicherheit über dem Erkennungsschwellenwert aufweist.

## Beispiel

Dieses Beispiel zeigt auf dem LED-Bildschirm in Sekunden an, wie lange die geschätzte Aktion „Applaus“ gedauert hat, wenn die geschätzte Aktion von „Applaus“ zu einer anderen Aktion wechselt.

```blocks
ml.onStopDetailed(ml.event.Clapping, function (duration) {
    basic.showNumber(duration / 1000)
})
```
```package
machine-learning-help-stubs=github:calliope-edu/pxt-ml-help-stubs
machine-learning=github:calliope-edu/pxt-ml
```