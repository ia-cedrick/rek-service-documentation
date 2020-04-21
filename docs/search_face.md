---
id: search_face
title: Search Face
---

This document scopes the following item :

- Introduction
- Requirements

  - Url
  - headers
  - body
  - sample response

- Usage

# Introduction

One way to identify customer identity is searching thru stored database/collection to execute the validation, and return a needed response to tag the user as authenticated or legit.

SearchFace API requires the image, authorization key, etc. as part of the request.

# Requirements

#### Url

```
POST: http://<SERVER_IP>:<PORT>/ia/faces/search

```

#### Headers

```
POST /ia/faces/search HTTP/1.1
Connection: keep-alive
Content-Length: 163091
Authorization:64FWlMjfhgiNeQGmrJEBM8D99A1nVNWEv2efeDzHZdH1WK2KOUjNbgcPZmvdawx38tS8m
Content-Type: application/json;charset=UTF-8
Accept-Encoding: gzip, deflate, br
Accept-Language: en-US,en;q=0.9
Accept: application/json, text/plain, */*
```

#### Body

```
{
    collection: "<COLLECTION_NAME>",
    image: "<BASE64_ENCODED_STRING>",
    faceMatchThreshold: <THRESOLD>,
    maxFaces: <NUMBER_OF_FACES>,
}
```

#### Sample Response

```
{
   "message":"Successfuly find the face base on the image provided",
   "data":{
      "SearchedFaceBoundingBox":{
         "Width":0.18664303421974182,
         "Height":0.4567655920982361,
         "Left":0.4204493463039398,
         "Top":0.3264122009277344
      },
      "SearchedFaceConfidence":99.99996185302734,
      "FaceMatches":[
         {
            "Similarity":99.83102416992188,
            "Face":{
               "FaceId":"f739eda9-3669-4432-9b4f-11ac66296a2f",
               "BoundingBox":{
                  "Width":0.29492801427841187,
                  "Height":0.46858999133110046,
                  "Left":0.34393298625946045,
                  "Top":0.37645500898361206
               },
               "ImageId":"dcf15e24-969a-3216-bdd0-4cbf42d6c13d",
               "ExternalImageId":"1asdasasdasd9123",
               "Confidence":99.9999008178711
            }
         }
      ],
      "FaceModelVersion":"4.0"
   }
}
```

# Usage (Javascript)

<!--DOCUSAURUS_CODE_TABS-->
<!--XMLHttpRequest-->

```Js
let request = new XMLHttpRequest();

const params = {
    collection: "test-collection",
    image: "data/image:base64..",
    faceMatchThreshold: 70,
    maxFaces: 1,
}

request.setRequestHeader('Content-Type', 'application/json;charset=UTF-8');
request.setRequestHeader('Authorization', '64FWlMjfhgiNeQGmrJEBM8D99A1nVNWEv2efeDzHZdH1WK2KOU8');
request.setRequestHeader('Accept', 'application/json, text/plain, */*');

request.open("POST", "http://<SERVER_IP>:<PORT>/ia/faces/search")
request.send(JSON.stringify(params));

request.onload = () => {
    if (request.status !== 201) {
        return request.response;
    } else {
        let resp = JSON.parse(request.response);
        return resp;
    }
}
```

<!--Fetch-->

```js
const params = {
  collection: "test-collection",
  image: "data/image:base64..",
  faceMatchThreshold: 70,
  maxFaces: 1,
};

fetch("http://<SERVER_IP>:<PORT>/ia/faces/search", {
  method: "POST",
  body: JSON.stringify(params),
  headers: {
    "Content-Type": "application/json;charset=UTF-8",
    Authorization: "64FWlMjfhgiNeQGmrJEBM8D99A1nVNWEv2efeDzHZdH1WK2KOU8",
    Accept: "application/json, text/plain, */*",
  },
})
  .then(function (response) {
    return response;
  })
  .catch(function (err) {
    return err;
  });
```

<!--Axios-->

```Js
const params = {
  collection: "test-collection",
  image: "data/image:base64..",
  faceMatchThreshold: 70,
  maxFaces: 1,
};

axios.post('http://<SERVER_IP>:<PORT>/ia/faces/search', params, {
    headers: {
    "Content-Type": "application/json;charset=UTF-8",
    Authorization: "64FWlMjfhgiNeQGmrJEBM8D99A1nVNWEv2efeDzHZdH1WK2KOU8",
    Accept: "application/json, text/plain, */*",
  }
})
  .then(function (response) {
    return response;
  })
  .catch(function (error) {
    return error;
  });
```

<!--jQuery-->

```Js
const params = {
  collection: "test-collection",
  image: "data/image:base64..",
  faceMatchThreshold: 70,
  maxFaces: 1,
};

$.ajax({
    url: 'http://<SERVER_IP>:<PORT>/ia/faces/search',
    type: "POST",
    body: JSON.stringify(params),
    headers: {
        "Content-Type": "application/json;charset=UTF-8",
        Authorization: "64FWlMjfhgiNeQGmrJEBM8D99A1nVNWEv2efeDzHZdH1WK2KOU8",
        Accept: "application/json, text/plain, */*",
    },
    success: function(response) {
        return response;
    },
    error: function(error) {
        return error;
    }
})
```

<!--END_DOCUSAURUS_CODE_TABS-->
