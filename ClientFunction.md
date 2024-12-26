# FUNCTIONSs

#### Parameters: Variables input on the client side.

```
Post-functions:
  uploadImages(iamgeDataArray, PostId)
    description: Upload images and associated metadata for server storage.
    authentication: cookie credential
    parameters:
      - iamgeDataArray: a JSON array of image metadata
                filePath(required): the location of the image for uploading on the client side e.g. 'C:\\Users\\sctcl\\Electron-FrontendV1\\cancercell.jpg',
                orderIndex(required): the order of the photo in the post (0 is the first post) e.g. '1',
                cellCount: the number of cells e.g. '31',
                cellDimensionsX: the average cell x dimension e.g. '50',
                cellDimensionsY: the average cell y dimension e.g. '10',
                cellDensity: the image cell density e.g. '1',
      - PostId: the associated post the images are being added to
