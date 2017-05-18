# Operator

## Get All Operator Products

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://connect.narnoo.com/v1/operator/products/85/",
  "method": "GET",
  "headers": {
    "api-key": "xxxxxxxxxxxxxxxxxx",
    "api-secret-key": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "authorization": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
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
  CURLOPT_URL => "https://connect.narnoo.com/v1/operator/products/85/",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "api-key: xxxxxxxxxxxxxxxxxx",
    "api-secret-key: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "authorization: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
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

conn = http.client.HTTPSConnection("connect.narnoo.com")

headers = {
    'api-key': "xxxxxxxxxxxxxxxxxx",
    'api-secret-key': "xxxxxxxxxxxxxxxxxx",
    'authorization': "xxxxxxxxxxxxxxxxxx"
    }

conn.request("GET", "/v1/operator/products/85/", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```swift
import Foundation

let headers = [
  "api-key": "xxxxxxxxxxxxxxxxxx",
  "api-secret-key": "xxxxxxxxxxxxxxxxxx",
  "authorization": "xxxxxxxxxxxxxxxxxx"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://connect.narnoo.com/v1/operator/products/85/")! as URL,
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
```

> The above command returns JSON structured like this:

```json
{
  "operatorPlatform": "Rezdy",
  "operatorPlatformNickName": "rezdy",
  "products": [
    {
      "id": "4",
      "uniqueId": "26698291",
      "title": "Daintree Dreaming Day Tour",
      "dateCreated": "2016-08-15 11:17:48",
      "dateModified": "2017-02-10 18:02:25",
      "businessUrl": "http://www.adventurenorthaustralia.com/",
      "businessEmail": "info@adventurenorthaustralia.com",
      "businessState": "QLD",
      "businessCountry": "Australia",
      "location": "36 Aplin St, Cairns City QLD 4870, Australia",
      "latitude": "-16.92203651966663",
      "longitude": "145.77207805984153",
      "productSummary": null,
      "logo": {
        "logoId": "216",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/crop_Adventure-North-Australia-Fu4WgGEddXoYC32.JPG",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/thumb_Adventure-North-Australia-Fu4WgGEddXoYC32.JPG",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/preview_Adventure-North-Australia-Fu4WgGEddXoYC32.JPG",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/large_Adventure-North-Australia-Fu4WgGEddXoYC32.JPG",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/200_Adventure-North-Australia-Fu4WgGEddXoYC32.JPG",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/400_Adventure-North-Australia-Fu4WgGEddXoYC32.JPG",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/800_Adventure-North-Australia-Fu4WgGEddXoYC32.JPG"
      },
      "image": {
        "imageId": "5688",
        "entryDate": "28-07-2016 12:08",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/crop/crop_Adventure-North-Australia-E7gh7HMqbLRU4po.jpg",
        "xcropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/xcrop/xcrop_Adventure-North-Australia-E7gh7HMqbLRU4po.jpg",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/thumb/thumb_Adventure-North-Australia-E7gh7HMqbLRU4po.jpg",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/preview/preview_Adventure-North-Australia-E7gh7HMqbLRU4po.jpg",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/large/large_Adventure-North-Australia-E7gh7HMqbLRU4po.jpg",
        "xlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/xlarge/xlarge_Adventure-North-Australia-E7gh7HMqbLRU4po.jpg",
        "xxlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/xxlarge/xxlarge_Adventure-North-Australia-E7gh7HMqbLRU4po.jpg",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_8/200/200_Adventure-North-Australia-E7gh7HMqbLRU4po.jpg",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_8/400/400_Adventure-North-Australia-E7gh7HMqbLRU4po.jpg",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_8/800/800_Adventure-North-Australia-E7gh7HMqbLRU4po.jpg",
        "imageCaption": "Daintree Dreaming - Kuku Yalanji Coastal Walk "
      },
      "availablePlatforms": [
        {
          "name": "Rezdy",
          "nickName": "rezdy",
          "serviceType": "Reservations"
        }
      ]
    },
    {
      "id": "481",
      "uniqueId": "338692428",
      "title": "1 Day Cooktown 4wd Adventure",
      "dateCreated": "2017-02-02 09:46:07",
      "dateModified": "2017-03-21 00:00:00",
      "businessUrl": "http://www.adventurenorthaustralia.com/",
      "businessEmail": "info@adventurenorthaustralia.com",
      "businessState": "QLD",
      "businessCountry": "Australia",
      "location": "36 Aplin St, Cairns City QLD 4870, Australia",
      "latitude": "-16.92203651966663",
      "longitude": "145.77207805984153",
      "productSummary": {
        "createdAt": "10-02-2017 17:44",
        "text": "<p>A9R21B5.tmp</p>\n<p>Travel by 4WD along the scenic coastl drive to Cooktown. You will cross the mighy Daintree River by cable ferry and travel through the World Heritage Daintree Rainforest and traverse the 4wd only Bloomfield Track. Cross rivers and mountain ranges, visit the quirkly Lion's Den bush pub.  Enjoy spectacular panoramic views from Grassy Hill of Cooktown, Endeavour River and Coral Sea. Free time in Cooktown before returning to Cairns along the Inland road, the Outback of Far North Queensland.</p>\n<p> </p>",
        "language": "english"
      },
      "logo": {
        "logoId": "200",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/crop_Adventure-North-Australia-XJ8WOqRScc6FSOL.jpg",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/thumb_Adventure-North-Australia-XJ8WOqRScc6FSOL.jpg",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/preview_Adventure-North-Australia-XJ8WOqRScc6FSOL.jpg",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/large_Adventure-North-Australia-XJ8WOqRScc6FSOL.jpg",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/200_Adventure-North-Australia-XJ8WOqRScc6FSOL.jpg",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/400_Adventure-North-Australia-XJ8WOqRScc6FSOL.jpg",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_85/logo/800_Adventure-North-Australia-XJ8WOqRScc6FSOL.jpg"
      },
      "image": {
        "imageId": "5721",
        "entryDate": "29-07-2016 22:36",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/crop/crop_Adventure-North-Australia-PZnGVGneLTsSaYb.jpg",
        "xcropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/xcrop/xcrop_Adventure-North-Australia-PZnGVGneLTsSaYb.jpg",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/thumb/thumb_Adventure-North-Australia-PZnGVGneLTsSaYb.jpg",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/preview/preview_Adventure-North-Australia-PZnGVGneLTsSaYb.jpg",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/large/large_Adventure-North-Australia-PZnGVGneLTsSaYb.jpg",
        "xlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/xlarge/xlarge_Adventure-North-Australia-PZnGVGneLTsSaYb.jpg",
        "xxlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_8/xxlarge/xxlarge_Adventure-North-Australia-PZnGVGneLTsSaYb.jpg",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_8/200/200_Adventure-North-Australia-PZnGVGneLTsSaYb.jpg",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_8/400/400_Adventure-North-Australia-PZnGVGneLTsSaYb.jpg",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_8/800/800_Adventure-North-Australia-PZnGVGneLTsSaYb.jpg",
        "imageCaption": "Cooktown 4wd Adventures (Day and Overnight)"
      },
      "availablePlatforms": [
        {
          "name": "Rezdy",
          "nickName": "rezdy",
          "serviceType": "Reservations"
        }
      ]
    }
  ],
  "success": true,
  "cacheTime": "24",
  "productCount": 2,
  "queryTime": "472.49ms"
}
```

This endpoint retrieves all products for the operator.

### HTTP Request

`GET https://connect.narnoo.com/v1/operator/products/<id>/{service}`

### Query Parameters

Parameter | Required | Description
--------- | ------- |  -----------
id | true | We need to pass the operator's Narnoo ID
service | false | Some online directors have been mapped to our products. For example you can pass an ATDW id and then add 'atdw' as the service

### Response Parameters

Parameter |  Type |  Description
--------- | ------- | -------
availablePlatforms | Array |  Displays the reservation system that this operator uses.
