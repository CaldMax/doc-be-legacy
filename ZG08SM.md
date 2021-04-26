# ZG08SM - Gestione multitransazione giornale

## Nuovo mapping
```
Omesso perchè non chiamato da modulo VT
```

## Tabelle legacy coinvolte
- 

## Chiamate a programmi legacy

| Programma   | Gestione stato | Comando   | Input legacy            | Output legacy           | Descrizione chiamata                                    | Nuovo Mapping     |
| ----------- | -------------- | --------- | ----------------------- | ----------------------- | ------------------------------------------------------- | ----------------- |
| ZG08S       | Stateful       | *APRI*    | [ZG08dDS1](ZG08dDS1.md) | [ZG08d2DS](ZG08d2DS.md) | Apertura transazione giornale                           | [ZG08S](ZG08S.md) |
| *f(ZZPCID)* | Stateful       | *blank*   | *f(input)*              | *blank*                 | Scrittura riga di servizio transazione giornale         | *f(ZZPCID)*       |
| ZG05S       | Stateful       | *ANNULLA* | [ZG01dDS8](ZG01dDS8.md) | *blank*                 | Annullo riga di servizio transazione giornale           | [ZG05S](ZG05S.md) |
| ZG18S       | Stateful       | *CLGSEQ*  | [ZG18dDSQ](ZG18dDSQ.md) | *blank*                 | Collegamento delle righe di servizio con il regolamento | [ZG18S](ZG18S.md) |
| ZG13S       | Stateful       | *blank*   | *f(input)*              | *blank*                 | Scrittura riga di regolamento transazione giornale      | [ZG13S](ZG13S.md) |
| ZG08S       | Stateful       | *CHIUDI*  | [ZG08dDS3](ZG08dDS3.md) | *blank*                 | Chiusura transazione giornale                           | [ZG08S](ZG08S.md) |


