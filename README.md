# Open Real Estate Listing Schema
## An open schema for the publication of real estate advertisements

This document defines a data structure for the publication of real estate advertisements, taking into account the following criteria:
- Cover as many types of advertisements as possible.
- Being able to be transferred on multiple platforms.
- Easily understandable.
- Valid for both supply and demand.

## Motivation
The aim of this project is to facilitate the interoperability of real estate listing data.


## Version history
- 1.0

## Definition

The schema has been defined using the [JSON](https://en.wikipedia.org/wiki/JSON) interchange format and `camelCase` convention.
All fields are optional, although it is highly recommended to fill in the following fields:
- version
- guid
- country
- propertyType

## Schema
Version 1.0

```json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "title": "Open Real Estate Listing Schema",
  "description": "An open schema for the publication of real estate advertisements",
  "$id": "https://raw.githubusercontent.com/techjb/Open-Real-Estate-Listing-Schema/master/1.0.schema.json",
  "type": "object",
  "properties": {
    "version": {
      "description": "Version number",
      "type": "number"
    },
    "guid": {
      "description": "Globally Unique Identifier",
      "type": "string"
    },
    "listingDate": {
      "description": "Date of listing",
      "type": "string",
      "format": "date-time"
    },
    "removeDate": {
      "description": "Date when it should be removed",
      "type": "string",
      "format": "date-time"
    },
    "country": {
      "description": "ISO 3166 property country code",
      "type": "string"
    },
    "propertyType": {
      "description": "Type of property",
      "type": "string",
      "enum": [ "home", "room", "premise", "garage", "storage", "wharehouse", "office", "land", "building" ]
    },
    "operation": {
      "description": "Type of operation",
      "type": "string",
      "enum": [ "buy", "sell", "rent", "share", "auction" ]
    },
    "images": {
      "description": "Urls of the images",
      "type": "array",
      "items": {
        "type": "string",
        "format": "uri"
      }
    },
    "thumbnails": {
      "description": "Urls of the thumbnails",
      "type": "array",
      "items": {
        "type": "string",
        "format": "uri"
      }
    },
    "videos": {
      "description": "Urls of the videos",
      "type": "array",
      "items": {
        "type": "string",
        "format": "uri"
      }
    },
    "floorPlans": {
      "description": "Urls of the floor plans",
      "type": "array",
      "items": {
        "type": "string",
        "format": "uri"
      }
    },
    "media": {
      "description": "Urls of other media",
      "type": "array",
      "items": {
        "type": "string",
        "format": "uri"
      }
    },
    "price": {
      "description": "Property type",
      "type": "number"
    },
    "currency": {
      "description": "ISO 4217 price currency code",
      "type": "string"
    },
    "description": {
      "description": "Property description",
      "type": "string"
    },
    "language": {
      "description": "ISO 639-1 language code for description",
      "type": "string"
    }
  }
}
```

## License

MIT
