---
swagger: "2.0"
x-collection-name: Google Plus
x-complete: 1
info:
  title: Google Plus
  version: 1.0.0
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /circles/{circleId}:
    delete:
      summary: Delete Circle
      description: Delete a circle.
      operationId: plusDomains.circles.remove
      x-api-path-slug: circlescircleid-delete
      parameters:
      - in: path
        name: circleId
        description: The ID of the circle to delete
      responses:
        200:
          description: OK
      tags:
      - Circle
    get:
      summary: Get Circle
      description: Get a circle.
      operationId: plusDomains.circles.get
      x-api-path-slug: circlescircleid-get
      parameters:
      - in: path
        name: circleId
        description: The ID of the circle to get
      responses:
        200:
          description: OK
      tags:
      - Circle
    patch:
      summary: Update Circle
      description: Update a circle's description. This method supports patch semantics.
      operationId: plusDomains.circles.patch
      x-api-path-slug: circlescircleid-patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: circleId
        description: The ID of the circle to update
      responses:
        200:
          description: OK
      tags:
      - Circle
    put:
      summary: Update Circle
      description: Update a circle's description.
      operationId: plusDomains.circles.update
      x-api-path-slug: circlescircleid-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: circleId
        description: The ID of the circle to update
      responses:
        200:
          description: OK
      tags:
      - Circle
  /circles/{circleId}/people:
    delete:
      summary: Delete Circle
      description: Remove a person from a circle.
      operationId: plusDomains.circles.removePeople
      x-api-path-slug: circlescircleidpeople-delete
      parameters:
      - in: path
        name: circleId
        description: The ID of the circle to remove the person from
      - in: query
        name: email
        description: Email of the people to add to the circle
      - in: query
        name: userId
        description: IDs of the people to remove from the circle
      responses:
        200:
          description: OK
      tags:
      - Circle
  /people/{userId}/circles:
    get:
      summary: Get Circles
      description: List all of the circles for a user.
      operationId: plusDomains.circles.list
      x-api-path-slug: peopleuseridcircles-get
      parameters:
      - in: query
        name: maxResults
        description: The maximum number of circles to include in the response, which
          is used for paging
      - in: query
        name: pageToken
        description: The continuation token, which is used to page through large result
          sets
      - in: path
        name: userId
        description: The ID of the user to get circles for
      responses:
        200:
          description: OK
      tags:
      - Circle
    post:
      summary: Create New Circle
      description: Create a new circle for the authenticated user.
      operationId: plusDomains.circles.insert
      x-api-path-slug: peopleuseridcircles-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: userId
        description: The ID of the user to create the circle on behalf of
      responses:
        200:
          description: OK
      tags:
      - Circle
---