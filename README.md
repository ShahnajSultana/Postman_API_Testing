# REST API Testing – Simple Books API (Postman + Newman)

API test collection for the public Simple Books API, built in Postman
and run from the command line with Newman. It covers authentication,
book lookup and the full order lifecycle (create, read, update, delete).

## Endpoints covered

| Method | Endpoint | What is checked |
|---|---|---|
| GET | /status | Status code 200, API status is "OK" |
| POST | /api-clients | Register client and get access token (201) |
| GET | /books?type=non-fiction&limit=10 | Status 200, books returned |
| GET | /books/:bookId | Status 200, book is in stock |
| POST | /orders | Order a book (201) |
| GET | /orders | List all orders (200) |
| GET | /orders/:orderId | Get a single order (200) |
| PATCH | /orders/:orderId | Update an order (204) |
| DELETE | /orders/:orderId | Delete an order (204) |

## Tech stack
Postman · Newman · JavaScript test scripts (pm.test)

## Features
- Collection variables for base URL and access token
- Bearer token authentication
- Path and query parameters
- Assertions on status codes and response body
- HTML report generated with Newman

## How to run

Install Newman:

```bash
npm install -g newman newman-reporter-html
```

Run the collection:

```bash
newman run SIMPLE-BOOK-API/postman_collection.json -r cli,html
```

## Report
A sample Newman HTML report is in `SIMPLE-BOOK-API/newman/`.
