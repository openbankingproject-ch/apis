# OpenBankingProject.ch

The OpenBankingProject.ch will offer professionals working in the financial industry an one stop access point with relevant information about application programming interfaces (API) that fintech companies, banks and providers with an operational base in Switzerland are developing and using.

The project follows the open source approach. The results are generally made available to all interested parties and can also be maintained and supplemented by everyone as part of a curated process. Participation as a partner or in the community is explicitly open to all companies.

Visit our website for more information about [OpenBankingProject.ch](https://www.openbankingproject.ch). You're welcome to support us as a project partner or community member.


## Swiss NextGen API

This repository contains the Swiss NextGen API, the adapted version of the NextGenPSD2 XS2A Framework of the the [Berlin Group](https://www.berlin-group.org/) with the Swiss Domestic Payment Definitions. The API
follows the [OpenAPI 3.0](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.2.md)
spezification:
* the API as HTML: [/docs](https://openbankingproject-ch.github.io/obp-apis)
* the API as YAML: [/swiss-ng-api.yaml](https://github.com/openbankingproject-ch/obp-apis/raw/master/swiss-ng-api.yaml)
[![Prüfungsstatus der Spezifikation](https://travis-ci.com/openbankingproject-ch/obp-apis.svg?branch=master "Prüfungsstatus der Spezifikation")](https://travis-ci.com/openbankingproject-ch/obp-apis)

## Swiss Domestic Payment Definitions

The Swiss Domestic Payment Definitions are adapted from the [SIX Swiss Payment Standard](https://www.six-group.com/interbank-clearing/en/home/standardization/iso-payments/customer-bank/implementation-guidelines.html) and verified by our community. We will be happy to examine your suggestions for further development.

| CH Domestic Data Element                | CH Domestic Type                  | domestic-swiss-credit-transfers-isr | domestic-swiss-credit-transfers                 | domestic-swiss-foreign-credit-transfers | sepa-credit-transfers        | cross-border-credit-transfers | 
| --------------------------------------- | --------------------------------- | ----------------------------------- | ----------------------------------------------- | --------------------------------------- | ---------------------------- | ----------------------------- |
|                                         |                                   | Payment Type 1: ISR                 | Payment Type 2: IBAN/postal account and IID/BIC | Payment Type 4: Foreign currency        | Payment Type 5: Foreign SEPA | Payment Type 6: Foreign       |
| endToEndIdentification                  | Max35Text-Swift                   | mandatory                           | mandatory                                       | mandatory                               | mandatory                    | mandatory                     |
| debtorAccount (incl. type)              | accountReference16-CH             | mandatory                           | mandatory                                       | mandatory                               | mandatory                    | mandatory                     |
| debtorAgent                             | deptorAgent7-CH                   | mandatory                           | mandatory                                       | mandatory                               | mandatory                    | optional                      |
| debtorName                              | Max70Text                         | mandatory                           | mandatory                                       | mandatory                               | mandatory                    | mandatory                     |
| debtorId                                | Max35Text                         | optional 3)                         | optional 3)                                     | optional 3)                             | optional 3)                  | optional 3)                   |
| ultimateDebtor                          | Max70Text                         | optional                            | optional                                        | optional                                | optional                     | optional                      |
| instructedAmount (incl. currency)       | amount                            | mandatory                           | dependent 1)                                    | dependent 1)                            | dependent 1)                 | dependent 1)                  |
| equivalentAmount                        | amount                            | n.a.                                | dependent 1)                                    | dependent 1)                            | dependent 1)                 | dependent 1)                  |
| currencyOfTransfer                      | currencyCode                      | n.a.                                | dependent 1)                                    | dependent 1)                            | dependent 1)                 | dependent 1)                  |
| exchangeRateInformation                 | exchangeRateInformation1          | n.a.                                | optional 2)                                     | optional 2)                             | optional 2)                  | optional 2)                   |
| creditorAccount                         | accountReference16-CH             | mandatory                           | mandatory                                       | mandatory                               | mandatory                    | mandatory                     |
| creditorAgent                           | creditorAgent7-CH                 | n.a.                                | dependent 4)                                    | mandatory                               | optional                     | dependent 4)                  |
| creditorAgentName                       | Max70Text                         | n.a.                                | n.a.                                            | dependent 5)                            | n.a.                         | dependent 5)                  |
| creditorName                            | Max70Text                         | mandatory                           | mandatory                                       | mandatory                               | mandatory                    | mandatory                     |
| creditorId                              | Max35Text                         | n.a.                                | optional                                        | optional                                | optional                     | optional                      |
| creditorAddress                         | postalAddress6-CH                 | optional                            | optional                                        | optional                                | optional                     | optional                      |
| creditorNameAndAddress                  | Max140Text                        | n.a.                                | dependent                                       | dependent                               | dependent                    | dependent                     |
| ultimateCreditor                        | Max70Text                         | n.a.                                | optional                                        | optional                                | optional                     | optional                      |
| chargeBearer                            | chargeBearer                      | n.a.                                | optional                                        | optional                                | mandatory                    | optional                      |
| purposeCode                             | purposeCode                       | optional                            | optional                                        | optional                                | optional                     | optional                      |
| remittanceInformation UnstructuredArray | Max140Text                        | n.a.                                | n.a.                                            | n.a.                                    | n.a.                         | n.a.                          |
| serviceLevel                            | externalServiceLevel1Code         | n.a.                                | optional                                        | optional                                | mandatory                    | optional                      |
| remittanceInformation Unstructured      | Max140Text                        | n.a.                                | optional                                        | optional                                | optional                     | optional                      |
| remittanceInformation Structured        | remittanceInformation Structured7 | mandatory                           | optional                                        | optional                                | optional                     | optional                      |
| requestedExecutionDate                  | ISODate                           | mandatory                           | mandatory                                       | mandatory                               | mandatory                    | mandatory                     |
| requestedExecutionTime                  | ISODateTime                       | n.a.                                | n.a.                                            | n.a.                                    | n.a.                         | n.a.                          |
| intermediaryAgent                       | bicfi                             | n.a.                                | n.a.                                            | optional 2)                             | n.a.                         | optional 2)                   |
 
1) currencyOfTransfer is a subfield of equivalentAmount and may only be used if equivalentAmount is used instead of instructedAmount.
2) The element may only be used in consultation with the financial institution commissioned.
3) The element is currently ignored by financial institutions.
4) Dependence on creditorAccount, see SIX Swiss Payments Standards implementation guidelines.
5) Type 4(V3), 6(V2, V3): must be present. Type 4(V2): may be present. Other species: may not be present.
