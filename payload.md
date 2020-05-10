
## Network International Digital Onboarding System
This document's target is to define all payload parameters in the different request typies.
#### ONBOARDING
| **field** | **Type** |**length**|**possible values**|**Way4**	|**Base24**|**Self-Services**|**MC-3D**|**Payload**
|--|--|--|--|--|--|--|--|--|
|**applications**| object[] |N/A ||mandatory|mandatory | | | | |
|**chain**| object |N/A ||optional|N/A | | | | |
|chain.chainId| alphanumeric | 25|| mandatory|N/A | | | | |
|chain.chainName| alphanumeric  | 100|| mandatory| N/A| | | | |
|chain.groupCode| alphabetic  | 10|AFG,  ALIMIGS, ASECYBS, ASEMIGS, ATG, BRLADP, DARADP, DDF, DET, DTR, EAM, ECMMIGS, EHMMIGS, EHSADP, ETI, ETS, FLD, FLN, JMB, JUM, KSA, MTOMOTO, OTH, RLG, ROTADP, RTA, SDG, TRNADP, TRNCYBS, TRNMIGS, TRNMOTO, TRNMPOS, TRNPOS, TRNSABR| mandatory| optional| | | | |
|chain.chainLevelReportRequired| boolean |5 || mandatory|N/A | | | | |
|chain.groupLevelReportingRequired| boolean | 5||mandatory |N/A | | | | |
|**merchant**  |object[]  |N/A ||mandatory | mandatory| | | | |
|merchant.merchantId  |alphanumeric|25 ||mandatory |mandatory | | | |
|merchant.merchantName|alphanumeric|100||mandatory | mandatory| | | |
|merchant.legalName|alphanumeric|100 ||mandatory | optional| | | |
|merchant.merchantType|alphanumeric|4||mandatory |mandatory | | | |
|merchant.mcc|numeric|5||mandatory |mandatory | | | |
|merchant.debitAccountNumOrIban|alphanumeric|25 ||mandatory | N/A| | | |
|merchant.creditAccountNumOrIban|alphanumeric|25 ||mandatory |N/A | | | |
|merchant.merchantCurrency|alphabetic|4 ||mandatory | mandatory| | | |
|merchant.statementFrequency|alphabetic|10|DAILY, WEEKLY, MONTHLY|mandatory |optional | | | |
|merchant.statementDeliveryType|alphabetic|5|Email, Fax|mandatory | optional| | | |
|merchant.paymentMode|alphabetic|3|EFT, EQ, FN, IFT, MC, NN, OB, TT |mandatory |optional | | | |
|merchant.kyc|boolean|5 ||mandatory | optional| | | |
|merchant.statementDay|numeric|2 ||mandatory |optional | | | |
|merchant.trn|alphanumeric|15 ||mandatory | optional| | | |
|merchant.fundSettlementLevel|alphabetic|1 |O, U|optional |optional | | | |
|merchant.legalType|alphanumeric|25 |LLC, SOLE_PROPRIETOR, PARTNERSHIP, FREE_ZONE|optional |optional | | | |
|**merchant.addresses**|object[]|N/A ||mandatory | mandatory | | | |
|merchant.addresses.addressType|alphabetic|25 |DEFAULT,  STMT_ADDR,  PAYM_ADDR,  CORRESPONDING,  TRADING|mandatory |mandatory| | | ||merchant.addresses.name |alphanumeric|100 ||mandatory |mandatory | | | |
|merchant.addresses.countryCode|alphabetic|4 ||mandatory |mandatory | | | |
|merchant.addresses.state|alphabetic|100 ||optional | mandatory| | | |
|merchant.addresses.city|alphabetic|100 ||mandatory | mandatory| | | |
|merchant.addresses.phone|numeric|25 ||optional | mandatory| | | |
|merchant.addresses.postalCode|numeric|25 ||mandatory |mandatory| | | |
|merchant.addresses.pobox|numeric|25 ||optional |mandatory || | |
|merchant.addresses.longitude|numeric|25 ||optional | optional| | | |
|merchant.addresses.latitude|numeric|25 ||optional | optional| | | |
|merchant.addresses.fax|numeric|25 ||optional | | | | |
|merchant.addresses.email|alphanumeric|256 ||mandatory | | | | |
|**merchant.configurations**|object|N/A||mandatory | mandatory| | | |
|merchant.configurations.overrideDefaultSchemesMcc|boolean|5||optional |optional | | | |
|merchant.configurations.commissionSettlement|alphabetic|15|NEXT_STTLM,  M1|mandatory | | | | |
|merchant.configurations.refundControlValue|alphabetic|1|G, R, C, N|mandatory | | | | |
|**merchant.configurations.acceptedCardSchemes**|object[]|N/A||mandatory | mandatory| | | |
|merchant.configurations.acceptedCardSchemes.cardScheme|alphabetic|4|VISA, MC, PL, JCB, CUP, MER, DCI, AMEX, TBOD, DODB, DOCR, DOHY, SBOC, SBOD, DOPR|mandatory | mandatory| | | |
|merchant.configurations.acceptedCardSchemes.tariffRate|numeric|10||mandatory in case of simple pricing merchants | | | | |
|**merchant.configurations.acceptedCardSchemes.acceptedCardModes**|object[]|N/A||mandatory in case of complex pricing merchants |N/A | | | |
|merchant.configurations.acceptedCardSchemes.acceptedCardModes.modeName|alphabetic|15|ELECTRONIC, MANUAL, INTERNATIONAL, DOMESTIC, PREMIUM|mandatory |N/A | | | |
|merchant.configurations.acceptedCardSchemes.acceptedCardModes.rate|numeric|10||mandatory |N/A | | | |
|**merchant.configurations.acceptedCardSchemes.schemeOverrideValue**|object|N/A||mandatory in case overrideDefaultSchemesMcc is true| N/A| | | |
|merchant.configurations.acceptedCardSchemes.schemeOverrideValue.mcc|numeric|5||mandatory|N/A | | | |
|merchant.configurations.acceptedCardSchemes.schemeOverrideValue.dbaName|alphanumeric|100||mandatory| | | | |
|**merchant.configurations.fees**|object[]|N/A||mandatory | N/A| | | |
|merchant.configurations.fees.feeTypeName|alphabetic|15|MIS, ACQ_MMBR_FEE, MFEE_STRT, MFEE_FRD_HND, FRAUD_HAND_FEE, TRANS_FEE, REFUND_FEE|mandatory | N/A| | | |
|merchant.configurations.fees.reOccurrenceFrequency|alphabetic|10|DAILY, WEEKLY, MONTHLY|mandatory |N/A| | | |
|merchant.configurations.fees.feeValue|numeric|10||mandatory |N/A| | | |
|**merchant.services**|object[]|N/A||optional | N/A| | | |
|merchant.services.serviceType|alphabetic|15|DCC, RENTAL, MC_3D_SECURE|mandatory |N/A| | | |
|merchant.services.dccProvider|alphabetic|2|PP, FX|mandatory in case of serviceType is DCC |N/A | | | |
|merchant.services.dccSettlementFrequency|alphabetic|10|DAILY, WEEKLY, MONTHLY|mandatory in case of serviceType is DCC |N/A | | | |
|merchant.services.daysOfMonth|numeric|2||mandatory in case of serviceType is DCC |N/A | | | |
|merchant.services.dccAcquirerRate|numeric|10||mandatory in case of serviceType is DCC |N/A | | | |
|merchant.services.dccMerchantMarkupRate|numeric|10||mandatory in case of serviceType is DCC |N/A | | | |
|merchant.services.dccMarkupRate|numeric|10||mandatory in case of serviceType is 'DCC' |N/A | | | |
|merchant.services.rentalModeCode|alphabetic|10|CASH, CHEQUE|mandatory in case of serviceType is 'RENTAL' |N/A| | | |
|merchant.services.rentalModeName|alphabetic|10||mandatory in case of serviceType is 'RENTAL' |N/A| | | |
|**merchant.terminals**|object[]|N/A||optional || | | |
|merchant.terminals.terminalId|alphanumeric|25||mandatory |mandatory | | | |
|merchant.terminals.terminalType|alphanumeric|10||mandatory | | | | |
|merchant.terminals.maker|alphanumeric|10||mandatory | | | | |
|merchant.terminals.terminalModel|alphanumeric|25||mandatory | | | | |
|merchant.terminals.communicationMethod|alphanumeric|10|SG,  GPRS_SIM|mandatory || | | |
|merchant.terminals.dccEnabled|boolean|5||mandatory | | | | |
|**merchant.terminals.fees**|object[]|N/A||mandatory | N/Aoptional| | | |
|merchant.terminals.fees.feeType|alphabetic|25|SIM_FEE,  GPRS_FEE,  TERMINAL_RENTAL_FEE,  INS_FEE|mandatory |N/A | | | |
|merchant.terminals.fees.feeValue|numeric|10||mandatory | N/A| | | |
|**merchant.terminals.allowedOperations**|object|N/A||optional |N/A | | | |
|merchant.terminals.allowedOperations.tips|boolean|5||optional | N/A| | | |
|merchant.terminals.allowedOperations.standardFunction||boolean|5|N/A | | | | |
|merchant.terminals.allowedOperations.refund|boolean|5|| |N/A | | | |
|merchant.terminals.allowedOperations.preAuthorization|boolean|5||N/Aoptional | | | | |
|merchant.terminals.allowedOperations.keyEntry|boolean|5||optional | N/A| | | |
|merchant.terminals.allowedOperations.cashAdvance|boolean|5||optional |N/A | | | |
|**merchant.user**|object|N/A||N/A | | | | |
|merchant.user.firstName|alphanumeric|100||N/A |N/A | | | |
|merchant.user.lastName|alphanumeric|100||N/A |N/A | | | |
|merchant.user.email|alphanumeric|256||N/A |N/A | | | |
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzYzMDk0NTcyLC04MDM4OTEyNjYsLTE4OT
k3NzIzNCw1MzEzNTU4NDYsOTc4MDEyMTA5LC0yMDg5NDU3Njgs
LTExNDMxMDMyMiwxOTM1ODI0MDE4LDY2ODcyNjQ3OF19
-->