# Programmi legacy richiamati all'interno del modulo VT - Cassette di sicurezza

## Elenco programmi legacy

| Programma | Gestione stato           | Comando | Input legacy            | Output legacy           | Descrizione chiamata                                | Nuovo Mapping     |
| --------- | ------------------------ | ------- | ----------------------- | ----------------------- | --------------------------------------------------- | ----------------- |
| AG01R     | Stateful ma singola call | *INQ*   | [AG01dDSI](AG01dDSI.md) | [AG01dDSF](AG01dDSF.md) | Controllo lettura dati di una filiale o della banca | [AG01R](AG01R.md) |
| ZR02R     | Stateless                | *blank* | [ZR02dDS](ZR02dDS.md)   | [ZR02dDS](ZR02dDS.md)   | Manipolazione date(*)                               | [ZR02R](ZR02R.md) |
| ZT19R     | Stateful ma singola call | *blank* | [ZT19dIDS](ZT19dIDS.md) | [ZT19dODS](ZT19dODS.md) | Lettura parametri dell'applicazione                 | [ZT19R](ZT19R.md) |
| FR90R     | Stateless                | *ANN*   | [FR90dDSE](FR90dDSE.md) | *blank*                 | Annullo richiesta di sconfinamento                  | [FR90R](FR90R.md) |


## (*)Appendice

- Manipolazione date = calcolo data ad un mese / bimestre / trimestre / quadrimestre / semestre / anno di distanza dalla data in corso di elaborazione