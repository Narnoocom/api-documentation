# Connect

Narnoo works by allowing you to create connections between your business and the operator's you want to interact with.

It's similar to a social network where you create lists of businesses that your business follows.

## Find business to follow

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/connect/find",
  "method": "POST",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxxxxx",
    "Cache-Control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/connect/find",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxx",
    "Cache-Control: no-cache"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
?>
```

```python
import http.client

conn = http.client.HTTPConnection("apis,narnoo,com")

headers = {
    'Authorization': "bearer xxxxxxxxxxxxxxxxxxxxx",
    'Cache-Control': "no-cache"
    }

conn.request("POST", "api,v1,connect,find", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```swift
import Foundation

let headers = [
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxx",
  "Cache-Control": "no-cache"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/connect/find")! as URL,
                                        cachePolicy: .useProtocolCachePolicy,
                                    timeoutInterval: 10.0)
request.httpMethod = "POST"
request.allHTTPHeaderFields = headers

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
})
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "data": [
        {
            "details": {
                "id": "498",
                "business": "Skydive Cairns",
                "location": "Shop 5 47 Shields Street, Cairns QLD 4870, Australia",
                "latitude": "-16.87896377480452",
                "longitude": "145.74577548129275",
                "type": "operator",
                "connected": false
            },
            "avatar": {
                "id": "5031",
                "uploadedAt": "2016-01-20 10:14:23",
                "cropImage": "//dmxhl5sgly8nk.cloudfront.net/op_498/crop/crop_Skydive-Cairns-QWXm8y5guqmyM4C.jpg",
                "xcropImage": "//dmxhl5sgly8nk.cloudfront.net/op_498/xcrop/xcrop_Skydive-Cairns-QWXm8y5guqmyM4C.jpg",
                "thumbImage": "//dmxhl5sgly8nk.cloudfront.net/op_498/thumb/thumb_Skydive-Cairns-QWXm8y5guqmyM4C.jpg",
                "previewImage": "//dmxhl5sgly8nk.cloudfront.net/op_498/preview/preview_Skydive-Cairns-QWXm8y5guqmyM4C.jpg",
                "largeImage": "//dmxhl5sgly8nk.cloudfront.net/op_498/large/large_Skydive-Cairns-QWXm8y5guqmyM4C.jpg",
                "xlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_498/xlarge/xlarge_Skydive-Cairns-QWXm8y5guqmyM4C.jpg",
                "xxlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_498/xxlarge/xxlarge_Skydive-Cairns-QWXm8y5guqmyM4C.jpg",
                "image200": "//dmxhl5sgly8nk.cloudfront.net/op_498/200/200_Skydive-Cairns-QWXm8y5guqmyM4C.jpg",
                "image400": "//dmxhl5sgly8nk.cloudfront.net/op_498/400/400_Skydive-Cairns-QWXm8y5guqmyM4C.jpg",
                "image800": "//dmxhl5sgly8nk.cloudfront.net/op_498/800/800_Skydive-Cairns-QWXm8y5guqmyM4C.jpg",
                "imageSize": "5606.05",
                "imageWidth": "2503",
                "imageHeight": "2719",
                "orientation": null,
                "caption": "",
                "privilege": "public",
                "featureImage": true
            }
        },
        {
            "details": {
                "id": "471",
                "business": "Daintree Air Services",
                "location": "Tom McDonald Dr, Aeroglen QLD 4870, Australia",
                "latitude": "-16.882043741834117",
                "longitude": "145.74662305934146",
                "type": "operator",
                "connected": true
            },
            "avatar": {
                "id": "4981",
                "uploadedAt": "2016-01-18 10:44:42",
                "cropImage": "//dmxhl5sgly8nk.cloudfront.net/op_471/crop/crop_Daintree-Air-Services-o3LQV5mW58pzQet.jpg",
                "xcropImage": "//dmxhl5sgly8nk.cloudfront.net/op_471/xcrop/xcrop_Daintree-Air-Services-o3LQV5mW58pzQet.jpg",
                "thumbImage": "//dmxhl5sgly8nk.cloudfront.net/op_471/thumb/thumb_Daintree-Air-Services-o3LQV5mW58pzQet.jpg",
                "previewImage": "//dmxhl5sgly8nk.cloudfront.net/op_471/preview/preview_Daintree-Air-Services-o3LQV5mW58pzQet.jpg",
                "largeImage": "//dmxhl5sgly8nk.cloudfront.net/op_471/large/large_Daintree-Air-Services-o3LQV5mW58pzQet.jpg",
                "xlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_471/xlarge/xlarge_Daintree-Air-Services-o3LQV5mW58pzQet.jpg",
                "xxlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_471/xxlarge/xxlarge_Daintree-Air-Services-o3LQV5mW58pzQet.jpg",
                "image200": "//dmxhl5sgly8nk.cloudfront.net/op_471/200/200_Daintree-Air-Services-o3LQV5mW58pzQet.jpg",
                "image400": "//dmxhl5sgly8nk.cloudfront.net/op_471/400/400_Daintree-Air-Services-o3LQV5mW58pzQet.jpg",
                "image800": "//dmxhl5sgly8nk.cloudfront.net/op_471/800/800_Daintree-Air-Services-o3LQV5mW58pzQet.jpg",
                "imageSize": "8101.86",
                "imageWidth": "4283",
                "imageHeight": "2961",
                "orientation": null,
                "caption": "",
                "privilege": "public",
                "featureImage": true
            }
        },
        {
            "details": {
                "id": "555",
                "business": "Cairns Airport",
                "location": "Unnamed Road, Aeroglen QLD 4870, Australia",
                "latitude": "-16.87750590622631",
                "longitude": "145.75262047869876",
                "type": "operator",
                "connected": true
            },
            "avatar": {
                "id": "5245",
                "uploadedAt": "2016-03-08 12:07:42",
                "cropImage": "//dmxhl5sgly8nk.cloudfront.net/op_555/crop/crop_Cairns-Airport-dMJIzN4DCdx5qxv.jpg",
                "xcropImage": "//dmxhl5sgly8nk.cloudfront.net/op_555/xcrop/xcrop_Cairns-Airport-dMJIzN4DCdx5qxv.jpg",
                "thumbImage": "//dmxhl5sgly8nk.cloudfront.net/op_555/thumb/thumb_Cairns-Airport-dMJIzN4DCdx5qxv.jpg",
                "previewImage": "//dmxhl5sgly8nk.cloudfront.net/op_555/preview/preview_Cairns-Airport-dMJIzN4DCdx5qxv.jpg",
                "largeImage": "//dmxhl5sgly8nk.cloudfront.net/op_555/large/large_Cairns-Airport-dMJIzN4DCdx5qxv.jpg",
                "xlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_555/xlarge/xlarge_Cairns-Airport-dMJIzN4DCdx5qxv.jpg",
                "xxlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_555/xxlarge/xxlarge_Cairns-Airport-dMJIzN4DCdx5qxv.jpg",
                "image200": "//dmxhl5sgly8nk.cloudfront.net/op_555/200/200_Cairns-Airport-dMJIzN4DCdx5qxv.jpg",
                "image400": "//dmxhl5sgly8nk.cloudfront.net/op_555/400/400_Cairns-Airport-dMJIzN4DCdx5qxv.jpg",
                "image800": "//dmxhl5sgly8nk.cloudfront.net/op_555/800/800_Cairns-Airport-dMJIzN4DCdx5qxv.jpg",
                "imageSize": "4856.57",
                "imageWidth": "4663",
                "imageHeight": "3109",
                "orientation": null,
                "caption": "",
                "privilege": "public",
                "featureImage": false
            }
        },
        {
            "details": {
                "id": "108",
                "business": "Skytrans",
                "location": "Cairns QLD, Australia",
                "latitude": "-16.877738312555888",
                "longitude": "145.75400265328983",
                "type": "operator",
                "connected": true
            },
            "avatar": {
                "id": "1037",
                "uploadedAt": "2016-07-26 16:40:21",
                "cropImage": "//dmxhl5sgly8nk.cloudfront.net/op_108/crop/crop_6B5B4114388198e7102.jpg",
                "xcropImage": "//dmxhl5sgly8nk.cloudfront.net/op_108/xcrop/xcrop_6B5B4114388198e7102.jpg",
                "thumbImage": "//dmxhl5sgly8nk.cloudfront.net/op_108/thumb/thumb_6B5B4114388198e7102.jpg",
                "previewImage": "//dmxhl5sgly8nk.cloudfront.net/op_108/preview/preview_6B5B4114388198e7102.jpg",
                "largeImage": "//dmxhl5sgly8nk.cloudfront.net/op_108/large/large_6B5B4114388198e7102.jpg",
                "xlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_108/xlarge/xlarge_6B5B4114388198e7102.jpg",
                "xxlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_108/xxlarge/xxlarge_6B5B4114388198e7102.jpg",
                "image200": "//dmxhl5sgly8nk.cloudfront.net/op_108/200/200_6B5B4114388198e7102.jpg",
                "image400": "//dmxhl5sgly8nk.cloudfront.net/op_108/400/400_6B5B4114388198e7102.jpg",
                "image800": "//dmxhl5sgly8nk.cloudfront.net/op_108/800/800_6B5B4114388198e7102.jpg",
                "imageSize": null,
                "imageWidth": null,
                "imageHeight": null,
                "orientation": null,
                "caption": "",
                "privilege": "public",
                "featureImage": false
            }
        },
        {
            "details": {
                "id": "192",
                "business": "GBR Helicopters",
                "location": "Bush Pilots Avenue, Cairns International Airport (CNS), Aeroglen QLD 4870, Australia",
                "latitude": "-16.8856697",
                "longitude": "145.7495831",
                "type": "operator",
                "connected": false
            },
            "avatar": {
                "id": "4928",
                "uploadedAt": "2016-01-12 13:16:56",
                "cropImage": "//dmxhl5sgly8nk.cloudfront.net/op_192/crop/crop_GBR-Helicopters-q8wD2B8SXatU3UQ.jpg",
                "xcropImage": "//dmxhl5sgly8nk.cloudfront.net/op_192/xcrop/xcrop_GBR-Helicopters-q8wD2B8SXatU3UQ.jpg",
                "thumbImage": "//dmxhl5sgly8nk.cloudfront.net/op_192/thumb/thumb_GBR-Helicopters-q8wD2B8SXatU3UQ.jpg",
                "previewImage": "//dmxhl5sgly8nk.cloudfront.net/op_192/preview/preview_GBR-Helicopters-q8wD2B8SXatU3UQ.jpg",
                "largeImage": "//dmxhl5sgly8nk.cloudfront.net/op_192/large/large_GBR-Helicopters-q8wD2B8SXatU3UQ.jpg",
                "xlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_192/xlarge/xlarge_GBR-Helicopters-q8wD2B8SXatU3UQ.jpg",
                "xxlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_192/xxlarge/xxlarge_GBR-Helicopters-q8wD2B8SXatU3UQ.jpg",
                "image200": "//dmxhl5sgly8nk.cloudfront.net/op_192/200/200_GBR-Helicopters-q8wD2B8SXatU3UQ.jpg",
                "image400": "//dmxhl5sgly8nk.cloudfront.net/op_192/400/400_GBR-Helicopters-q8wD2B8SXatU3UQ.jpg",
                "image800": "//dmxhl5sgly8nk.cloudfront.net/op_192/800/800_GBR-Helicopters-q8wD2B8SXatU3UQ.jpg",
                "imageSize": "1089.13",
                "imageWidth": "1440",
                "imageHeight": "920",
                "orientation": null,
                "caption": "",
                "privilege": "public",
                "featureImage": true
            }
        }
    ],
    "queryTime": "186.12ms"
}
```

This endpoint retrieves a "suggested" list of operators from Narnoo.


### HTTP Request

`POST https://apis.narnoo.com/api/v1/connect/find`

### Query Parameters

A json BODY request with latitude and longitude values. This will then find operators based on the latitude and longitude entered.

Parameter | Required | Description
--------- | ------- |  -----------
latitude | FALSE | Pass a latitude option
longitude | FALSE | Pass a longitude option


## Search for operators

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/connect/search",
  "method": "POST",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxx",
    "Content-Type: application/json",
    "Cache-Control": "no-cache"
  },
  "data": "{\"name\":\"narnoo\"}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/connect/search",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\"name\":\"narnoo\"}",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxxxxxx",
    "Cache-Control: no-cache",
    "Postman-Token: 7b7540ba-2a97-4129-96f1-235086097a9d",
    "Content-Type: application/json",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
?>
```

```python
import requests

url = "https://apis.narnoo.com/api/v1/connect/search"

payload = "{\"name\":\"narnoo\"}"
headers = {
    'Authorization': "bearer xxxxxxxxxxxxxxxxxxxxxx",
    'Content-Type': "application/json",
    'Cache-Control': "no-cache",
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```swift
import Foundation

let headers = [
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxxx",
  "Content-Type": "application/json",
  "Cache-Control": "no-cache"
]
let parameters = ["name": "narnoo"] as [String : Any]

let postData = JSONSerialization.data(withJSONObject: parameters, options: [])

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/connect/search")! as URL,
                                        cachePolicy: .useProtocolCachePolicy,
                                    timeoutInterval: 10.0)
request.httpMethod = "POST"
request.allHTTPHeaderFields = headers
request.httpBody = postData as Data

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "data": [
        {
            "id": "39",
            "type": "operator",
            "name": "Narnoo Demo",
            "contact": "John Doe",
            "email": "info@narnoo.com",
            "phone": "+61 (13) 0040-6071",
            "url": "https://www.narnoo.com",
            "postcode": "4870",
            "state": "QLD",
            "suburb": "Stratford",
            "country": "Australia",
            "avatar": {
                "id": "1258",
                "uploadedAt": "2017-11-22 18:37:23",
                "cropImage": "//dmxhl5sgly8nk.cloudfront.net/op_39/crop/crop_929M11Q12Z4W2773144.jpg",
                "xcropImage": "//dmxhl5sgly8nk.cloudfront.net/op_39/xcrop/xcrop_929M11Q12Z4W2773144.jpg",
                "thumbImage": "//dmxhl5sgly8nk.cloudfront.net/op_39/thumb/thumb_929M11Q12Z4W2773144.jpg",
                "previewImage": "//dmxhl5sgly8nk.cloudfront.net/op_39/preview/preview_929M11Q12Z4W2773144.jpg",
                "largeImage": "//dmxhl5sgly8nk.cloudfront.net/op_39/large/large_929M11Q12Z4W2773144.jpg",
                "xlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_39/xlarge/xlarge_929M11Q12Z4W2773144.jpg",
                "xxlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_39/xxlarge/xxlarge_929M11Q12Z4W2773144.jpg",
                "image200": "//dmxhl5sgly8nk.cloudfront.net/op_39/200/200_929M11Q12Z4W2773144.jpg",
                "image400": "//dmxhl5sgly8nk.cloudfront.net/op_39/400/400_929M11Q12Z4W2773144.jpg",
                "image800": "//dmxhl5sgly8nk.cloudfront.net/op_39/800/800_929M11Q12Z4W2773144.jpg",
                "imageSize": null,
                "imageWidth": null,
                "imageHeight": null,
                "orientation": null,
                "caption": "Narnoo Creative",
                "privilege": "public",
                "featureImage": true
            },
            "connected": false
        }
    ],
    "queryTime": "76.45ms"
}

```

This endpoint retrieves any businesses that have similar names to the search request.


### HTTP Request

`POST https://apis.narnoo.com/api/v1/connect/search`

### Query Parameters

{"name":"narnoo"}

Parameter | Required | Description
--------- | ------- |  -----------
name | true | Operator Name

## Get list of operators business is following

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/connect/following",
  "method": "GET",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxx",
    "Cache-Control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/connect/following",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxxxxxxxxxx",
    "Cache-Control: no-cache"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
?>
```

```python
import requests

url = "https://apis.narnoo.com/api/v1/connect/following"

headers = {
    'Authorization': "bearer xxxxxxxxxxxxxxxxxxxx",
    'Cache-Control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```swift
import Foundation

let headers = [
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxx",
  "Cache-Control": "no-cache"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/connect/following")! as URL,
                                        cachePolicy: .useProtocolCachePolicy,
                                    timeoutInterval: 10.0)
request.httpMethod = "GET"
request.allHTTPHeaderFields = headers

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "data": [
        {
            "details": {
                "id": "615",
                "business": "Website Travel Demo",
                "contact": "Kenny Lee",
                "phone": "(61) 7369-8745",
                "email": "support@websitetravel.com",
                "url": "https://www.websitetravel.com/",
                "type": "operator",
                "role": "products"
            },
            "avatar": {
                "id": "7624",
                "uploadedAt": "2018-07-11 16:56:03",
                "cropImage": "//dmxhl5sgly8nk.cloudfront.net/op_615/crop/crop_Website-Travel-Demo-bEp1YkogxpnY31y.jpg",
                "xcropImage": "//dmxhl5sgly8nk.cloudfront.net/op_615/xcrop/xcrop_Website-Travel-Demo-bEp1YkogxpnY31y.jpg",
                "thumbImage": "//dmxhl5sgly8nk.cloudfront.net/op_615/thumb/thumb_Website-Travel-Demo-bEp1YkogxpnY31y.jpg",
                "previewImage": "//dmxhl5sgly8nk.cloudfront.net/op_615/preview/preview_Website-Travel-Demo-bEp1YkogxpnY31y.jpg",
                "largeImage": "//dmxhl5sgly8nk.cloudfront.net/op_615/large/large_Website-Travel-Demo-bEp1YkogxpnY31y.jpg",
                "xlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_615/xlarge/xlarge_Website-Travel-Demo-bEp1YkogxpnY31y.jpg",
                "xxlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_615/xxlarge/xxlarge_Website-Travel-Demo-bEp1YkogxpnY31y.jpg",
                "image200": "//dmxhl5sgly8nk.cloudfront.net/op_615/200/200_Website-Travel-Demo-bEp1YkogxpnY31y.jpg",
                "image400": "//dmxhl5sgly8nk.cloudfront.net/op_615/400/400_Website-Travel-Demo-bEp1YkogxpnY31y.jpg",
                "image800": "//dmxhl5sgly8nk.cloudfront.net/op_615/800/800_Website-Travel-Demo-bEp1YkogxpnY31y.jpg",
                "imageSize": "992.45",
                "imageWidth": "1831",
                "imageHeight": "1255",
                "orientation": "landscape",
                "caption": "",
                "privilege": "public",
                "featureImage": true
            }
        },
        {
            "details": {
                "id": "614",
                "business": "Rezdy Demo",
                "contact": "Rezdy Demo",
                "phone": "+61 (02) 8244-3060",
                "email": "stevie+noreply@rezdy.com",
                "url": "https://www.rezdy.com",
                "type": "operator",
                "role": "products"
            },
            "avatar": {
                "id": "7623",
                "uploadedAt": "2018-07-11 14:46:48",
                "cropImage": "//dmxhl5sgly8nk.cloudfront.net/op_614/crop/crop_Rezdy-Demo-s9hHFN4a9OiaLXZ.jpg",
                "xcropImage": "//dmxhl5sgly8nk.cloudfront.net/op_614/xcrop/xcrop_Rezdy-Demo-s9hHFN4a9OiaLXZ.jpg",
                "thumbImage": "//dmxhl5sgly8nk.cloudfront.net/op_614/thumb/thumb_Rezdy-Demo-s9hHFN4a9OiaLXZ.jpg",
                "previewImage": "//dmxhl5sgly8nk.cloudfront.net/op_614/preview/preview_Rezdy-Demo-s9hHFN4a9OiaLXZ.jpg",
                "largeImage": "//dmxhl5sgly8nk.cloudfront.net/op_614/large/large_Rezdy-Demo-s9hHFN4a9OiaLXZ.jpg",
                "xlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_614/xlarge/xlarge_Rezdy-Demo-s9hHFN4a9OiaLXZ.jpg",
                "xxlargeImage": "//dmxhl5sgly8nk.cloudfront.net/op_614/xxlarge/xxlarge_Rezdy-Demo-s9hHFN4a9OiaLXZ.jpg",
                "image200": "//dmxhl5sgly8nk.cloudfront.net/op_614/200/200_Rezdy-Demo-s9hHFN4a9OiaLXZ.jpg",
                "image400": "//dmxhl5sgly8nk.cloudfront.net/op_614/400/400_Rezdy-Demo-s9hHFN4a9OiaLXZ.jpg",
                "image800": "//dmxhl5sgly8nk.cloudfront.net/op_614/800/800_Rezdy-Demo-s9hHFN4a9OiaLXZ.jpg",
                "imageSize": "997.69",
                "imageWidth": "5000",
                "imageHeight": "2696",
                "orientation": "landscape",
                "caption": "",
                "privilege": "public",
                "featureImage": true
            }
        }
    ],
    "queryTime": "11.74ms"
}

```

This endpoint retrieves any businesses that you are following.

<aside class="notice">
The number of businesses that you following determine the Narnoo subscription plan you are on.
</aside>


### HTTP Request

`GET https://apis.narnoo.com/api/v1/connect/following`

### Query Parameters

Parameter | Required | Description
--------- | ------- |  -----------
page | false | paging
total | false | total number of responses request

## Connect with an operator

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/connect/add",
  "method": "POST",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxxxxx",
    "Content-Type": "application/json",
    "Cache-Control": "no-cache"
  },
  "processData": false,
  "data": "{\"type\":\"operator\",\"id\":85}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/connect/add",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\"type\":\"operator\",\"id\":85}",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxxxxxxxxxx",
    "Cache-Control: no-cache",
    "Content-Type: application/json"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
?>
```

```python
import requests

url = "https://apis.narnoo.com/api/v1/connect/add"

payload = "{\"type\":\"operator\",\"id\":85}"
headers = {
    'Authorization': "bearer xxxxxxxxxxxxxxxxxxxxxxxxx",
    'Content-Type': "application/json",
    'Cache-Control': "no-cache",
    'Postman-Token': "d6e51ff5-ccf0-4808-90ca-5a315e135119"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```swift
import Foundation

let headers = [
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxx",
  "Content-Type": "application/json",
  "Cache-Control": "no-cache"
]
let parameters = [
  "type": "operator",
  "id": 85
] as [String : Any]

let postData = JSONSerialization.data(withJSONObject: parameters, options: [])

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/connect/add")! as URL,
                                        cachePolicy: .useProtocolCachePolicy,
                                    timeoutInterval: 10.0)
request.httpMethod = "POST"
request.allHTTPHeaderFields = headers
request.httpBody = postData as Data

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "data": "The business is now connected",
    "queryTime": "76.45ms"
}

```

This endpoint adds an operator to your connection list.


### HTTP Request

`POST https://apis.narnoo.com/api/v1/connect/add`

### Query Parameters

{"type":"operator","id":85}


Parameter | Required | Description
--------- | ------- |  -----------
type | true | Operator
id | true | Operator ID

## Remove connected operator

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/connect/remove",
  "method": "POST",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxx",
    "Content-Type": "application/json",
    "Cache-Control": "no-cache"
  },
  "processData": false,
  "data": "{\"type\":\"operator\",\"id\":548}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/connect/remove",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\"type\":\"operator\",\"id\":548}",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxxxxxxxxxx",
    "Cache-Control: no-cache",
    "Content-Type: application/json",
    "Postman-Token: 02b021fa-6f5e-4976-a330-3146bca2d505"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
?>
```

```python
import requests

url = "https://apis.narnoo.com/api/v1/connect/remove"

payload = "{\"type\":\"operator\",\"id\":548}"
headers = {
    'Authorization': "bearer xxxxxxxxxxxxxxxxxxxxxxxx",
    'Content-Type': "application/json",
    'Cache-Control': "no-cache"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```swift
import Foundation

let headers = [
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "Content-Type": "application/json",
  "Cache-Control": "no-cache"
]
let parameters = [
  "type": "operator",
  "id": 548
] as [String : Any]

let postData = JSONSerialization.data(withJSONObject: parameters, options: [])

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/connect/remove")! as URL,
                                        cachePolicy: .useProtocolCachePolicy,
                                    timeoutInterval: 10.0)
request.httpMethod = "POST"
request.allHTTPHeaderFields = headers
request.httpBody = postData as Data

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "data": "The business has been unfollowed",
    "queryTime": "76.45ms"
}

```

This endpoint removes a following connection.


### HTTP Request

`POST https://apis.narnoo.com/api/v1/connect/remove`

### Query Parameters

{"type":"operator","id":85}

Parameter | Required | Description
--------- | ------- |  -----------
type | true | Operator
id | true | Operator ID


