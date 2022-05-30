# How to use cIQ Milestones in ONE Record (at the example of FIW/FOW)

## Basic Information on this document

### Objective 
...

### Target audience
...

### Geographical coverage
As there are no legal or operational restrictions, the solution can be used world wide.

### Creators
...

### Continous development and availability

This document is to be used and continously developed, even if the current major stakeholders should move to other topics. Thus a "handover" in Github is planned if responsibilities should shift.

### Use and reference

This Good Practice is free to access and use. If you use it, please refer to this document explicitly plus provide a link to the Github repository as source. This will ensure know-how-transfer and transparency.

### Publication date, version and history

Publication date, version and history should be provided by the Github version control system and not be duplicated here.

## Dependencies

### Standards applied

The ONE Record business ontology version as of APR 13, 2022 was used [Working draft Ontology of 2022APR13](https://github.com/IATA-Cargo/ONE-Record/blob/bbe86e364b04d6a6279f0ab6e9ee47e1905ec9c4/working_draft/ontology/IATA-1R-DM-Ontology.ttl).

The ONE Record API and security specification draft witout a version as of APR 13, 2022 was used (no link available yet).

### ONE Record Server Implementation used

(no ONE Record server implementation yet)

### Other Software products used

## Assumptions
...

## Solution approach

ONE Record is based on a de-central data sharing approach. So quite some aspects of cIQ must be matched to fit into the ONE Record approach. They are described in the follown. Nevertheless, ONE Record´s approach ot cIQ is to fulfill all current requirements by design.

Open:

FIW/FOW on shipment or piece level


## Solution in current environment

...

# Data use and target process


## Matching Table FOW
| Element to capture                                   | Mandatory/optonal | ONE Record |
| ---------------------------------------------------- | ----------------- | ---------- |
| Transferring party                                   | M                 | party providing the *Event*; if the data provider is not the party performing the operational transaction, the the data field *Event/performedBy* of the type *Company* is to be used|
| Receiving party  (Using standard Cargo iQ code)      | M                 | to be cleared at cIQ!!!        |
| AWB number                                           | M                 | *Waybill/waybillNumber* with *Waybill/waybillType=Master* via *bookingOption*, *bookingOptionRequest*, *Shipment*, and *Piece*       |
| House AWB number                                     | O                 | *Waybill/waybillNumber* with *Waybill/waybillType=House* via *bookingOption*, *bookingOptionRequest*, *Shipment*, and *Piece*       |
| Piece level identifier                               | O                 | *Piece/uPID*        |
| Number of pieces                                     | M                 | Number of *Pieces*         |
| Total Weight (in kg)                                 | M                 | Sum of *Piece/GrossWeight*         |
| Part weight (in kg)                                  | C (if split/part) | *Piece/GrossWeight*         |
| Flight number                                        | M                 | *TransportMovement/transportIdentfier* via *Piece*     |
| Flight date                                          | M                 | *TransportMovement/departureDate* via *Piece*         |
| Warehouse airport code                               | M                 | *Location/locationCode*, *Location/locationType=IATA AirportCode*,  via *TransportMovement/departureLocation* and *Piece*        |
| Station status                                       | T,O,D             | ??         |
| Equipment type (ULD, Cart/Dolly)                     | M                 | ?*ULD/uldTypeCode*         |
| Equipment ID code                                    | M                 | *ULD/serialNumber*         |
| Equipment serviceability/checks                      | O                 | ??         |
| Consignment type (complete, split, part, divided)    | M                 | implicit on ONE Record (Are all pieces on same ULD?)  |
| FOW actual date and timestamp                        | M                 | *Event/dateTime*        |
| ETD or STD date and timestamp at the event time      | M                 | ??         |
| Handover location point (standard airport locations) | m                 | ?see Warehouse Airport Code         |
| Geolocation                                          | O                 | *Geolocation/latitude* and *Geolocation/longitude* via *Location/Geolocation*, *TransportMovement/departureLocation* and *Piece*        |          |

## Matching table FIW

| Element to capture                                   | Mandatory/optonal | ONE Record |
| ---------------------------------------------------- | ----------------- | ---------- |
| Transferring party                                   | M                 | \*         |
| Receiving party  (Using standard Cargo iQ code)      | M                 | \*         |
| AWB number                                           | M                 | \*         |
| House AWB number                                     | O                 | \*         |
| Piece level identifier                               | O                 | \*         |
| Number of pieces                                     | M                 | \*         |
| Total Weight (in kg)                                 | M                 | \*         |
| Part weight (in kg)                                  | C (if split/part) | \*         |
| Flight number                                        | M                 | \*         |
| Flight date                                          | M                 | \*         |
| Warehouse airport code                               | M                 | \*         |
| Station status                                       | T,O,D             | \*         |
| Equipment type (ULD, Cart/Dolly)                     | M                 | \*         |
| Equipment ID code                                    | M                 | \*         |
| Equipment serviceability/checks                      | O                 | \*         |
| Consignment type (complete, split, part, divided)    | M                 | \*         |
| FIW actual date and timestamp                        | M                 | \*         |
| ATA actual date and timestamp                        | M                 | \*         |
| Handover location point (standard airport locations) | m                 | \*         |
| Geolocation                                          | O                 | \*         |


# API use
...
## Technical setting
...

## Basic API-Features used
...

# Results / Summary
...
## Additional comments / FAQs
...
