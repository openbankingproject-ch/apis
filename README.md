# OpenBankingPropject.ch

## Schweizer Ausgabe der Berlin Group NextGen API

Dieses Repository enthält eine helvetisierte Version der Banking API der
[Berlin Group](https://www.berlin-group.org/). Die API
liegt als [OpenAPI 3.0](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md)
Spezifikation vor:

* Die API als HTML-Dokumenent: [/docs](https://openbankingproject-ch.github.io/obp-apis)
* Die API als YAML-Datei: [/swiss-ng-api.yaml](https://github.com/openbankingproject-ch/obp-apis/raw/master/swiss-ng-api.yaml)

## Anhang 1 - Swiss Domestic Definition

Die Schweiz spezifischen Definition umfassen die ESR-Zahlungen, sowie falls nötig weiter
Ergänzungen:

|              Element   Type               |         Type          |   Oranger EZS   (ISR)   |
| ----------------------------------------- | --------------------- | ----------------------- |
| endToEnd   Identification                 | Max35Text             | optional                |
| debtorAccount   (incl. type)              | Account Reference     | mandatory               |
| debtorId                                  | Max35Text             | n.a.                    |
| ultimateDebtor                            | Max70Text             | optional                |
| instructedAmount   (inc. Curr.)           | Amount                | mandatory               |
| currencyOfTransfer                        | Currency Code         | n.a.                    |
| exchangeRateInformation                   | Payment Exchange Rate | n.a.                    |
| creditorAccount                           | Account Reference     | mandatory               |
| creditorAgent                             | BICFI                 | optional                |
| creditorAgentName                         | Max70Text             | n.a.                    |
| creditorName                              | Max70Text             | mandatory               |
| creditorId                                | Max35Text             | optional                |
| creditorAddress                           | Address               | mandatory               |
| creditorNameAndAddress                    | Max140Text            | n.a.                    |
| ultimateCreditor                          | Max70Text             | optional                |
| purposeCode                               | Purpose Code          | optional                |
| chargeBearer                              | Charge Bearer         | n.a.                    |
| serviceLevel                              | Service Level Code    | n.a.                    |
| remittanceInformation   Unstructured      | Max140Text            | n.a.                    |
| remittanceInformation   UnstructuredArray | Array of Max140Text   | n.a.                    |
| remittanceInformation   Structured        | Remittance            | **mandatory (ESR-Ref)** |
| requestedExecution   Date                 | ISODate               | **mandatory**           |
| requestedExecution   Time                 | ISODateTime           | n.a.                    |
