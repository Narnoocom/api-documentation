# Booking

The booking endpoint provides information regarding the product's bookable option.

These calls are often made live to a third party reservation/wholesaler's system. These endpoints require a booking code id to be passed so that Narnoo can request exact information for this product via the respective third party systems. These booking codes can be found by calling [get product details](#get-product-details)

## Get Supplier Bookable Products

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/booking/bookable_products/614",
  "method": "GET",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "Cache-Control": "no-cache",
    "Postman-Token": "8faa583d-adc7-47d1-9ac4-4224c88771a6"
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
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/booking/bookable_products/614",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
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

url = "https://apis.narnoo.com/api/v1/booking/bookable_products/614"

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
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxx",
  "Cache-Control": "no-cache"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/booking/bookable_products/614")! as URL,
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
    "queryTime": "13.09ms"
}
```

This endpoint retrieves the list of operators products that have been mapped to at least one reservation system.


### HTTP Request

`GET https://apis.narnoo.com/api/v1/booking/bookable_products/{operator_id}`

### Query Parameters

<aside class="warning">
Returns only products that have been mapped to a reservation system and therefore, are bookable via the API.
</aside>

## Get Product Booking Information

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/booking/product/614/578",
  "method": "GET",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxxxx",
    "Cache-Control": "no-cache",
    "Postman-Token": "ee297ec6-5bc8-438c-b366-06dc6b2f5344"
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
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/booking/product/614/578",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "Cache-Control: no-cache",
    "Postman-Token: 094dfe07-7169-4ad2-8633-9d946f187ede"
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

url = "https://apis.narnoo.com/api/v1/booking/product/614/578"

headers = {
    'Authorization': "bearer xxxxxxxxxxxxxxxxxxxxxxxxx",
    'Cache-Control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```swift
import Foundation

let headers = [
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxx",
  "Cache-Control": "no-cache"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/booking/product/614/578")! as URL,
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
        "bookingData": {
            "bookingPlatform": "Rezdy",
            "bookingPlatformNickname": "rezdy",
            "bookingPlatformMapping": "operatorPreferred",
            "bookingCodes": [
                {
                    "id": "RZ:578",
                    "label": "Rezdy Tour",
                    "time": null,
                    "duration": "240",
                    "optionPrice": [
                        {
                            "id": 11801,
                            "label": "Bronze Ticket",
                            "price": 20,
                            "pax": 1,
                            "commission": "10",
                            "levy": null,
                            "currency": "AUD"
                        },
                        {
                            "id": 11804,
                            "label": "Silver Ticket",
                            "price": 45,
                            "pax": 1,
                            "commission": "10",
                            "levy": null,
                            "currency": "AUD"
                        },
                        {
                            "id": 11805,
                            "label": "Gold Ticket",
                            "price": 88,
                            "pax": 1,
                            "commission": "10",
                            "levy": null,
                            "currency": "AUD"
                        },
                        {
                            "id": 11806,
                            "label": "Platinum Ticket",
                            "price": 150,
                            "pax": 1,
                            "commission": "10",
                            "levy": null,
                            "currency": "AUD"
                        }
                    ]
                }
            ],
            "productTimes": null,
            "paymentMethods": [
                {
                    "id": "FULL_AGENT",
                    "detail": "Full payment to agent at time of booking.",
                    "default": true
                }
            ],
            "bookingCodesCount": 1,
            "productTimesCount": 0,
            "paymentMethodsCount": 1
        },
        "success": true,
        "cacheTime": "24"
    },
    "queryTime": "809.72ms"
}

```

This endpoint retrieves the basic booking information for the product.


### HTTP Request

`GET https://apis.narnoo.com/api/v1/booking/product/{operator_id}/{product_id}`

### Query Parameters

<aside class="warning">
{product_id} is not the productId in the product list response. It is the {id} found in the product details response
</aside>


Parameter | Required | Description
--------- | ------- |  -----------
operator_id | true | We need to pass the operator's Narnoo ID
product_id | true | We need to pass the operator's Narnoo product ID

### Response Parameters

<aside class="notice">
The bookingData array in the response contains all the information needed to make further product calls down the pipeline.
</aside>

<aside class="warning">
If productTimes exists in the response then future bookingsCode ID need to be in the format bookingCode['id']:productTimes['id']. See the product details call
</aside>

<aside class="notice">
The product prices here might be different to the productOptions in the product details call. This is because some reservation systems request that options without prices not be displayed.
Respax Documentation: https://docs.respax.com/confluence/display/RONR/RON+XML+API+Reference#RONXMLAPIReference-readTourPricesreadTourPrices
</aside>

## Get Product Booking Details

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/booking/details/614/578?id=RZ:578",
  "method": "GET",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "Cache-Control": "no-cache",
    "Postman-Token": "211e6436-18b9-43b0-a0c6-6f707dec3fce"
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
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/booking/details/614/578?id=RZ:578",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
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

url = "https://apis.narnoo.com/api/v1/booking/details/614/578"

querystring = {"id":"RZ:578"}

headers = {
    'Authorization': "bearer xxxxxxxxxxxxxxxxxxxxxxxxxx",
    'Cache-Control': "no-cache"
    }

response = requests.request("GET", url, headers=headers, params=querystring)

print(response.text)
```

```swift
import Foundation

let headers = [
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxx",
  "Cache-Control": "no-cache"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/booking/details/614/578?id=RZ:578")! as URL,
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
        "bookingData": {
            "bookingPlatform": "Rezdy",
            "bookingPlatformNickname": "rezdy",
            "bookingPlatformMapping": "operatorPreferred",
            "bookingCode": {
                "id": "RZ:578"
            },
            "productPrices": [
                {
                    "id": 11801,
                    "label": "Bronze Ticket",
                    "price": 20,
                    "pax": 1,
                    "commission": "10",
                    "levy": null,
                    "currency": "AUD"
                },
                {
                    "id": 11804,
                    "label": "Silver Ticket",
                    "price": 45,
                    "pax": 1,
                    "commission": "10",
                    "levy": null,
                    "currency": "AUD"
                },
                {
                    "id": 11805,
                    "label": "Gold Ticket",
                    "price": 88,
                    "pax": 1,
                    "commission": "10",
                    "levy": null,
                    "currency": "AUD"
                },
                {
                    "id": 11806,
                    "label": "Platinum Ticket",
                    "price": 150,
                    "pax": 1,
                    "commission": "10",
                    "levy": null,
                    "currency": "AUD"
                }
            ],
            "productExtras": false,
            "productPickUps": [
                {
                    "id": "Bellagio Hotel",
                    "label": "Bellagio Hotel"
                }
            ],
            "bookingFields": {
                "perBooking": [
                    {
                        "label": "First Name",
                        "required": true
                    },
                    {
                        "label": "Last Name",
                        "required": true
                    },
                    {
                        "label": "Mobile",
                        "required": true
                    },
                    {
                        "label": "Email",
                        "required": true
                    },
                    {
                        "label": "Country",
                        "required": true
                    },
                    {
                        "label": "Special Requirements",
                        "required": true
                    }
                ]
            },
            "paymentMethods": [
                {
                    "id": "FULL_AGENT",
                    "detail": "Full payment to agent at time of booking.",
                    "default": true
                }
            ],
            "productPricesCount": 4,
            "productExtrasCount": 1,
            "productPickUpsCount": 1,
            "bookingFieldsPerBookingCount": 6,
            "bookingFieldsPerParticipantCount": 0,
            "paymentMethodsCount": 1
        },
        "debug": {
            "bookingPlatform": "Rezdy",
            "bookingPlatformNickname": "rezdy",
            "bookingPlatformMapping": "operatorPreferred",
            "bookingCode": {
                "id": "RZ:578"
            },
            "productPrices": [
                {
                    "id": 11801,
                    "label": "Bronze Ticket",
                    "price": 20,
                    "pax": 1,
                    "commission": "10",
                    "levy": null,
                    "currency": "AUD"
                },
                {
                    "id": 11804,
                    "label": "Silver Ticket",
                    "price": 45,
                    "pax": 1,
                    "commission": "10",
                    "levy": null,
                    "currency": "AUD"
                },
                {
                    "id": 11805,
                    "label": "Gold Ticket",
                    "price": 88,
                    "pax": 1,
                    "commission": "10",
                    "levy": null,
                    "currency": "AUD"
                },
                {
                    "id": 11806,
                    "label": "Platinum Ticket",
                    "price": 150,
                    "pax": 1,
                    "commission": "10",
                    "levy": null,
                    "currency": "AUD"
                }
            ],
            "productExtras": false,
            "productPickUps": [
                {
                    "id": "Bellagio Hotel",
                    "label": "Bellagio Hotel"
                }
            ],
            "bookingFields": {
                "perBooking": [
                    {
                        "label": "First Name",
                        "required": true
                    },
                    {
                        "label": "Last Name",
                        "required": true
                    },
                    {
                        "label": "Mobile",
                        "required": true
                    },
                    {
                        "label": "Email",
                        "required": true
                    },
                    {
                        "label": "Country",
                        "required": true
                    },
                    {
                        "label": "Special Requirements",
                        "required": true
                    }
                ]
            },
            "paymentMethods": [
                {
                    "id": "FULL_AGENT",
                    "detail": "Full payment to agent at time of booking.",
                    "default": true
                }
            ],
            "productPricesCount": 4,
            "productExtrasCount": 1,
            "productPickUpsCount": 1,
            "bookingFieldsPerBookingCount": 6,
            "bookingFieldsPerParticipantCount": 0,
            "paymentMethodsCount": 1
        },
        "success": true,
        "cacheTime": "24"
    },
    "queryTime": "1228.73ms"
}
```

This endpoint retrieves the basic product information and also important booking information.


### HTTP Request

`GET https://apis.narnoo.com/api/v1/booking/details/{operator_id}/{product_id}?id=<bookingCode>`

### Query Parameters

<aside class="warning">
If productTimes exists in the response then future bookingsCode ID need to be in the format bookingCode['id']:productTimes['id']. See the product details call
</aside>

Parameter | Required | Description
--------- | ------- |  -----------
{operator_id} | true | We need to pass the operator's Narnoo ID
{product_id} | true | We need to pass the operator's Narnoo product ID
bookingCode | true | Passed in the id parameter. This bookingCode is found in the [product details call](#get-product-booking-information) and is the combination of bookingCode and productTimes ( if productTimes exists )

### Response Parameters

<aside class="notice">
The bookingData array in the response contains all the information needed to make further product calls down the pipeline.
</aside>

Parameter |  Type |  Description
--------- | ------- | -------
productPrices | Array |  Returns the prices of each of the product types. If a levy exists this will be displayed here.
productExtras | Array | Any additional extras that can be included in the booking.
productPickUps | Array | Any pickup locations. Can be used further down the pipline to request pricing based on transfers.
bookingFields | Array | The resevation systems require specific form fields to be filled out. This array contains all the booking form information.
paymentMethods | Array | This is your agents payment method options. See Payment Methods for detailed descriptions of these.

<aside class="notice">
The product prices here might be different to the productOptions in the product details call. This is because some reservation systems request that options without prices not be displayed.
Respax Documentation: https://docs.respax.com/confluence/display/RONR/RON+XML+API+Reference#RONXMLAPIReference-readTourPricesreadTourPrices
</aside>

## Get Product Availability and Pricing Details

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/booking/availability/614/578?id=RZ:578&startDate=10-08-2018&endDate=30-08-2018",
  "method": "POST",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxxx",
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
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/booking/availability/614/578?id=RZ:578&startDate=10-08-2018&endDate=30-08-2018",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
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

url = "https://apis.narnoo.com/api/v1/booking/availability/614/578"

querystring = {"id":"RZ:578","startDate":"10-08-2018","endDate":"30-08-2018"}

headers = {
    'Authorization': "bearer xxxxxxxxxxxxxxxxxxxxxxxxx",
    'Cache-Control': "no-cache"
    }

response = requests.request("POST", url, headers=headers, params=querystring)

print(response.text)
```

```swift
import Foundation

let headers = [
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxx",
  "Cache-Control": "no-cache"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/booking/availability/614/578?id=RZ:578&startDate=10-08-2018&endDate=30-08-2018")! as URL,
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
    {
    "success": true,
    "data": {
        "bookingPlatform": "Rezdy",
        "bookingPlatformNickname": "rezdy",
        "bookingPlatformMapping": "operatorPreferred",
        "bookingData": {
            "bookingCode": {
                "id": "RZ:578"
            }
        },
        "availabilityStartDate": "2018-08-10 00:00:00",
        "availabilityEndDate": "2018-08-11 00:00:00",
        "productAvailability": [
            {
                "bookingDate": "2018-08-10 09:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-10 10:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-10 11:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-10 12:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-10 14:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-10 15:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-10 16:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-10 17:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-11 09:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-11 10:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-11 11:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-11 12:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-11 14:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-11 15:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-11 16:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": "2018-08-11 17:00:00",
                "availability": 999,
                "totalAvailability": null,
                "price": [
                    {
                        "id": 11801,
                        "price": 20,
                        "label": "Bronze Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11804,
                        "price": 45,
                        "label": "Silver Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11805,
                        "price": 88,
                        "label": "Gold Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    },
                    {
                        "id": 11806,
                        "price": 150,
                        "label": "Platinum Ticket",
                        "pax": 1,
                        "commission": null,
                        "levy": null,
                        "currency": null
                    }
                ]
            },
            {
                "bookingDate": null,
                "availability": null,
                "totalAvailability": null,
                "price": null
            }
        ],
        "productAvailabilityCount": 17,
        "cacheTime": "24",
        "success": true
    },
    "queryTime": "710.01ms"
}

```

This endpoint retrieves the availability and prices.


### HTTP Request

`GET https://apis.narnoo.com/api/v1/booking/availability/{operator_id}/{product_id}?id={bookingCode}&startDate=<d-m-Y>&endDate=<d-m-Y>`

### Query Parameters


Parameter | Required | Description
--------- | ------- |  -----------
{operator_id} | true | We need to pass the operator's Narnoo ID
{product_id} | true | We need to pass the operator's Narnoo product ID
bookingCode | true | Passed in the id parameter. This bookingCode is found in the [product details call](#get-product-booking-information) and is the combination of bookingCode and productTimes ( if productTimes exists )
startDate | true | The first day we want to check availability for. Date formate ( d-M-Y )
endDate | true | The last day we want to check availability for. Date formate ( d-M-Y )


### Response Parameters

Parameter |  Type |  Description
--------- | ------- | -------
[productAvailability][availability] | integer |  containing available seats.
[productAvailability][availability][bookingDate]  | date time |  This needs to be sent over to the reservation write when creating a booking
[productAvailability][price] | float |  containing the price of the seat for each option.

<aside class="notice">
The product prices here might be different to the productOptions in the product details call. This is because some reservation systems request that options without prices not be displayed.
Respax Documentation: https://docs.respax.com/confluence/display/RONR/RON+XML+API+Reference#RONXMLAPIReference-readTourPricesreadTourPrices
</aside>
