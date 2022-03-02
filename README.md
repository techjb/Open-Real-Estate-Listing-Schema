# Open Real Estate Listing Schema
## An open schema for the publication of real estate advertisements

This document defines a data structure for the publication of real estate advertisements, taking into account the following criteria:
- Cover as many types of advertisements as possible.
- Transfer data between platforms.
- Be understandable.
- Valid for both supply and demand.
- Multilingual.
- Multipurpose.

## Motivation
- Facilitate the interoperability of real estate listing data.
- Define a data structure for a decentralised global real estate marketplace.


## Version history
- 1.0

## Definition

The schema has been defined using the [JSON](https://en.wikipedia.org/wiki/JSON) interchange format and `camelCase` convention.

All properties are optional, although it is highly recommended to fill in:
- version
- guid
- country
- propertyType

## Privacy
Contact information can be hidden by filling in the `contactUrl` property only.

## Schema
Version 1.0

```json
{
  "$schema": "http://json-schema.org/draft-04/schema#",
  "$id": "https://raw.githubusercontent.com/techjb/Open-Real-Estate-Listing-Schema/master/1.0.schema.json",
  "title": "Open Real Estate Listing Schema",
  "description": "An open schema for the publication of real estate advertisements",
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
    "unlistingDate": {
      "description": "Date of unlisting",
      "type": "string",
      "format": "date-time"
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
      "$ref": "#/definitions/urls",
      "description": "Urls of the images"
    },
    "thumbnails": {
      "$ref": "#/definitions/urls",
      "description": "Urls of the thumbnails"
    },
    "videos": {
      "$ref": "#/definitions/urls",
      "description": "Urls of the videos"
    },
    "floorPlans": {
      "$ref": "#/definitions/urls",
      "description": "Urls of the floor plans"
    },
    "otherMedia": {
      "$ref": "#/definitions/urls",
      "description": "Urls of the other media"
    },
    "price": {
      "$ref": "#/definitions/price",
      "description": "Property price"
    },
    "priceMin": {
      "$ref": "#/definitions/price",
      "description": "Minimum demand price"
    },
    "priceMax": {
      "$ref": "#/definitions/price",
      "description": "Maximum demand price"
    },
    "descriptions": {
      "$ref": "#/definitions/descriptions",
      "description": "Property descriptions"
    },
    "url": {
      "description": "Listing url",
      "type": "string",
      "format": "uri"
    },
    "dataSourceName": {
      "description": "Data source name",
      "type": "string"
    },
    "contactName": {
      "description": "Contact name",
      "type": "string"
    },
    "contactPhone": {
      "description": "Contact phone",
      "type": "string"
    },
    "contactEmail": {
      "description": "Contact email",
      "type": "string"
    },
    "contactUrl": {
      "description": "Contact url",
      "type": "string",
      "format": "uri"
    },
    "latitude": {
      "description": "Property latitude in decimal degrees",
      "type": "number"
    },
    "longitude": {
      "description": "Property longitude in decimal degrees",
      "type": "number"
    },
    "address": {
      "description": "Formated address",
      "type": "string"
    },
    "postalCode": {
      "description": "Postal code",
      "type": "string"
    },
    "state": {
      "description": "State code",
      "type": "string"
    },
    "country": {
      "description": "ISO 3166 country code",
      "type": "string"
    },
    "constructionSize": {
      "$ref": "#/definitions/size",
      "description": "Size of constuction"
    },
    "constructionYear": {
      "description": "Year of construction",
      "type": "integer"
    },
    "landSize": {
      "$ref": "#/definitions/size",
      "description": "Land size"
    },
    "floors": {
      "description": "Number of floors",
      "type": "integer"
    },
    "rooms": {
      "description": "Number of rooms",
      "type": "integer"
    },
    "bathrooms": {
      "description": "Number of bathrooms",
      "type": "integer"
    }

  },
  "definitions": {
    "urls": {
      "description": "List of urls",
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "title": {
            "description": "Url titles",
            "$ref": "#/definitions/descriptions"
          },
          "url": {
            "description": "Url",
            "type": "string",
            "format": "uri"
          }
        }
      }
    },
    "descriptions": {
      "description": "List of descriptions",
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "language": {
            "description": "ISO 639-1 language code",
            "type": "string"
          },
          "text": {
            "default": "Description text",
            "type": "string"
          }
        }
      }
    },
    "size": {
      "description": "Size definition",
      "type": "object",
      "properties": {
        "value": {
          "description": "Size value",
          "type": "number"
        },
        "unit": {
          "default": "Size unit",
          "type": "string"
        }
      }
    },
    "price": {
      "description": "Price",
      "type": "object",
      "properties": {
        "value": {
          "description": "Price value",
          "type": "number"
        },
        "currency": {
          "description": "ISO 4217 or cryptocurrency code",
          "type": "string"
        },
        "formated": {
          "description": "Price formated",
          "type": "string"
        }
      }
    }
  }
}

```

## License

MIT
