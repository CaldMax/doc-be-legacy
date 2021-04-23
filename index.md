# Programmi legacy richiamati all'interno del modulo VT - Cassette di sicurezza

## Elenco programmi legacy

| Programma | Gestione stato           | Comando    | Input legacy                 | Output legacy           | Descrizione chiamata                                      | Nuovo Mapping       |
| --------- | ------------------------ | ---------- | ---------------------------- | ----------------------- | --------------------------------------------------------- | ------------------- |
| AG01R     | Stateful ma singola call | *INQ*      | [AG01dDSI](AG01dDSI.md)      | [AG01dDSF](AG01dDSF.md) | Controllo lettura dati di una filiale o della banca       | [AG01R](AG01R.md)   |
| ZR02R     | Stateless                | *blank*    | [ZR02dDS](ZR02dDS.md)        | [ZR02dDS](ZR02dDS.md)   | Manipolazione date(*)                                     | [ZR02R](ZR02R.md)   |
| ZT19R     | Stateful ma singola call | *blank*    | [ZT19dIDS](ZT19dIDS.md)      | [ZT19dODS](ZT19dODS.md) | Lettura parametri dell'applicazione                       | [ZT19R](ZT19R.md)   |
| FR90R     | Stateless                | *ANN*      | [FR90dDSE](FR90dDSE.md)      | *blank*                 | Annullo richiesta di sconfinamento                        | [FR90R](FR90R.md)   |
| ZT35R     | Stateless                | *CERCA*    | [ZT35dDSI](ZT35dDSI.md)(**)  | [ZT35dCGE](ZT35dCGE.md) | Lettura conti di Co.Ge. (*RIFECOGE*)                      | [ZT35R](ZT35R.md)   |
|           |                          | *CERCA*    | [ZT35dDSI](ZT35dDSI.md)      | [ZT35dCAU](ZT35dCAU.md) | Lettura causali addebiti canoni di locazione (*RIFEMOVI*) | [ZT35R](ZT35R.md)   |
| ZR15R     | Stateful ma singola call | *blank*    | [ZR15dDS](ZR15dDS.md)        | [ZR15dDS](ZR15dDS.md)   | Formattazione del codice rapporto in base al servizio     | [ZR15R](ZR15R.md)   |
| ZG08SM    | Stateful                 | *CONFERMA* | [ZG13dIDS](ZG13dIDS.md)(***) | [ZG13dODS](ZG13dODS.md) | Interazione con lo strumento "giornale"                   | [ZG08SM](ZG08SM.md) |

## (*)Appendice

- Manipolazione date = calcolo data ad un mese / bimestre / trimestre / quadrimestre / semestre / anno di distanza dalla data in corso di elaborazione

## (**)Appendice

- Avvaloramento variabile in base al contesto di business per addebiti canoni su: assegni, DR, CC, etc

## (***)Appendice

- Utilizzo non standard della struttura dati "ZZ$PRM"