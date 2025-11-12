# ML wurde erkannt

Überprüfe, ob eine ML-Aktion die erkannte Aktion ist.

```sig
ml.isDetected(ml.event.Unknown)
```

Das ML-Modell aktualisiert seine ausgewählte Aktion mehrmals pro Sekunde. Diese Funktion gibt „true“ zurück, wenn die ausgewählte Aktion aktuell geschätzt wird. Verwenden Sie den booleschen Wert, um logische Entscheidungen in Ihrem Programm zu treffen.

Einige Programme lassen sich mit den Ereignisbehandlungsroutinen wenn ML gestartet“ und „wenn ML gestoppt“ einfacher schreiben.

## Parameter

- **Ereignis**: Eine der Aktionen, mit denen das maschinelle Lernmodell trainiert wurde. Der Sonderwert „unbekannt” steht für den Fall, dass keine Aktion eine Sicherheit über dem Erkennungsschwellenwert aufweist.

## Rückgaben

- Ein boolescher Wert, der „true“ ist, wenn die ML-Aktion die bevorzugte Aktion ist, und „false“, wenn die ML-Aktion nicht die bevorzugte Aktion ist.

## Beispiel

In diesem Beispiel wird ein Icon auf dem LED-Bildschirm angezeigt, wenn die geschätzte Aktion zum Zeitpunkt der Auswertung der bedingten Anweisung „Klatschen“ lautet.

```blocks
basic.forever(function () {
    if (ml.isDetected(ml.event.Clapping)) {
        basic.showIcon(IconNames.Yes)
    }
})
```
```package
machine-learning-help-stubs=github:calliope-edu/pxt-ml-help-stubs
machine-learning=github:calliope-edu/pxt-ml
```
