# Reservation

The reservation endpoint performs all the live reservation tasks. This endpoint submits reservation details to the nominated products reservation system.

## Create Reservation

<aside class="notice">
Reservation API details are being updated.
</aside>

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/booking/create",
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
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/booking/create",
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

url = "https://apis.narnoo.com/api/v1/booking/create"

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

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/booking/create")! as URL,
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
    "data": {
        "request": {
            "booking": [
                {
                    "reservationProvider": "Rezdy",
                    "confirmed": true,
                    "reservationCode": "DU000103",
                    "productId": 578,
                    "productBookingCode": "RZ:578",
                    "bookingDate": "2018-07-26 09:00:00",
                    "reservationProductName": null,
                    "reservationPaymentOption": "FULL_AGENT"
                }
            ],
            "success": true,
            "bookingCount": 1,
            "queryTime": "2674.86ms"
        }
    },
    "queryTime": "3050.35ms"
}
```

### HTTP Request

`POST https://apis.narnoo.com/api/v1/booking/create`

### Query Parameters

<aside class="notice">
This is an example response - we will update information on each for more detail.
</aside>


A JSON PAYLOAD

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
        "id": "To Be Advised"
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



