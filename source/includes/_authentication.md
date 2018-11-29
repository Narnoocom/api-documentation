# Authentication

To authenticate with our API you will require a access key and a secret key. These keys can be obtained from your Narnoo account.

It's similar to a social network where you create lists of businesses that your business follows.

## Authentication

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://apis.narnoo.com/api/v1/authenticate/token",
  "method": "GET",
  "headers": {
    "API-KEY": "xxxxxxxxxxxxxxxx",
    "API-SECRET-KEY": "xxxxxxxxxxxxxxxxxxxxxxxxx",
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
  CURLOPT_URL => "https://apis.narnoo.com/api/v1/authenticate/token",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "API-KEY: xxxxxxxxxxxxxxxxxxxxx",
    "API-SECRET-KEY: xxxxxxxxxxxxxxxxxxxxxxxxx",
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

url = "https://apis.narnoo.com/api/v1/authenticate/token"

headers = {
    'API-KEY': "xxxxxxxxxxxxxxxxxxx",
    'API-SECRET-KEY': "xxxxxxxxxxxxxxxxxxx",
    'Cache-Control': "no-cache"
    }

response = requests.request("GET", url, headers=headers)

print(response.text)
```

```swift
import Foundation

let headers = [
  "API-KEY": "xxxxxxxxxxxxxxxxxxx",
  "API-SECRET-KEY": "xxxxxxxxxxxxxxxxxxx",
  "Cache-Control": "no-cache"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://apis.narnoo.com/api/v1/authenticate/token")! as URL,
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
    "status": true,
    "token": "xxxxxxxxxxxxxxxxxxx",
    "queryTime": "32.35ms"
}
```

This endpoint retrieves a token which will be used for further authentication to our API.


### HTTP Request

`GET https://apis.narnoo.com/api/v1/authenticate/token`

### Response Parameters

[token] is used for further authentication with our API

