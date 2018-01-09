# Multiple Buyers Extension

## Background

The core OCDS schema provides space for only one single buyer to be described for each contracting process, thus making it impossible to fit more than one. 
However, for the Mexican case, it is very common that one contract is paid by more than one buyer (institution).
This extension provides a way to provide multiple buyers per contract.

## Extension fields

This extension adds a buyers’ property to the contract section of OCDS.
contract.buyers is an OrganizationReference consisting of the following fields:
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
  "buyers": {
    "name": "Centro SCT Veracruz",
    "id": "09650"
    }
  }]
```