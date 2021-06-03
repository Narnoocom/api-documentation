# Validation

The valdiate booking endpoint performs all the live reservation check task. This endpoint should be triggered before the reservation call to make sure the booking can go through. Issues such as availability / pick ups and extras could in some instances cause a booking to fall over. By calling this endpoint before the live reservation you can catch any potential errors.

## Validate Reservation
The same data sent to this endpoint must be sent to the live reservations endpoint.

An array with the results of each of the checks. The booking is valid if "bookable"= true.

If there is an issue with the booking request "bookable" = false. We try are best to reply with a "message" that describes the issue in detail.

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/booking/validate",
  "method": "POST",
  "headers": {
    "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "Content-Type": "application/json",
    "Cache-Control": "no-cache"
  },
  "data": "{\"contact\":{\"firstName\":\"Jon”,”lastName”:”Doe”,”email”:”jon.doe@gmail.com\",\"phone”:”123457890\",\"country\":\"Australia\"},\"payment\":{\"type\":\"CREDITCARD\",\"currency\":\"AUD\"},\"products\":[{\"productId\":578,\"bookingCode\":\"RZ:578\",\"bookingDate\":\"2018-07-25 09:00:00\",\"paymentMethod\":\"FULL_AGENT\",\"option\":[{\"id\":\"11801\",\"label\":\"Bronze Ticket\",\"quantity\":2,\"price\":20}],\"pickUp\":{\"id\":\"To Be Advised\"},\"participants\":[[{\"label\":\"First Name\",\"value\":\"Jon”},{“label\":\"Last Name\",\"value”:”Doe”},{“label\":\"Country\",\"value\":\"Australia\"}],[{\"label\":\"First Name\",\"value”:”Jane”},{“label\":\"Last Name\",\"value”:”Doe”},{“label\":\"Country\",\"value\":\"Australia\"}]],\"bookingForm\":[{\"label\":\"Special Requirements\",\"value\":\"None\"},{\"label\":\"Mobile\",\"value\":\"0412194550\"}]}]}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/booking/validate",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "{\"contact\":{\"firstName\":\"Jon”,”lastName”:”Doe”,”email”:”jon.doe@gmail.com\",\"phone”:”123457890\",\"country\":\"Australia\"},\"payment\":{\"type\":\"CREDITCARD\",\"currency\":\"AUD\"},\"products\":[{\"productId\":578,\"bookingCode\":\"RZ:578\",\"bookingDate\":\"2018-07-25 09:00:00\",\"paymentMethod\":\"FULL_AGENT\",\"option\":[{\"id\":\"11801\",\"label\":\"Bronze Ticket\",\"quantity\":2,\"price\":20}],\"pickUp\":{\"id\":\"To Be Advised\"},\"participants\":[[{\"label\":\"First Name\",\"value\":\"Jon”},{“label\":\"Last Name\",\"value”:”Doe”},{“label\":\"Country\",\"value\":\"Australia\"}],[{\"label\":\"First Name\",\"value”:”Jane”},{“label\":\"Last Name\",\"value”:”Doe”},{“label\":\"Country\",\"value\":\"Australia\"}]],\"bookingForm\":[{\"label\":\"Special Requirements\",\"value\":\"None\"},{\"label\":\"Mobile\",\"value\":\"0412194550\"}]}]}",
  CURLOPT_HTTPHEADER => array(
    "Authorization: bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
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

url = "https://apis.narnoo.com/api/v1/booking/validate"

payload = "{\"contact\":{\"firstName\":\"Jon”,”lastName”:”Doe”,”email”:”jon.doe@gmail.com\",\"phone”:”123457890\",\"country\":\"Australia\"},\"payment\":{\"type\":\"CREDITCARD\",\"currency\":\"AUD\"},\"products\":[{\"productId\":578,\"bookingCode\":\"RZ:578\",\"bookingDate\":\"2018-07-25 09:00:00\",\"paymentMethod\":\"FULL_AGENT\",\"option\":[{\"id\":\"11801\",\"label\":\"Bronze Ticket\",\"quantity\":2,\"price\":20}],\"pickUp\":{\"id\":\"To Be Advised\"},\"participants\":[[{\"label\":\"First Name\",\"value\":\"Jon”},{“label\":\"Last Name\",\"value”:”Doe”},{“label\":\"Country\",\"value\":\"Australia\"}],[{\"label\":\"First Name\",\"value”:”Jane”},{“label\":\"Last Name\",\"value”:”Doe”},{“label\":\"Country\",\"value\":\"Australia\"}]],\"bookingForm\":[{\"label\":\"Special Requirements\",\"value\":\"None\"},{\"label\":\"Mobile\",\"value\":\"0412194550\"}]}]}"
headers = {
    'Authorization': "bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    'Content-Type': "application/json",
    'Cache-Control': "no-cache"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```

```swift
import Foundation

let headers = [
  "Authorization": "bearer xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
  "Content-Type": "application/json",
  "Cache-Control": "no-cache"
]

let postData = NSData(data: "{"contact":{"firstName":"Jon”,”lastName”:”Doe”,”email”:”jon.doe@gmail.com","phone”:”123457890","country":"Australia"},"payment":{"type":"CREDITCARD","currency":"AUD"},"products":[{"productId":578,"bookingCode":"RZ:578","bookingDate":"2018-07-25 09:00:00","paymentMethod":"FULL_AGENT","option":[{"id":"11801","label":"Bronze Ticket","quantity":2,"price":20}],"pickUp":{"id":"To Be Advised"},"participants":[[{"label":"First Name","value":"Jon”},{“label":"Last Name","value”:”Doe”},{“label":"Country","value":"Australia"}],[{"label":"First Name","value”:”Jane”},{“label":"Last Name","value”:”Doe”},{“label":"Country","value":"Australia"}]],"bookingForm":[{"label":"Special Requirements","value":"None"},{"label":"Mobile","value":"0412194550"}]}]}".data(using: String.Encoding.utf8)!)

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/booking/validate")! as URL,
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
            "bookable": true,
            "productId": 578
        }
    ],
    "queryTime": "1250.47ms"
}
```

### HTTP Request

`POST https://apis.narnoo.com/api/v1/booking/valdiate`

### Query Parameters


Sample JSON PAYLOAD

```json

{
  "contact": {
    "firstName": "Jon",
    "lastName": "Doe",
    "email": "jon.doe@gmail.com",
    "phone": "1234567890",
    "country": "Australia"
  },
  "payment": {
    "type": "CREDITCARD",
    "currency": "AUD"
  },
  "products": [
    {
      "productId": 578,
      "bookingCode": "RZ:578",
      "bookingDate": "2018-07-25 09:00:00",
      "paymentMethod": "FULL_AGENT",
      "option": [
        {
          "id": "11801",
          "label": "Bronze Ticket",
          "quantity": 2,
          "price": 20
        }
      ],
      "pickUp": {
        "id": "C08R1:167:132"
      },
      "participants": [
        [
          {
            "label": "First Name",
            "value": "Jon"
          },
          {
            "label": "Last Name",
            "value": "Doe"
          },
          {
            "label": "Country",
            "value": "Australia"
          }
        ],
        [
          {
            "label": "First Name",
            "value": "Jane"
          },
          {
            "label": "Last Name",
            "value": "Doe"
          },
          {
            "label": "Country",
            "value": "Australia"
          }
        ]
      ],
      "bookingForm": [
        {
          "label": "Special Requirements",
          "value": "None"
        },
        {
          "label": "Mobile",
          "value": "1234567890"
        }
      ]
    }
  ]
}
```

### Sample Response


```json
{
    "success": true,
    "data": [
        {
            "error": true,
            "bookable": false,
            "productId": 578,
            "message": "Insufficient route availability for the specified pickup."
        }
    ],
    "queryTime": "1735.53ms"
}
```