---
id: bulk_face_indexing
title: Bulk Indexing
sidebar_label: Bulk Indexing
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

Reference reference, in order to process validation one side of data must be legit or true. In other words in face verification there must be a side which will correspond to the given data/face

Face indexing is process of identifying the face on the given image, once the image is detected using the bounding box. It will automatically store the face into the collection wherein all the authenticated faces is stored.

This API requires the image, and the collection name where the face will be kept.

# Requirements

#### Url

```
POST: http://<SERVER_IP>:<PORT>/ia/faces/bulkUpload
```

#### Headers

```
POST /ia/faces/bulkUpload HTTP/1.1
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
    fileExternalId: "<FILE_NAME>",
}
```

#### Sample Response

```
{
   "message": "Successfuly find the face base on the
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
    fileExternalId: "image.jpeg",
}

request.setRequestHeader('Content-Type', 'application/json;charset=UTF-8');
request.setRequestHeader('Authorization', '64FWlMjfhgiNeQGmrJEBM8D99A1nVNWEv2efeDzHZdH1WK2KOU8');
request.setRequestHeader('Accept', 'application/json, text/plain, */*');

request.open("POST", "http://<SERVER_IP>:<PORT>/ia/faces/bulkUpload")
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
  fileExternalId: "image.jpeg",
};

fetch("http://<SERVER_IP>:<PORT>/ia/faces/bulkUpload", {
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
  fileExternalId: "image.jpeg",
};

axios.post('http://<SERVER_IP>:<PORT>/ia/faces/bulkUpload', params, {
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
  fileExternalId: "image.jpeg",
};

$.ajax({
    url: 'http://<SERVER_IP>:<PORT>/ia/faces/bulkUpload',
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
