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
Content-Type: multipart/form-data
Accept-Encoding: gzip, deflate, br
Accept-Language: en-US,en;q=0.9
Accept: application/json, text/plain, */*
```

#### Body

```
let formData = new FormData();
formData.append("inputImages[]", <UPLOADED_FILE>)
formData.append("collection", "<STRING>")
```

#### Sample Response

```
{
    "message": "Bulk indexing is now completed successfuly",
    "data": [
        {
            "FaceRecords": [
                {
                    "Face": {
                        "FaceId": "e61a3097-c1e4-4c50-80c1-48a90b24a42d",
                        "BoundingBox": {
                            "Width": 0.13489148020744324,
                            "Height": 0.3932458460330963,
                            "Left": 0.16912849247455597,
                            "Top": 0.39353108406066895
                        },
                        "ImageId": "626f15ea-6b55-38f6-a5a7-0b3b08d26dc0",
                        "ExternalImageId": "drivers-license-requirements-2.jpg",
                        "Confidence": 99.99993896484375
                    },
                    "FaceDetail": {
                        "BoundingBox": {
                            "Width": 0.13489148020744324,
                            "Height": 0.3932458460330963,
                            "Left": 0.16912849247455597,
                            "Top": 0.39353108406066895
                        },
                        "AgeRange": {
                            "Low": 51,
                            "High": 69
                        },
                        "Smile": {
                            "Value": false,
                            "Confidence": 85.63027954101562
                        },
                        "Eyeglasses": {
                            "Value": false,
                            "Confidence": 96.06853485107422
                        },
                        "Sunglasses": {
                            "Value": false,
                            "Confidence": 99.13520812988281
                        },
                        "Gender": {
                            "Value": "Male",
                            "Confidence": 98.36045837402344
                        },
                        "Beard": {
                            "Value": false,
                            "Confidence": 72.96073913574219
                        },
                        "Mustache": {
                            "Value": false,
                            "Confidence": 94.9766845703125
                        },
                        "EyesOpen": {
                            "Value": true,
                            "Confidence": 97.95256042480469
                        },
                        "MouthOpen": {
                            "Value": false,
                            "Confidence": 83.86181640625
                        },
                        "Emotions": [
                            {
                                "Type": "FEAR",
                                "Confidence": 0.9422245621681213
                            },
                            {
                                "Type": "DISGUSTED",
                                "Confidence": 1.33741295337677
                            },
                            {
                                "Type": "CONFUSED",
                                "Confidence": 1.1999455690383911
                            },
                            {
                                "Type": "CALM",
                                "Confidence": 51.646339416503906
                            },
                            {
                                "Type": "ANGRY",
                                "Confidence": 15.346315383911133
                            },
                            {
                                "Type": "HAPPY",
                                "Confidence": 11.204495429992676
                            },
                            {
                                "Type": "SURPRISED",
                                "Confidence": 0.49602970480918884
                            },
                            {
                                "Type": "SAD",
                                "Confidence": 17.827234268188477
                            }
                        ],
                        "Landmarks": [
                            {
                                "Type": "eyeLeft",
                                "X": 0.20319366455078125,
                                "Y": 0.534623920917511
                            },
                            {
                                "Type": "eyeRight",
                                "X": 0.26618966460227966,
                                "Y": 0.5327346324920654
                            },
                            {
                                "Type": "mouthLeft",
                                "X": 0.20965860784053802,
                                "Y": 0.6788626909255981
                            },
                            {
                                "Type": "mouthRight",
                                "X": 0.26145821809768677,
                                "Y": 0.6771440505981445
                            },
                            {
                                "Type": "nose",
                                "X": 0.2376347780227661,
                                "Y": 0.6040218472480774
                            },
                            {
                                "Type": "leftEyeBrowLeft",
                                "X": 0.1774163693189621,
                                "Y": 0.5050132870674133
                            },
                            {
                                "Type": "leftEyeBrowRight",
                                "X": 0.21674571931362152,
                                "Y": 0.48935404419898987
                            },
                            {
                                "Type": "leftEyeBrowUp",
                                "X": 0.1974400281906128,
                                "Y": 0.48462793231010437
                            },
                            {
                                "Type": "rightEyeBrowLeft",
                                "X": 0.25394904613494873,
                                "Y": 0.4883708655834198
                            },
                            {
                                "Type": "rightEyeBrowRight",
                                "X": 0.2901349365711212,
                                "Y": 0.5014394521713257
                            },
                            {
                                "Type": "rightEyeBrowUp",
                                "X": 0.2723350524902344,
                                "Y": 0.48170018196105957
                            },
                            {
                                "Type": "leftEyeLeft",
                                "X": 0.19167262315750122,
                                "Y": 0.5353139042854309
                            },
                            {
                                "Type": "leftEyeRight",
                                "X": 0.2154075652360916,
                                "Y": 0.535727858543396
                            },
                            {
                                "Type": "leftEyeUp",
                                "X": 0.20302681624889374,
                                "Y": 0.5276928544044495
                            },
                            {
                                "Type": "leftEyeDown",
                                "X": 0.20347878336906433,
                                "Y": 0.5408218502998352
                            },
                            {
                                "Type": "rightEyeLeft",
                                "X": 0.2530638575553894,
                                "Y": 0.5346159338951111
                            },
                            {
                                "Type": "rightEyeRight",
                                "X": 0.2760460078716278,
                                "Y": 0.5327064394950867
                            },
                            {
                                "Type": "rightEyeUp",
                                "X": 0.2656093239784241,
                                "Y": 0.5257765054702759
                            },
                            {
                                "Type": "rightEyeDown",
                                "X": 0.26516494154930115,
                                "Y": 0.5388970971107483
                            },
                            {
                                "Type": "noseLeft",
                                "X": 0.2243589460849762,
                                "Y": 0.6247439980506897
                            },
                            {
                                "Type": "noseRight",
                                "X": 0.24754659831523895,
                                "Y": 0.6229302287101746
                            },
                            {
                                "Type": "mouthUp",
                                "X": 0.23632514476776123,
                                "Y": 0.656537652015686
                            },
                            {
                                "Type": "mouthDown",
                                "X": 0.23613570630550385,
                                "Y": 0.6997678279876709
                            },
                            {
                                "Type": "leftPupil",
                                "X": 0.20319366455078125,
                                "Y": 0.534623920917511
                            },
                            {
                                "Type": "rightPupil",
                                "X": 0.26618966460227966,
                                "Y": 0.5327346324920654
                            },
                            {
                                "Type": "upperJawlineLeft",
                                "X": 0.1584835648536682,
                                "Y": 0.5490978956222534
                            },
                            {
                                "Type": "midJawlineLeft",
                                "X": 0.17415723204612732,
                                "Y": 0.6995784640312195
                            },
                            {
                                "Type": "chinBottom",
                                "X": 0.23534506559371948,
                                "Y": 0.7752443552017212
                            },
                            {
                                "Type": "midJawlineRight",
                                "X": 0.28814709186553955,
                                "Y": 0.6960889101028442
                            },
                            {
                                "Type": "upperJawlineRight",
                                "X": 0.30036571621894836,
                                "Y": 0.5447230339050293
                            }
                        ],
                        "Pose": {
                            "Roll": -0.14228956401348114,
                            "Yaw": 0.6201589107513428,
                            "Pitch": -1.9568188190460205
                        },
                        "Quality": {
                            "Brightness": 84.08855438232422,
                            "Sharpness": 78.64350128173828
                        },
                        "Confidence": 99.99993896484375
                    }
                }
            ],
            "FaceModelVersion": "4.0",
            "UnindexedFaces": []
        },
        {
            "FaceRecords": [
                {
                    "Face": {
                        "FaceId": "39ec014d-c694-4dd9-b11a-b043e486c8a8",
                        "BoundingBox": {
                            "Width": 0.4938713312149048,
                            "Height": 0.5434554219245911,
                            "Left": 0.28448396921157837,
                            "Top": 0.22804847359657288
                        },
                        "ImageId": "97c03de9-45f4-3b6f-bb99-5827adaf2751",
                        "ExternalImageId": "kerwin.jpeg",
                        "Confidence": 99.99989318847656
                    },
                    "FaceDetail": {
                        "BoundingBox": {
                            "Width": 0.4938713312149048,
                            "Height": 0.5434554219245911,
                            "Left": 0.28448396921157837,
                            "Top": 0.22804847359657288
                        },
                        "AgeRange": {
                            "Low": 22,
                            "High": 34
                        },
                        "Smile": {
                            "Value": false,
                            "Confidence": 74.85940551757812
                        },
                        "Eyeglasses": {
                            "Value": true,
                            "Confidence": 99.10614776611328
                        },
                        "Sunglasses": {
                            "Value": false,
                            "Confidence": 91.54340362548828
                        },
                        "Gender": {
                            "Value": "Male",
                            "Confidence": 97.32296752929688
                        },
                        "Beard": {
                            "Value": false,
                            "Confidence": 94.91365051269531
                        },
                        "Mustache": {
                            "Value": false,
                            "Confidence": 98.97300720214844
                        },
                        "EyesOpen": {
                            "Value": true,
                            "Confidence": 99.73595428466797
                        },
                        "MouthOpen": {
                            "Value": false,
                            "Confidence": 56.10952377319336
                        },
                        "Emotions": [
                            {
                                "Type": "CONFUSED",
                                "Confidence": 1.2150565385818481
                            },
                            {
                                "Type": "DISGUSTED",
                                "Confidence": 0.41957786679267883
                            },
                            {
                                "Type": "ANGRY",
                                "Confidence": 0.5458423495292664
                            },
                            {
                                "Type": "FEAR",
                                "Confidence": 0.15494932234287262
                            },
                            {
                                "Type": "SURPRISED",
                                "Confidence": 1.966475486755371
                            },
                            {
                                "Type": "HAPPY",
                                "Confidence": 26.011444091796875
                            },
                            {
                                "Type": "SAD",
                                "Confidence": 0.6262997388839722
                            },
                            {
                                "Type": "CALM",
                                "Confidence": 69.06035614013672
                            }
                        ],
                        "Landmarks": [
                            {
                                "Type": "eyeLeft",
                                "X": 0.40999287366867065,
                                "Y": 0.43070513010025024
                            },
                            {
                                "Type": "eyeRight",
                                "X": 0.6454404592514038,
                                "Y": 0.4290737509727478
                            },
                            {
                                "Type": "mouthLeft",
                                "X": 0.43260568380355835,
                                "Y": 0.6269830465316772
                            },
                            {
                                "Type": "mouthRight",
                                "X": 0.6268360614776611,
                                "Y": 0.6258331537246704
                            },
                            {
                                "Type": "nose",
                                "X": 0.5238949060440063,
                                "Y": 0.530683696269989
                            },
                            {
                                "Type": "leftEyeBrowLeft",
                                "X": 0.3189238905906677,
                                "Y": 0.3881489932537079
                            },
                            {
                                "Type": "leftEyeBrowRight",
                                "X": 0.4556065499782562,
                                "Y": 0.371107816696167
                            },
                            {
                                "Type": "leftEyeBrowUp",
                                "X": 0.3868350684642792,
                                "Y": 0.3630397319793701
                            },
                            {
                                "Type": "rightEyeBrowLeft",
                                "X": 0.5943298935890198,
                                "Y": 0.37008288502693176
                            },
                            {
                                "Type": "rightEyeBrowRight",
                                "X": 0.7397466897964478,
                                "Y": 0.3848488926887512
                            },
                            {
                                "Type": "rightEyeBrowUp",
                                "X": 0.6657121777534485,
                                "Y": 0.36020296812057495
                            },
                            {
                                "Type": "leftEyeLeft",
                                "X": 0.3692967891693115,
                                "Y": 0.4305170774459839
                            },
                            {
                                "Type": "leftEyeRight",
                                "X": 0.45578479766845703,
                                "Y": 0.4321427643299103
                            },
                            {
                                "Type": "leftEyeUp",
                                "X": 0.4090074896812439,
                                "Y": 0.4211958944797516
                            },
                            {
                                "Type": "leftEyeDown",
                                "X": 0.4109724760055542,
                                "Y": 0.43898719549179077
                            },
                            {
                                "Type": "rightEyeLeft",
                                "X": 0.5961316823959351,
                                "Y": 0.43111175298690796
                            },
                            {
                                "Type": "rightEyeRight",
                                "X": 0.6837884187698364,
                                "Y": 0.4282495975494385
                            },
                            {
                                "Type": "rightEyeUp",
                                "X": 0.6422542333602905,
                                "Y": 0.41951873898506165
                            },
                            {
                                "Type": "rightEyeDown",
                                "X": 0.64091956615448,
                                "Y": 0.43735387921333313
                            },
                            {
                                "Type": "noseLeft",
                                "X": 0.48222437500953674,
                                "Y": 0.5559430718421936
                            },
                            {
                                "Type": "noseRight",
                                "X": 0.5696294903755188,
                                "Y": 0.5536775588989258
                            },
                            {
                                "Type": "mouthUp",
                                "X": 0.5257675647735596,
                                "Y": 0.6001476645469666
                            },
                            {
                                "Type": "mouthDown",
                                "X": 0.5268781781196594,
                                "Y": 0.6585109233856201
                            },
                            {
                                "Type": "leftPupil",
                                "X": 0.40999287366867065,
                                "Y": 0.43070513010025024
                            },
                            {
                                "Type": "rightPupil",
                                "X": 0.6454404592514038,
                                "Y": 0.4290737509727478
                            },
                            {
                                "Type": "upperJawlineLeft",
                                "X": 0.269587904214859,
                                "Y": 0.44083431363105774
                            },
                            {
                                "Type": "midJawlineLeft",
                                "X": 0.32280340790748596,
                                "Y": 0.6487058401107788
                            },
                            {
                                "Type": "chinBottom",
                                "X": 0.530182421207428,
                                "Y": 0.7598567605018616
                            },
                            {
                                "Type": "midJawlineRight",
                                "X": 0.747367799282074,
                                "Y": 0.6454014182090759
                            },
                            {
                                "Type": "upperJawlineRight",
                                "X": 0.7981622815132141,
                                "Y": 0.43665894865989685
                            }
                        ],
                        "Pose": {
                            "Roll": -2.2626864910125732,
                            "Yaw": -13.74853801727295,
                            "Pitch": -1.9915748834609985
                        },
                        "Quality": {
                            "Brightness": 81.6023178100586,
                            "Sharpness": 96.61495208740234
                        },
                        "Confidence": 99.99989318847656
                    }
                }
            ],
            "FaceModelVersion": "4.0",
            "UnindexedFaces": []
        }
    ]
}
```

# Usage (Javascript)

<!--DOCUSAURUS_CODE_TABS-->
<!--XMLHttpRequest-->

```Js
let request = new XMLHttpRequest();

let form = new FormData();
var images = document.getElementById("inputImages").files;
form.append("inputImages[]", images);
form.append("collection", "test-collection");

request.setRequestHeader('Content-Type', 'multipart/form-data');
request.setRequestHeader('Authorization', '64FWlMjfhgiNeQGmrJEBM8D99A1nVNWEv2efeDzHZdH1WK2KOU8');
request.setRequestHeader('Accept', 'application/json, text/plain, multipart/form-data, */*');

request.open("POST", "http://<SERVER_IP>:<PORT>/ia/faces/bulkUpload");
request.send(form);

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
let form = new FormData();
var images = document.getElementById("inputImages").files;
form.append("inputImages[]", images);
form.append("collection", "test-collection");

fetch("http://<SERVER_IP>:<PORT>/ia/faces/bulkUpload", {
  method: "POST",
  body: form,
  headers: {
    "Content-Type": "multipart/form-data",
    Authorization: "64FWlMjfhgiNeQGmrJEBM8D99A1nVNWEv2efeDzHZdH1WK2KOU8",
    Accept: "application/json, text/plain, ,multipart/form-data, */*",
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
let form = new FormData();
var images = document.getElementById("inputImages").files;
form.append("inputImages[]", images);
form.append("collection", "test-collection");

axios.post('http://<SERVER_IP>:<PORT>/ia/faces/bulkUpload', form, {
    headers: {
    "Content-Type": "multipart/form-data",
    Authorization: "64FWlMjfhgiNeQGmrJEBM8D99A1nVNWEv2efeDzHZdH1WK2KOU8",
    Accept: "application/json, text/plain, multipart/form-data, */*",
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

let form = new FormData();
var images = document.getElementById("inputImages").files;
form.append("inputImages[]", images);
form.append("collection", "test-collection");


$.ajax({
    url: 'http://<SERVER_IP>:<PORT>/ia/faces/bulkUpload',
    type: "POST",
    body: form,
    headers: {
        "Content-Type": "multipart/form-data",
        Authorization: "64FWlMjfhgiNeQGmrJEBM8D99A1nVNWEv2efeDzHZdH1WK2KOU8",
        Accept: "application/json, text/plain, multipart/form-data, */*",
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
