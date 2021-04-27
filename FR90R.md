# FR90R - Annullo richiesta di sconfinamento

## Nuovo mapping
```java
public Optional<FilialeResp> annulloRichiesta(string id)
```

## Tabelle legacy coinvolte
- 

## Chiamate a programmi legacy

| Programma | Gestione stato           | Comando           | Input legacy            | Output legacy           | Descrizione chiamata                | Dettaglio       |
| --------- | ------------------------ | ----------------- | ----------------------- | ----------------------- | ----------------------------------- | ------------------- |
| FR19S1    | Stateful ma singola call | *uguale ad input* | *f(parametri ricevuti)* | *blank*                 | Annullo richiesta di sconfinamento  | [FR19S1](FR19S1.md) |