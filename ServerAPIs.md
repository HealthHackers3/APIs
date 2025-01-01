# APIs

#### Parameters: Used in the URL, headers, or cookies to pass data to the API.
#### Properties: Used within the request or response body to structure data payloads.

```
Multimedia-APIs: [COMPLETED]
  GET /api/v1/img/fullres/{img-UUID}: [COMPLETED]
    description: Provides a endpoint for img access.
    authentication: cookie credential
    parameters:
      - name: img-UUID
        in: path
        required: true
        description: Unique identifier for the image.

  GET /api/v1/img/thumbnail/{img-UUID}: [COMPLETED]
    description: Provides a endpoint for img access.
    authentication: cookie credential
    parameters:
      - name: img-UUID
        in: path
        required: true
        description: Unique identifier for the image.

  GET /api/img/properties/{img-UUID}: [COMPLETED
    description: Returns a JSON object with the image cell properties.
    authentication: cookie credential
    parameters:
      - name: img-UUID
        in: path
        required: true
        description: Unique identifier for the image.

  POST /api/img/upload/{post-UUID}: [COMPLETED]
    description: Upload multiple images and their properties to a post object.
    authentication: cookie credential + post-UUID
    headers:
      Content-Type: multipart/form-data array
    parameters:
      - name: post-UUID
        in: path
        required: true
        description: Identifier for the post.
    body:
      description: Images and associated metadata.
      required: true

Authentication-APIs:
  POST /api/v1/auth/login:
    description: Post login info (username + password) to obtain cookie credential + user-UUID.
    body:
      required: true
      properties:
        email:
          type: string
        password:
          type: string

  POST /api/v1/auth/register:
    description: Register a new user.
    body:
      required: true
      properties:
        email:
          type: string
        password:
          type: string

User-APIs:
  GET /api/v1/profile/{user-UUID}:
    description: Download user profile.
    authentication: cookie credential
    parameters:
      - name: user-UUID
        in: path
        required: true

  POST /api/v1/profile/{user-UUID}:
    description: Update user profile.
    authentication: cookie credential
    parameters:
      - name: user-UUID
        in: path
        required: true
    body:
      description: Profile fields to update.
      required: true

Search-APIs:
  GET /api/v1/search/{query}:
    description: Search for images and metadata.
    authentication: cookie credential
    parameters:
      - name: query
        in: path
        required: true
    responses:
      200:
        description: JSON response with search results.
      400:
        description: Invalid query.

General Enhancements:
  - Implement basic rate limiting (e.g., 1000 requests/hour per user).
  - Add CSRF protection to POST endpoints.
  - Introduce pagination for search results (e.g., ?page=1&limit=50).
  - Specify max upload size and accepted file formats in documentation.
```
