# 1, Introduction and Goals

## Overview

NorthStar will become a new system of record for all contacts and companies. Hub will still maintain it's contact and company tables, so it can maintain its integrity, but will pass contact and company information to NorthStar and update its internal database, without modification, with records that NorthStar returns.

Initially NorthStar will only consume a portion of the contact records, and no Company records.


## Goals

The goal of this phase of the implementation is integrate Hub with NorthStar so that, contacts and companies can be managed by NorthStar's Dynamics CRM system.

* All new and update contact operations will place a copy of the contact record onto a service bus for NortStar to consume.
* NorthStar will consume records from a Service Bus which match its filter.
  * NorthStar is a phased implementation so only needs certain contacts at this point.
* Records that NorthStar consumes will be assigned a NorthStar ID
* All records will be placed on a service bus for Hub to consume
* Hub will update its contact records with the record on the service bus.

* Companies will be handled at a later point.


## Stakeholders

| Department                      | Name                |
| ------------------------------- | ------------------- |
| Client Platforms                | Ian Fothergill      |
| CRM Developer                   | Chris Adams         |
| Architecture         (Hub)      | Gary Newport        |
| IT Development                  | Aneela Ahmed        |

