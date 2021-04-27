# ZR02R - calcolo data ad un mese / bimestre / trimestre / quadrimestre / semestre / anno di distanza dalla data in corso di elaborazione

## Nuovo mapping
```java
public Optional<DataResp> getFinePeriodo(Date dataInizio, long quantità)
```

## Tabelle legacy coinvolte
- Z19O (Lettura da Z19 dei calendari *blank*, lavorativi e festivi)

## Chiamate a programmi legacy

| Programma | Gestione stato | Comando | Input legacy | Output legacy           | Descrizione chiamata                                       | Dettaglio     |
| --------- | -------------- | ------- | ------------ | ----------------------- | ---------------------------------------------------------- | ----------------- |
| CZ02L     | Stateless      | *blank* |              | [CZ02LdDS](CZ02LdDS.md) | Verifica se sabato sia impostato come data lavorativa o no | [CZ02L](CZ02L.md) |
| ZR01R     | Stateless      | *CHAIN* |              | [Z10AdK](Z10AdK.md)     | Lettura filiale legata al terminale                        | [Z11Z](Z11Z.md)   |