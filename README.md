# Open Real Estate Listing Schema
## An open schema for the publication of real estate advertisements

This document defines a data structure for the publication of real estate advertisements, taking into account the following criteria:
- Cover as many types of advertisements as possible.
- Being able to be transferred on multiple platforms.
- Be easily understandable.

## Motivation
The aim of this project is to facilitate the interoperability of real estate listing data.


## Version history
- 1.0

## Definition

The schema has been defined using the [JSON](https://en.wikipedia.org/wiki/JSON) interchange format and camelCase convention.
All fields are optional, although it is highly recommended to fill in the following fields:
- version
- guid
- country
- propertyType

## Schema

```json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "type": "object",
  "properties": {
    "version": {
      "type": "number"
    },
    "guid": {
      "type": "string"
    },
    "country": {
      "type": "string"
    },
    "propertyType": {
      "type": "string"
    }
  }
}
```


## License

MIT
