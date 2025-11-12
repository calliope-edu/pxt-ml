# Wahrscheinlichkeit (%) ML

Ruft den aktuellsten Wahrscheinlichkeitswert für eine ML-Aktion ab.

```sig
ml.getCertainty(ml.event.Unknown)
```

Das ML-Modell wird mehrmals pro Sekunde ausgeführt und berechnet für jede Aktion einen Sicherheitswert. Die geschätzte Aktion ist die Aktion mit der höchsten Sicherheit. Eine Aktion kann nicht als geschätzte Aktion gelten, wenn ihre Gewissheit unterhalb der Erkennungsschwelle liegt. Einige Programme müssen die Gewissheitswerte möglicherweise direkt verwenden, beispielsweise um sie anzuzeigen oder zu protokollieren. Die meisten Programme können die geschätzte Aktion anstelle der Gewissheitswerte verwenden.

## Parameter

- **Ereignis**: Eine der Aktionen, mit denen das maschinelle Lernmodell trainiert wurde.

## Rückgabe

- ein Prozentsatz als [Zahl](/types/number) zwischen 0 und 100, der die Gewissheit des ML-Modells angibt, dass es sich um die ausgeführte Aktion handelt. Die Gewissheit für „unbekannt” ist immer 0.

## Beispiel

Dieses Beispiel zeigt die prozentuale Sicherheit des ML-Modells, dass die aktuelle Aktion jede Sekunde „Klatschen” ist.

```blocks
loops.everyInterval(1000, function () {
    basic.showNumber(ml.getCertainty(ml.event.Clapping))
})
```

```package
machine-learning-help-stubs=github:calliope-edu/pxt-ml-help-stubs
machine-learning=github:calliope-edu/pxt-ml
```
