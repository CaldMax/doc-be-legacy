# Programmi legacy richiamati all'interno del modulo VT - Cassette di sicurezza

## Elenco programmi legacy

| Programma | Gestione stato           | Comando    | Input legacy                 | Output legacy           | Descrizione chiamata                                  | Nuovo Mapping       |
| --------- | ------------------------ | ---------- | ---------------------------- | ----------------------- | ----------------------------------------------------- | ------------------- |
| AG01R     | Stateful ma singola call | *INQ*      | [AG01dDSI](AG01dDSI.md)      | [AG01dDSF](AG01dDSF.md) | Controllo lettura dati di una filiale o della banca   | [AG01R](AG01R.md)   |
| ZR02R     | Stateless                | *blank*    | [ZR02dDS](ZR02dDS.md)        | [ZR02dDS](ZR02dDS.md)   | Manipolazione date(*A*)                               | [ZR02R](ZR02R.md)   |
| ZT19R     | Stateful ma singola call | *blank*    | [ZT19dIDS](ZT19dIDS.md)      | [ZT19dODS](ZT19dODS.md) | Lettura parametri dell'applicazione                   | [ZT19R](ZT19R.md)   |
| FR90R     | Stateless                | *ANN*      | [FR90dDSE](FR90dDSE.md)      | *blank*                 | Annullo richiesta di sconfinamento                    | [FR90R](FR90R.md)   |
| ZT35R     | Stateless                | *CERCA*    | [ZT35dDSI](ZT35dDSI.md)(*B*) | [ZT35dCGE](ZT35dCGE.md) | Lettura conti di Co.Ge. (*RIFECOGE*)                  | [ZT35R](ZT35R.md)   |
|           |                          | *CERCA*    | [ZT35dDSI](ZT35dDSI.md)      | [ZT35dCAU](ZT35dCAU.md) | Lettura causali add. canoni di locazione (*RIFEMOVI*) | [ZT35R](ZT35R.md)   |
| ZR15R     | Stateful ma singola call | *blank*    | [ZR15dDS](ZR15dDS.md)        | [ZR15dDS](ZR15dDS.md)   | Formattazione del codice rapporto f(servizio)         | [ZR15R](ZR15R.md)   |
| ZG08SM    | Stateful                 | *blank*    | [ZG08dDS1](ZG08dDS1.md)(*C*) | [ZG08dDS2](ZG08dDS2.md) | Inizializzazione transazione giornale                 | [ZG08SM](ZG08SM.md) |
|           |                          | *CONFERMA* | [VT90dDSI](VT90dDSI.md)(*D*) | *blank*                 | Scrittura riga di servizio transazione giornale       | [ZG08SM](ZG08SM.md) |
|           |                          |            | + [ZGdGLB](ZGdGLB.md)(*D*)   |                         |                                                       | [ZG08SM](ZG08SM.md) |
|           |                          | *blank*    | [ZGdGLB](ZGdGLB.md)(*C*)     |                         | Annullo riga di servizio transazione giornale         | [ZG08SM](ZG08SM.md) |
|           |                          | *blank*    | [ZG13dIDS](ZG13dIDS.md)(*C*) | [ZG13dODS](ZG13dODS.md) | Scrittura riga di regolamento transazione giornale    | [ZG08SM](ZG08SM.md) |
|           |                          | *blank*    | *blank*                      | *blank*                 | Chiusura transazione giornale                         | [ZG08SM](ZG08SM.md) |


## (*A*)Appendice

- Manipolazione date = calcolo data ad un mese / bimestre / trimestre / quadrimestre / semestre / anno di distanza dalla data in corso di elaborazione

## (*B*)Appendice

- Avvaloramento variabile in base al contesto di business per addebiti canoni su: assegni, DR, CC, etc

## (*C*)Appendice

- Utilizzo non standard della struttura dati "ZZ$PRM"

| Campo struttura dati | Utilizzo standard   | Utilizzo in contesto giornale                                                   | Valori                |
| -------------------- | ------------------- | ------------------------------------------------------------------------------- | --------------------- |
| ZZPFIO               | Flag generio I/O    | Flag per identificare il momento della transazione in corso                     | I = Iniziaolizzazione |
|                      |                     |                                                                                 | S = Servizio          |
|                      |                     |                                                                                 | A = Annullo           |
|                      |                     |                                                                                 | R = Regolamento       |
|                      |                     |                                                                                 | Z = Chiusura          |
| ZZPCID               | Cod. Identificativo | Nome del programma di servizio da chiamare per scrivere una riga di servizio    | VT90S                 |
| ZZPCID               | Cod. Identificativo | Nome del programma di servizio da chiamare per scrivere una riga di regolamento | ZG13S                 |

## (*D*)Appendice

- [ZGdGLB](ZGdGLB.md) è una struttura tecnica usata dalla transazione del giornale
- Ogni servizio che vuole usare il giornale per gestire le transazioni deve poter passare al proprio programma di servizio i dati (in questo caso VT90S)
- Entrambi hanno a disposizione solo la struttura ZZ$DAT dovendo passare sia le informazioni usate da ZG08SM che quelle usate poi dal programma VT90S da lui chiamato
   
Quindi:

- Ogni servizio deve riservare i primi 100 byte della sua struttura dati, qui [VT90dDSI](VT90dDSI.md), in modo che siano sovrascrivibili mettendoci i dati di [ZGdGLB](ZGdGLB.md)
- Lo stesso vale per le righe di regolamento con struttura dati [ZG13dIDS](ZG13dIDS.md)