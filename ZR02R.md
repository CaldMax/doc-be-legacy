# ZR02R - calcolo data ad un mese / bimestre / trimestre / quadrimestre / semestre / anno di distanza dalla data in corso di elaborazione

## Nuovo mapping
```java
public Optional<DataResp> getFinePeriodo(Date dataInizio, long quantità)
```

## Tabelle legacy coinvolte
- Z19O (Lettura da Z19 dei calendari *blank*, lavorativi e festivi)

## Chiamate a programmi legacy

| Programma | Gestione stato | Comando | Input legacy | Output legacy           | Descrizione chiamata                                             | Nuovo Mapping     |
| --------- | -------------- | ------- | ------------ | ----------------------- | ---------------------------------------------------------------- | ----------------- |
| CZ02L     | Stateless      | *blank* |              | [CZ02LdDS](CZ02LdDS.md) | Verifica se sabato sia impostato come data lavorativa o no       | [CZ02L](CZ02L.md) |
| ZR01R     | Stateless      | *CHAIN* |              | [ZR01dDS](ZR01dDS.md)   | Modifica formato data da formato ISO a XXX con indicazioni extra | [ZR01R](ZR01R.md) |