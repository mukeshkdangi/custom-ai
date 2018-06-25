# customeai

# Let first upload some images of the two different card Jeep and Mercedes
Then we train and build a model out these uploaded images: 

POST https://southcentralus.api.cognitive.microsoft.com/customvision/v2.0/Prediction/{PID}/url?iterationId={iterationId} HTTP/1.1
Host: southcentralus.api.cognitive.microsoft.com
Prediction-Key: {PKEY}
Content-Type: application/json

{
  "Url": "https://di-uploads-pod11.dealerinspire.com/raylaethemchryslerdodgejeep/uploads/2017/09/2018-Jeep-Compass-Hero.png"
}


# Let's test our model with the one JEEP image see how accurate our model is

apim-request-id: {id}
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
x-content-type-options: nosniff
Date: Mon, 25 Jun 2018 21:01:34 GMT
Content-Length: 389
Content-Type: application/json; charset=utf-8

{
  "id": "{id}",
  "project": "{pid}",
  "iteration": "{iteration}",
  "created": "2018-06-25T21:01:34.487003Z",
  "predictions": [{
    "probability": 0.468212515,
    "tagId": "b2af220e-a4f4-43b7-9c98-c13a6c9f8ca1",
    "tagName": "Mercedes"
  }, {
    "probability": 0.367403924,
    "tagId": "8e958793-dfd4-40c5-92ee-b861c7005b5e",
    "tagName": "Jeep"
  }]
}



# So our model is not si good as it's saying the new image os 47% Mercedes and 36%  channces that it could be Jeep 
Now we'll uploaded more images so that our system can understand the differnces b/t these 2 cars very well 

Once we are doing the training phase 2, we test same image against our model then see the result : 

Http Response : 
apim-request-id: {id}
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
x-content-type-options: nosniff
Date: Mon, 25 Jun 2018 20:59:48 GMT
Content-Length: 388
Content-Type: application/json; charset=utf-8

{
  "id": "{id}",
  "project": "{pid}",
  "iteration": "{iteration2}",
  "created": "2018-06-25T20:59:48.4573752Z",
  "predictions": [{
    "probability": 0.9310171,
    "tagId": "8e958793-dfd4-40c5-92ee-b861c7005b5e",
    "tagName": "Jeep"
  }, {
    "probability": 0.166567564,
    "tagId": "b2af220e-a4f4-43b7-9c98-c13a6c9f8ca1",
    "tagName": "Mercedes"
  }]
}

# So our model is not si good as it's saying the new image os 93% Mercedes and  only 16%  channces that it could be Jeep 
