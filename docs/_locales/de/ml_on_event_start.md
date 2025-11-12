# Beginnen mit ML

Initialisiere einen Ereignis-Handler (Teil des Programms, der ausgeführt wird, wenn etwas passiert). Dieser Handler wird ausgeführt, wenn sich die bevorzugte Aktion des ML-Modells zu der von Ihnen ausgewählten Aktion ändert.

```sig
ml.onStart(ml.event.Unknown, function () {
})
```

Das ML-Modell aktualisiert seine geschätzte Aktion mehrmals pro Sekunde, aber dieser Ereignis-Handler wird nur ausgeführt, wenn sich die geschätzte Aktion ändert.
## Parameter

- **Ereignis**: Eine der Aktionen, mit denen das maschinelle Lernmodell trainiert wurde. Der Sonderwert „unbekannt” steht für den Fall, dass keine Aktion eine Sicherheit über dem Erkennungsschwellenwert aufweist.

## Beispiel

Dieses Beispiel spielt eine Hintergrundmelodie ab, wenn die Aktion „Klatschen“ eine Sicherheit über dem Erkennungsschwellenwert aufweist.

```blocks
ml.onStart(ml.event.Clapping, function () {
    music._playDefaultBackground(music.builtInPlayableMelody(Melodies.Dadadadum), music.PlaybackMode.InBackground)
})
```

```package
machine-learning-help-stubs=github:calliope-edu/pxt-ml-help-stubs
machine-learning=github:calliope-edu/pxt-ml
```
