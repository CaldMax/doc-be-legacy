# ZT35R - Lettura parametri di servizio di natura contabile o movimentazione 

## Nuovo mapping
```language
Omesso perchè non chiamato da modulo VT
```

## Tabelle legacy coinvolte
- 

## Chiamate a programmi legacy

| Programma | Gestione stato | Comando | Input legacy        | Output legacy       | Descrizione chiamata          | Dettaglio       |
| --------- | -------------- | ------- | ------------------- | ------------------- | ----------------------------- | --------------- |
| Z11Z      | Stateless      | *CHAIN* |                     | [Z10AdK](Z10AdK.md) | Lettura elemento di interesse | [Z11Z](Z11Z.md) |
| Z35A      | Stateless      | *CHAIN* | [Z35AdK](Z35AdK.md) | [Z35](Z35.md)       | Lettura elemento di interesse | [Z35A](Z35A.md) |