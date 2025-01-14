# Client side APIS

#### For use in the client programmed in js

```
authAPI:
  loginUser(email, password)
    description: Verifies a users credentials on the server.
    example usage: loginUser("sam@email.com", "passywordy")
                    => SUCCESS: cookie credential and success message
                    => FAILURE: error message
  signupUser(username, email, password)
    description: Signs up a new user to the database.
    example usage: signupUser("sam", "sam@email.com", "passywordy")
                    => SUCCESS: success mesage
                    => FAILURE: error message
fetchpostAPI:
  fetchPostCoverImgID(postId)
    description: Fetches the ID of a post's cover image.
    example usage: fetchPostCoverImgID(3)
                    => SUCCESS: returns image_id corresponding to post 3
                                e.g. {image_id: 3}
                    => FAILURE: error message
  fetchPostImages(postId)
    description: Fetches the IDs of all images attached to a post.
    example usage: fetchPostImages(3)
                    => SUCCESS: returns JSON array of image_ids corresponding to post 3
                                e.g. [{image_id: 3}, ...]
                    => FAILURE: error message
  fetchPostInfo(postId)
    description: Fetches the JSON data of a post.
    example usage: fetchPostInfo(3)
                    => SUCCESS: returns JSON object with post details
                    => FAILURE: error message
  fetchLikedPosts(userId)
    description: Fetches the posts liked by a user.
    example usage: fetchLikedPosts(1)
                    => SUCCESS: returns JSON object with posts liked by user 1
                    => FAILURE: error message
  fetchImgInfo(imageId)
    description: Fetches information about an image based on its ID.
    example usage: fetchImgInfo(1)
                    => SUCCESS: returns JSON object with image details
                    => FAILURE: error message
  fetchPostsAZ()
    description: Fetches a list of posts ordered alphabetically (A-Z).
    example usage: fetchPostsAZ()
                    => SUCCESS: returns a JSON object with a list of posts
                    => FAILURE: error message
likeAPI:
  addLike(postId)
    description: Adds a like to a post by the current user.
    example usage: addLike(3)
                    => SUCCESS: returns a JSON object with success message
                    => FAILURE: error message
  removeLike(postId)
    description: Removes a like from a post by the current user.
    example usage: removeLike(3)
                    => SUCCESS: returns a JSON object with success message
                    => FAILURE: error message
  getLikeStatus(postId)
    description: Retrieves the like status of a post for the current user.
    example usage: getLikeStatus(3)
                    => SUCCESS: returns true if the user liked the post, false otherwise
                    => FAILURE: error message
postAPI:
  newPost(postData)
    description: Creates a new post with the provided data.
    example usage: newPost({ post_name: 'Post Title', category_id: 2, cell_type_id: 3, image_modality_id: 4, description: 'This is a post description', poster_id: 1 })
                    => SUCCESS: returns the created post data
                    => FAILURE: error message
  uploadImages(imageDataArray)
    description: Uploads an array of images and returns their IDs.
    example usage: uploadImages([{ fileBuffer: buffer, fileName: 'image.jpg', orderIndex: 1, cellCount: 100, cellDimensionsX: 200, cellDimensionsY: 200, cellDensity: 1.5 }])
                    => SUCCESS: returns an array of uploaded image IDs
                    => FAILURE: error message
  createCompletePost(postData, imageDataArray)
    description: Creates a post and uploads images, attaching the images to the post.
    example usage: createCompletePost({ post_name: 'Post Title', category_id: 2, cell_type_id: 3, image_modality_id: 4, description: 'This is a post description', poster_id: 1 }, [imageDataArray])
                    => SUCCESS: returns an object with postId and imageIds
                    => FAILURE: error message
  attachImgToPost(imgId, postId)
    description: Attaches an uploaded image to a post.
    example usage: attachImgToPost(1, 3)
                    => SUCCESS: returns the result of the attachment
                    => FAILURE: error message
  deletePost(postId)
    description: Deletes a post by its ID.
    example usage: deletePost(3)
                    => SUCCESS: returns the deletion result
                    => FAILURE: error message
  checkPostName(postName)
    description: Checks if a post name already exists.
    example usage: checkPostName('Post Title')
                    => SUCCESS: returns true if the name exists, false otherwise
                    => FAILURE: error message
fetchAPI:
  fetchCategories()
    description: Fetches the available categories from the server.
    example usage: fetchCategories()
                    => SUCCESS: returns an array of categories
                    => FAILURE: null (error message logged in the console)
  fetchCellTypes()
    description: Fetches the available cell types from the server.
    example usage: fetchCellTypes()
                    => SUCCESS: returns an array of cell types
                    => FAILURE: null (error message logged in the console)
  fetchImageModalities()
    description: Fetches the available image modalities from the server.
    example usage: fetchImageModalities()
                    => SUCCESS: returns an array of image modalities
                    => FAILURE: null (error message logged in the console)
searchAPI:
  searchPosts(searchQuery)
    description: Searches for posts based on a given query.
    example usage: searchPosts("te")
                    => SUCCESS: returns an array of matching posts
                    => FAILURE: returns an empty array, error message logged in the console
userAPI:
  fetchUserUsername(userId)
    description: Fetches the username of a user by their user ID.
    example usage: fetchUserUsername(1)
                    => SUCCESS: returns the username of the user
                    => FAILURE: returns null, error message logged in the console
  fetchUserDate(userId)
    description: Fetches the account creation date of a user by their user ID.
    example usage: fetchUserDate(1)
                    => SUCCESS: returns the creation date of the user's account
                    => FAILURE: returns null, error message logged in the console
  fetchUserEmail(userId)
    description: Fetches the email of a user by their user ID.
    example usage: fetchUserEmail(1)
                    => SUCCESS: returns the email of the user
                    => FAILURE: returns null, error message logged in the console

