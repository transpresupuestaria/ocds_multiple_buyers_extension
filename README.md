# Multiple Buyers per Contract 

## Background

The core OCDS schema provides space for a single buyer to be described at the top level of each contracting process (`release.buyer`), specified using an OrganizationReference object, which cross-references an entry in the `parties` array. 

Whilst more than one organization may be included in the `parties` array with the `role` of "buyer", it is not possible in core OCDS to associate particular buyers with particular contracts. 

In some contexts, including Mexican public procurement, it is very common that a contract is paid for by more than one buyer (institution).

This extension provides a way to reference multiple buyers (who should be present in the `parties` array) at the level of each individual contract.

## Extension fields

This extension adds a `buyers` property to the contract section of OCDS.
`contract.buyers` is an array of OrganizationReference objects consisting of the following fields:

• name - The name of the party being referenced. This must match the name of an entry in the parties section.
• id - The id of the party being referenced. This must match the id of an entry in the parties section.

## Example

```json
"contracts": [{
  "id": "201709003485",
  "awardID": "1485598",
  "title": "SEGUIMIENTO Y CONTROL DE LOS TRABAJOS FALTANTES CONSISTENTES EN LA CONSTRUCCIÓN DE TERRACERÍAS",
  "period": "",
  "valueWithTax": "",
  "buyers": [{
    "name": "Centro SCT Veracruz",
    "id": "09650"
    }]
  }]
```

## Notes

Applications that are not aware of this extension may assume that the organization referenced in `release.buyer` is the buyer for all contracts in the process. 

If there is a lead buyer organization, this organization may referenced in `release.buyer`. In other cases, to avoid misinterpretation of the data `release.buyer` should be left blank. 

This extension is similar to the [Contract Level Buyer Information](https://github.com/open-contracting/ocds_multiple_buyers_extension) which adds a `contract.buyer` (singular) property, for cases where there is a different buyer for each contract, but only ever one buyer per contract. 

## Issues

This extension is maintained by [transpresupuestaria](https://github.com/transpresupuestaria). 