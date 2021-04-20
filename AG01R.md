# AG01R - Controllo esistenza e lettura dati filiale o banca 

## Nuovo mapping

```java
public Optional<FilialeResp> getFiliale(long id)
```

## Tabelle legacy coinvolte

- Z80A (Lettura Z80 senza record annullati )
- A05B (Lettura A05 senza record annullati)
- Z25J (Lettura Z25 senza record annullati)
- A10A (Lettura A10 senza record annullati)

## Chiamate a programmi legacy

| Programma | Gestione stato           | Comando | Input legacy            | Output legacy           | Descrizione chiamata                          | Nuovo Mapping       |
| --------- | ------------------------ | ------- | ----------------------- | ----------------------- | --------------------------------------------- | ------------------- |
| AN90R1    | Stateful ma singola call | *BANCA* | [AN90dDSA](AN90dDSA.md) | [AN90dDSC](AN90dDSC.md) | Determina il CAG a partire dal codice filiale | [AN90R1](AN90R1.md) |

### Parametri chiamata
- AN90R1
  - nessuno
