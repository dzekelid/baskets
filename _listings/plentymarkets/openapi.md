---
swagger: "2.0"
x-collection-name: Plentymarkets
x-complete: 1
info:
  title: plentymarkets REST-API
  description: the-plentymarkets-rest-api-expands-the-functionality-of-the-plentymarkets-cms-and-allows-access-to-resources-i-e--data-records-via-unique-uri-paths
  contact:
    name: plentymarkets
    url: https://forum.plentymarkets.com/c/rest-api
  version: 1.0.0
host: example.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /rest/basket:
    get:
      summary: Get basket
      description: Gets the shopping cart for the current customer session.
      operationId: getRestBasket
      x-api-path-slug: restbasket-get
      responses:
        200:
          description: OK
      tags:
      - Basket
  /rest/basket/items:
    get:
      summary: List basket items
      description: Lists all items in the shopping cart for the current customer session.
      operationId: getRestBasketItems
      x-api-path-slug: restbasketitems-get
      responses:
        200:
          description: OK
      tags:
      - List
      - Basket
      - Items
    post:
      summary: Add item to basket
      description: Adds a new item to the shopping cart using the request parameters.
      operationId: postRestBasketItems
      x-api-path-slug: restbasketitems-post
      parameters:
      - in: body
        name: /rest/basket/items
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Item
      - To
      - Basket
  /rest/basket/items/{id}:
    get:
      summary: Find a basket item by it's ID
      description: Find a basket item by it's id.
      operationId: getRestBasketItems
      x-api-path-slug: restbasketitemsid-get
      parameters:
      - in: path
        name: id
      responses:
        200:
          description: OK
      tags:
      - Find
      - Basket
      - Item
      - By
      - Its
      - ID
---