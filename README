# APIs

#### Parameters: Used in the URL, headers, or cookies to pass data to the API.
#### Properties: Used within the request or response body to structure data payloads.

```
Authentication APIS:
  POST /api/auth/register:
    description: Register a new user.
    authentication: cookie credential
    body:
      description: JSON containing username, email and password.
      required: true
  POST /api/auth/login:
    description: Checks a password with the db stored hash
    body:
      description: JSON containing username and password.
      required: true
    responses:
      success: {message: Login successful, userd:<user_id>}
      failure: {error: Invalid username or password}
Debug APIS:
  GET /api/console:
    description: custom made console showing server processes. Should be accessed in a web browser.
    authentication: none
  GET /api/refreshAll
    description: refreshes all database storage and rebuilds tables. 
    authentication: none
    response:
      success: {message: Tables reset successfully}
      failure: {error: Failed to reset tables: <table>}
  POST /api/sqlraw
    description: post a raw sql request to the server
    authentication: none
    body:
      description: String contained SQL request
      required: true
    response:
      success: The SQL response in a JSON list
      error: {error: <error>}
Img APIS:
  GET /api/img/fullres/{image_id}
    description: return a full resolution image with the specified id.
    authentication: cookie credential
    response:
      success: image endpoint
      error: {error: <error>}
  GET /api/img/thumbnail/{image_id}
    description: return a thumbnail image with the specified id.
    authentication: cookie credential
    response:
      success: image endpoint
      error: {error: <error>}
  GET /api/img/properties/{image_id}
    description: returns the properties of a image
    authentication: cookie credential
    response:
      success: a JSON with all the images fields
      error: {error: <error>}
  POST /api/img/upload/{image_id}
    description: upload an image and its thumbnail counterpart to s3 volume and save it to a  dummy post with id = -1
    authentication: cookie credential
    body:
          description: Formdata including image properties and a file stream of image data
          required: true
    response:
        success: {image_id: <image_id>, message: File uploaded successfully to S3}
        error: {error: <error>}
  POST /api/img/settopost/{image_id}/{post_id}
    description: attach an image to a specific post
    authentication: cookie credential
    response:
        success: {message: Successfully added image to <post_id>}
        error: {error: <error>}
Post APIS:
  GET /api/post/postslistAZ
    description: returns list of posts in AZ order.
    authentication: cookie credential
    response:
        success: JSON array of post_id s
        error: {error: <error>}
  GET /api/post/coverImgId/{post_id}
    description: returns image_id of the front cover img of a post
    authentication: cookie credential
    response:
        success: {image_id: <image_id>}
        error: {error: <error>}
  GET /api/post/info/{post_id}
    description: returns info of a post
    authentication: cookie credential
    response:
        success: JSON array of post fields
        error: {error: <error>}
  GET /api/post/likestatus/{post_id}/{user_id}
    description: returns whether a specific user has liked a post
    authentication: cookie credential
    response:
        success: {post_id: <post_id>, user_id: <user_id>, has_liked: <Boolean response>}
        error: {error: <error>}
  GET /api/post/checkname
    description: check if a name already exists in a post
    authentication: cookie credential
    response:
        success: {exists: <Boolean response>}
        error: {error: <error>}
  GET /api/post/getcelltypes
      description: returns a list of cell types and their ids
      authentication: cookie credential
      response:
          success: JSON array of cell types
          error: {error: <error>}
  GET /api/post/getimagemodalities
      description: returns a list of image modalities and their ids
      authentication: cookie credential
      response:
          success: JSON array of image modalities
          error: {error: <error>}
  GET /api/post/getcategories
      description: returns a list of categories and their ids
      authentication: cookie credential
      response:
          success: JSON array of cell types
          error: {error: <error>}
  POST /api/post/newpost/{user_id}
      description: adds a new post attributed to a user
      authentication: cookie credential
      body:
            description: Formdata JSON including all post properties
            required: true
      response:
          success: {post_id: <post id>}
          error: {error: <error>}
  POST /api/post/like/{post_id}/{user_id}
      description: adds a like and increments post's like counter
      authentication: cookie credential
      response:
          success: {message: Like added successfully}
          error: {error: User had already liked this post}
  POST /api/post/unlike/{post_id}/{user_id}
      description: removes a like and decrements post's like counter
      authentication: cookie credential
      response:
          success: {message: Like removed successfully}
          error: {error: User has not liked this post}
  POST /api/post/search
      description: searches a String query and returns relevant post ids and search statistics
      authentication: cookie credential
      body:
            description: String with search term
            required: true
      response:
          success: array list as {post_id:<post_id>, full_text_rank: <similaritytofullword>, similarity_rank: <similaritytosubstrings>} 
          error: {error: <error>}
User APIS:
    GET /api/user/username/{user_id}
      description: returns the username of a user
      authentication: cookie credential
      response:
          success: {username: <username>}
          error: {error: <error>}
    GET /api/user/email/{user_id}
      description: returns the email of a user
      authentication: cookie credential
      response:
          success: {email: <email>}
          error: {error: <error>}
    GET /api/user/date/{user_id}
      description: returns the date of a user accounts creation
      authentication: cookie credential
      response:
          success: {created_at: <date>}
          error: {error: <error>}
    GET /api/user/favourites/{user_id}
      description: returns the post_ids a user has favourited
      authentication: cookie credential
      response:
          success: JSON array of post_ids
          error: {error: <error>}
    POST /api/email/{user_id}
      description: updates a user's email
      authentication: cookie credential
      body:
            description: String with new email
            required: true
      response:
          success: {message: Successfully updated email of <user_id>}
          error: {error: <error>}
    POST /api/username/{user_id}
      description: updates a user's username
      authentication: cookie credential
      body:
            description: String with new username
            required: true
      response:
          success: {message: Successfully updated username of <user_id>}
          error: {error: <error>}
