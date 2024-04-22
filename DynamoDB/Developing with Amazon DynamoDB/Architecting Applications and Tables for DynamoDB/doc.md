# Architecting Applications and Tables for DynamoDB

## Two key concepts for NoSQL design

1. Design your DynamoDB schema when you know the specific query patterns the application must satisfy.

### Identify the access patterns by doing the following:

* Review user stories about activities the application will perform
* Document specific use cases you have identified

2. To reduce latency, costs, and management overhead, minimize the number of tables your application must interact with.

## Forecast access patterns for the ecommerce application

After reviewing user stories and use cases for the e-commerce application, list the required access patterns. E.g.:

| Access pattern | Description |
| --- | --- |
| 1. Get a user profile | Look up customer's contact information. |
| 2. Get orders for a user | Get customer's order history. |
| 3. Get a single order and its order items | Review items for a given order. |

## Define entities and relational schema

Store -> Taxes -> Associations // Products?

## Define the primary key

?

## Generic primary key names for tables with multiple entity types

| Primary Key |
| --- | --- |
| PK | SK |


## Design the primary key for the first entity
| PK  | SK  |
| --- | --- |
| Store:`uuid` | Tax:`uuid` |

## Design the layout of the second entity

| PK  | SK  |
| --- | --- |
| Store:`uuid` | Tax:`uuid`#TaxAssociation:`uuid` |

## Design the layout of the third entity

| PK  | SK  |
| --- | --- |
| Store:`uuid` | TaxAssociation:`uuid`#Tax:`uuid` |

## Single table design summary

