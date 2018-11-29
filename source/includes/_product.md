# Product

The product endpoint provides further information on an operator's products.

Once you know the ID of a product you can drill down further for more detailed information on that product.

## Get Product List

```javascript
var form = new FormData();

var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/product/list/614",
  "method": "GET",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "Cache-Control": "no-cache"
  },
  "processData": false,
  "contentType": false,
  "mimeType": "multipart/form-data",
  "data": form
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/product/list/614",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_POSTFIELDS => "",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxx",
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

url = "https://apis.narnoo.com/api/v1/product/list/614"

payload = ""
headers = {
    'Authorization': "bearer xxxxxxxxxxxxxxxxxxxxx",
    'Cache-Control': "no-cache"
    }

response = requests.request("GET", url, data=payload, headers=headers)

print(response.text)
```

```swift
import Foundation

let headers = [
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxxx",
  "Cache-Control": "no-cache"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/product/list/614")! as URL,
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
    "data": {
        "count": 1,
        "currentPage": 1,
        "totalPages": 1,
        "responseLimit": 50,
        "data": [
            {
                "id": "578",
                "productId": "225234852",
                "title": "Rezdy Day Tour",
                "image": {
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
                    "featureImage": true,
                    "markets": false
                }
            }
        ]
    },
    "queryTime": "4.96ms"
}
```

This endpoint retrieves the list of operator products.

### HTTP Request

`GET https://apis.narnoo.com/api/v1/product/list/{operator_id}`

<aside class="notice">
If the operator_id is left off the endpoint then the response will return the token owner's products.
</aside>

### Query Parameters

Parameter | Required | Description
--------- | ------- |  -----------
page | False | For paging results
total | False | To control response numbers

## Get Product Details

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/product/details/225234852/614",
  "method": "POST",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxxxx",
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
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/product/details/225234852/614",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxxxxxxxxxxx",
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

url = "https://apis.narnoo.com/api/v1/product/details/225234852/614"

headers = {
    'Authorization': "bearer xxxxxxxxxxxxxxxxxxxxxxxx",
    'Cache-Control': "no-cache"
    }

response = requests.request("POST", url, headers=headers)

print(response.text)
```

```swift
import Foundation

let headers = [
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxxx",
  "Cache-Control": "no-cache"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/product/details/225234852/614")! as URL,
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
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "data": {
        "productId": "225234852",
        "dateCreated": "2018-07-11 13:42:12",
        "dateModified": "2018-07-11 16:15:49",
        "title": "Rezdy Day Tour",
        "bookingId": "578",
        "minPrice": "100.00",
        "avgPrice": "100.00",
        "maxPrice": "100.00",
        "currency": "AUD",
        "keywords": null,
        "directBooking": null,
        "primary": false,
        "access": true,
        "bookable": true,
        "featureImage": {
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
            "featureImage": true,
            "markets": false
        },
        "featureLogo": null,
        "featureVideo": null,
        "featurePrint": null,
        "description": {
            "summary": [
                {
                    "english": {
                        "entry_date": "2018-07-11 13:42:28",
                        "modified_date": null,
                        "text": "<p ><span >Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla viverra aliquam nisl eget fermentum. Mauris venenatis consequat pellentesque. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Mauris consequat turpis eu ante fermentum, nec congue mauris posuere. Vivamus risus tellus, suscipit non ex in, tincidunt vulputate sapien.</span></p>"
                    }
                }
            ],
            "description": [
                {
                    "english": {
                        "entry_date": "2018-07-11 13:42:39",
                        "modified_date": null,
                        "text": "<p ><span >Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla viverra aliquam nisl eget fermentum. Mauris venenatis consequat pellentesque. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Mauris consequat turpis eu ante fermentum, nec congue mauris posuere. Vivamus risus tellus, suscipit non ex in, tincidunt vulputate sapien. Donec quis nisl erat. Etiam nibh ligula, imperdiet vel massa id, ultrices tincidunt justo. Proin efficitur nisi sed odio porttitor euismod. Ut lacinia purus vulputate molestie sollicitudin. Pellentesque dictum, dolor in accumsan suscipit, ante diam iaculis arcu, tincidunt dapibus nisi nibh ac orci. Proin porttitor maximus elit vel pretium.</span></p>"
                    }
                }
            ]
        },
        "gallery": {
            "total": 1,
            "images": [
                {
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
            ]
        },
        "features": false,
        "additionalInformation": {
            "operatingHours": "4",
            "startTime": "12:30:00",
            "endTime": "17:30:00",
            "transfer": null,
            "purchases": null,
            "fitness": null,
            "packing": null,
            "child": null,
            "additional": null,
            "terms": null
        }
    },
    "queryTime": "10.08ms"
}
```

This endpoint retrieves the details list for the operator product.

### HTTP Request

`GET https://apis.narnoo.com/api/v1/product/details/{productId}/{operator_id}`

<aside class="notice">
If the operator_id is left off the endpoint then the response will return the token owner's product if stored by that productId.
</aside>

