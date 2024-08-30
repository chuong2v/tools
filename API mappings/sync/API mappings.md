${toc}

# API mappings
## List all products
![f74149c9271007b0e58384b180b62196.png](../_resources/f74149c9271007b0e58384b180b62196.png)
-  API: [https://next.fugamusic.com/api/docs/v2/#/Product/getProducts](https://next.fugamusic.com/api/docs/v2/#/Product/getProducts)
-  Endpoint: `GET products`
-  Parameters
```
{
  artist_id: <current_artist_id>
}
```
## Get product details
![ce6f24e23f6b10c066dff9799b556a70.png](../_resources/ce6f24e23f6b10c066dff9799b556a70.png)
- API: [https://next.fugamusic.com/api/docs/v2/#/Product/getProductById](https://next.fugamusic.com/api/docs/v2/#/Product/getProductById)
## Create product
### Add title
![01719c6bba3b2f7880d027234e49b3a2.png](../_resources/01719c6bba3b2f7880d027234e49b3a2.png) 

![1b8584e0e949fd7ed3388b9149bdd70b.png](../_resources/1b8584e0e949fd7ed3388b9149bdd70b.png)
- API: [https://next.fugamusic.com/api/docs/v2/#/Product/createProduct](https://next.fugamusic.com/api/docs/v2/#/Product/createProduct)
- Endpoint: `POST api/v2/products`
- Parameters
```
{
  "name": "Your release title",
  "display_artist": "Loo loo",
  "artists": [
    {
      "id": 1001263904959, // current user id
      "primary": true
    }
  ]
}
```
###  Add more artists
![4042b4103f9a29b49b05bbaa91ca7fb5.png](../_resources/4042b4103f9a29b49b05bbaa91ca7fb5.png)

![6a35b03c0f6abaff365202bf38899c49.png](../_resources/6a35b03c0f6abaff365202bf38899c49.png)

![7125969ca80810f92fcf9c285c38f023.png](../_resources/7125969ca80810f92fcf9c285c38f023.png)
- API: [https://next.fugamusic.com/api/docs/v2/#/Product/updateProductById](https://next.fugamusic.com/api/docs/v2/#/Product/updateProductById)
- Endpoint: `PUT api/v2/products/{id}`
- Parameters
```
{
  "artists": [
    {
      "id": 121429,
      "primary": true
    }
  ]
}
```
### Tracks
#### Add a track
- API: [https://next.fugamusic.com/api/docs/v2/#/Product/createProductAssetById](https://next.fugamusic.com/api/docs/v2/#/Product/createProductAssetById)
- Endpoint: `POST api/v2/products/{id}`
- Parameters
```
{
  "name": "string",
  "type": "TRACK"
}
```
- Response
```
{
  id: 1001769561079
}
```
#### Upload track audio
![069880839aeed91c6efa4aced81d8adf.png](../_resources/069880839aeed91c6efa4aced81d8adf.png)
- API: [https://next.fugamusic.com/api/docs/v2/#/Upload/createUploadStart](https://next.fugamusic.com/api/docs/v2/#/Upload/createUploadStart)
- Endpoint: `POST api/v2/upload/start`
- Parameters
```
{
  id: 1001769561079, // asset_id in the above response
  type: "audio"
}
```
#### Get list tracks
![c857a159ec90edb6738b6686ae2903a4.png](../_resources/c857a159ec90edb6738b6686ae2903a4.png)
- API: [https://next.fugamusic.com/api/docs/v2/#/Asset/getProductAssets](https://next.fugamusic.com/api/docs/v2/#/Asset/getProductAssets)
- Path: `GET api/v2/products/{id}/assets`
### Edit track title
![bd64295e40ebdb9491cf06f052cf32dd.png](../_resources/bd64295e40ebdb9491cf06f052cf32dd.png)

![3b940d7728506256b0e8a9ddd69c30c2.png](../_resources/3b940d7728506256b0e8a9ddd69c30c2.png)
- API: https://next.fugamusic.com/api/docs/v2/#/Product/updateProductAssetById
- Endpoint: `PUT api/v2/products/{id}/assets/{asset_id}`
- Parameters
```
{
  "name": "string"
}
```
#### Add lyrics
![73b57a2cda6b512e254d6bf148a1c31a.png](../_resources/73b57a2cda6b512e254d6bf148a1c31a.png)
- API: [https://next.fugamusic.com/api/docs/v2/#/Product/updateProductAssetById](https://next.fugamusic.com/api/docs/v2/#/Product/updateProductAssetById)
- Endpoint: `PUT api/v2/products/{id}/assets/{asset_id}`
- Parameters
```
{
  "lyrics": "Simple string"
}
```
#### Gerne
![cc16d3436869e329e69d78d30b4de7ab.png](../_resources/cc16d3436869e329e69d78d30b4de7ab.png)
- API: [https://next.fugamusic.com/api/docs/v2/#/Product/updateProductAssetById](https://next.fugamusic.com/api/docs/v2/#/Product/updateProductAssetById)
- Endpoint: `PUT api/v2/products/{id}/assets/{asset_id}`
- Parameters
```
{
  "genre": "JAZZ",
  "subgenre": 1001775227048,
  "alternate_genre": null,
  "alternate_subgenre": null,
  "mfit_email_address": null,
  "parental_advisory_next": "NO",
  "available_separately": true,
  "allow_preorder": true,
  "preorder_type": "STANDARD",
  "allow_preorder_preview": false
}
```
#### Writers
![cd707740421823256366f46acd01afca.png](../_resources/cd707740421823256366f46acd01afca.png)
- API: [https://next.fugamusic.com/api/docs/v2/#/Product/updateProductAssetById](https://next.fugamusic.com/api/docs/v2/#/Product/updateProductAssetById)
- Endpoint: `PUT api/v2/products/{id}/assets/{asset_id}`
- Parameters
```
{
  "artists": [{
    "id": 1001263904959,
    "name": "Loo loo",
    "primary": true
  }, {
    "id": 1001295870236,
    "name": "Dragon",
    "primary": false
  }, {
    "id": 1001493653156,
    "name": "Dmitry Di",
    "primary": false
  }]
}
```
## Update artwork
![4e69a48e67631e665a388dbc19e9c89b.png](../_resources/4e69a48e67631e665a388dbc19e9c89b.png)

![22db94ac46ab5e0b78f71269761e046f.png](../_resources/22db94ac46ab5e0b78f71269761e046f.png)

![a88a3b4be4b393b9dd9fcd6eae839c2c.png](../_resources/a88a3b4be4b393b9dd9fcd6eae839c2c.png)

![09b0cd833361776532ff38732fa56ef0.png](../_resources/09b0cd833361776532ff38732fa56ef0.png)
Every product has a default image with a unique `id` in FUGA system, when we need to update this image, just upload other image to replace it
### Initialize an upload process
- API: [https://next.fugamusic.com/api/docs/v2/#/Upload/createUploadStart](https://next.fugamusic.com/api/docs/v2/#/Upload/createUploadStart)
- Endpoint: `POST api/v2/upload/start`
-  Parameters
```
{
  id: 1001701741964, // asset_id of the default image
  type: "image"
}
```
### Upload
- API: [https://next.fugamusic.com/api/docs/v2/#/Upload/createUpload](https://next.fugamusic.com/api/docs/v2/#/Upload/createUpload)
### Finish an upload
- API: [https://next.fugamusic.com/api/docs/v2/#/Upload/createUploadFinish](https://next.fugamusic.com/api/docs/v2/#/Upload/createUploadFinish)
