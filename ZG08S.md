# ZG08S - Gestione multitransazione giornale

## Nuovo mapping
```
Omesso perchè non chiamato da modulo VT
```

## Tabelle legacy coinvolte
- 

## Chiamate a programmi legacy

| Programma | Gestione stato | Comando   | Input legacy            | Output legacy           | Descrizione chiamata            | Dettaglio     |
| --------- | -------------- | --------- | ----------------------- | ----------------------- | ------------------------------- | ----------------- |
| KG91S     | Stateful       | *IMPEGNA* | [KG91dDS1](KG91dDS1.md) | [KG91dDSO](KG91dDSO.md) | Apertura F.A. in base a causale | [KG91S](KG91S.md) |
| ZG01S     | Stateful       | *APRI*    | [ZG01dDS1](ZG01dDS1.md) | [ZG01dDS2](ZG01dDS2.md) | Apertura giornale               | [ZG01S](ZG01S.md) |

