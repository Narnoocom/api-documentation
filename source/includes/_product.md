# Product

## Get Product Details

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://connect.narnoo.com/v1/product/details/91/491",
  "method": "GET",
  "headers": {
    "api-key": "xxxxxxxxxxxxxxxxxx",
    "api-secret-key": "xxxxxxxxxxxxxxxxxx",
    "authorization": "xxxxxxxxxxxxxxxxxx"
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
  CURLOPT_URL => "https://connect.narnoo.com/v1/product/details/91/491",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "api-key: xxxxxxxxxxxxxxxxxx",
    "api-secret-key: xxxxxxxxxxxxxxxxxx",
    "authorization: xxxxxxxxxxxxxxxxxx"
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

conn.request("GET", "/v1/product/details/91/491", headers=headers)

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

let request = NSMutableURLRequest(url: NSURL(string: "https://connect.narnoo.com/v1/product/details/91/491")! as URL,
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
  "productInformation": {
    "id": "491",
    "uniqueId": "118576286",
    "title": "Ocean Spirit Cruises",
    "dateCreated": "2017-03-30 09:32:32",
    "dateModified": null,
    "businessUrl": "http://www.oceanspirit.com.au/",
    "businessEmail": "xxxxx@quicksilvergroup.com.au",
    "businessState": "QLD",
    "businessCountry": "Australia",
    "location": "Reef Fleet Terminal 1 Spence Street, Cairns QLD 4870, Australia",
    "latitude": "-16.9218184032553",
    "longitude": "145.780138097931",
    "productSummary": {
      "createdAt": "30-03-2017 09:32",
      "text": "Please check-in at the Ocean Spirit/Great Adventures reservations counter inside the Cairns Reef Fleet Terminal on 1 Spence St between 7:30 and 8:00am. Ocean Spirit departs the marina at 8:30am. \n\nOur staff will issue you with your boarding pass and direct you to our vessel.\n\nPlease note:\nIf you have selected the \"Pay On Board\" option you must reconfirm your booking within 24 hours of travel by contacting our reservations team. If not, Quicksilver Connections reserves the right to cancel",
      "language": "english"
    },
    "logo": {
      "logoId": "107",
      "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/logo/crop_Ocean-Spirit-Cruises-VRx7xsylNrZPG63.jpg",
      "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/logo/thumb_Ocean-Spirit-Cruises-VRx7xsylNrZPG63.jpg",
      "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/logo/preview_Ocean-Spirit-Cruises-VRx7xsylNrZPG63.jpg",
      "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/logo/large_Ocean-Spirit-Cruises-VRx7xsylNrZPG63.jpg",
      "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/logo/200_Ocean-Spirit-Cruises-VRx7xsylNrZPG63.jpg",
      "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/logo/400_Ocean-Spirit-Cruises-VRx7xsylNrZPG63.jpg",
      "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/logo/800_Ocean-Spirit-Cruises-VRx7xsylNrZPG63.jpg"
    },
    "image": null,
    "productDiscription": {
      "created_at": "30-03-2017 09:32",
      "text": "Please check-in at the Ocean Spirit/Great Adventures reservations counter inside the Cairns Reef Fleet Terminal on 1 Spence St between 7:30 and 8:00am. Ocean Spirit departs the marina at 8:30am. \n\nOur staff will issue you with your boarding pass and direct you to our vessel.\n\nPlease note:\nIf you have selected the \"Pay On Board\" option you must reconfirm your booking within 24 hours of travel by contacting our reservations team. If not, Quicksilver Connections reserves the right to cancel your booking.",
      "language": "english"
    },
    "productImages": [
      {
        "imageId": "3812",
        "entryDate": "2014-08-05 17:55:10",
        "xcropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xcrop/xcrop_Ocean-Spirit-Cruises-EWOvK436xZqMc64.jpg",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/crop/crop_Ocean-Spirit-Cruises-EWOvK436xZqMc64.jpg",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/thumb/thumb_Ocean-Spirit-Cruises-EWOvK436xZqMc64.jpg",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/preview/preview_Ocean-Spirit-Cruises-EWOvK436xZqMc64.jpg",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/large/large_Ocean-Spirit-Cruises-EWOvK436xZqMc64.jpg",
        "xlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xlarge/xlarge_Ocean-Spirit-Cruises-EWOvK436xZqMc64.jpg",
        "xxlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xxlarge/xxlarge_Ocean-Spirit-Cruises-EWOvK436xZqMc64.jpg",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/200/200_Ocean-Spirit-Cruises-EWOvK436xZqMc64.jpg",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/400/400_Ocean-Spirit-Cruises-EWOvK436xZqMc64.jpg",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/800/800_Ocean-Spirit-Cruises-EWOvK436xZqMc64.jpg",
        "imageCaption": "Introductory Scuba Diving at Michaelmas Cay"
      },
      {
        "imageId": "3813",
        "entryDate": "2014-08-05 17:56:00",
        "xcropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xcrop/xcrop_Ocean-Spirit-Cruises-FIUfQIKN9Yz1qaE.jpg",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/crop/crop_Ocean-Spirit-Cruises-FIUfQIKN9Yz1qaE.jpg",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/thumb/thumb_Ocean-Spirit-Cruises-FIUfQIKN9Yz1qaE.jpg",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/preview/preview_Ocean-Spirit-Cruises-FIUfQIKN9Yz1qaE.jpg",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/large/large_Ocean-Spirit-Cruises-FIUfQIKN9Yz1qaE.jpg",
        "xlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xlarge/xlarge_Ocean-Spirit-Cruises-FIUfQIKN9Yz1qaE.jpg",
        "xxlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xxlarge/xxlarge_Ocean-Spirit-Cruises-FIUfQIKN9Yz1qaE.jpg",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/200/200_Ocean-Spirit-Cruises-FIUfQIKN9Yz1qaE.jpg",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/400/400_Ocean-Spirit-Cruises-FIUfQIKN9Yz1qaE.jpg",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/800/800_Ocean-Spirit-Cruises-FIUfQIKN9Yz1qaE.jpg",
        "imageCaption": "OCEAN SPIRIT Beach"
      },
      {
        "imageId": "3814",
        "entryDate": "2014-08-05 17:57:33",
        "xcropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xcrop/xcrop_Ocean-Spirit-Cruises-mvuyOeI2sHc35OY.jpg",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/crop/crop_Ocean-Spirit-Cruises-mvuyOeI2sHc35OY.jpg",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/thumb/thumb_Ocean-Spirit-Cruises-mvuyOeI2sHc35OY.jpg",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/preview/preview_Ocean-Spirit-Cruises-mvuyOeI2sHc35OY.jpg",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/large/large_Ocean-Spirit-Cruises-mvuyOeI2sHc35OY.jpg",
        "xlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xlarge/xlarge_Ocean-Spirit-Cruises-mvuyOeI2sHc35OY.jpg",
        "xxlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xxlarge/xxlarge_Ocean-Spirit-Cruises-mvuyOeI2sHc35OY.jpg",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/200/200_Ocean-Spirit-Cruises-mvuyOeI2sHc35OY.jpg",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/400/400_Ocean-Spirit-Cruises-mvuyOeI2sHc35OY.jpg",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/800/800_Ocean-Spirit-Cruises-mvuyOeI2sHc35OY.jpg",
        "imageCaption": "Michaelmas Cay, a vegetated sand cay"
      },
      {
        "imageId": "3815",
        "entryDate": "2014-08-05 17:58:31",
        "xcropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xcrop/xcrop_Ocean-Spirit-Cruises-3zAx5Vb4InT9xIs.jpg",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/crop/crop_Ocean-Spirit-Cruises-3zAx5Vb4InT9xIs.jpg",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/thumb/thumb_Ocean-Spirit-Cruises-3zAx5Vb4InT9xIs.jpg",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/preview/preview_Ocean-Spirit-Cruises-3zAx5Vb4InT9xIs.jpg",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/large/large_Ocean-Spirit-Cruises-3zAx5Vb4InT9xIs.jpg",
        "xlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xlarge/xlarge_Ocean-Spirit-Cruises-3zAx5Vb4InT9xIs.jpg",
        "xxlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xxlarge/xxlarge_Ocean-Spirit-Cruises-3zAx5Vb4InT9xIs.jpg",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/200/200_Ocean-Spirit-Cruises-3zAx5Vb4InT9xIs.jpg",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/400/400_Ocean-Spirit-Cruises-3zAx5Vb4InT9xIs.jpg",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/800/800_Ocean-Spirit-Cruises-3zAx5Vb4InT9xIs.jpg",
        "imageCaption": "Snorkelling at Michaelmas Cay"
      },
      {
        "imageId": "3816",
        "entryDate": "2014-08-05 17:59:40",
        "xcropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xcrop/xcrop_Ocean-Spirit-Cruises-1eCmqexSdBqj90k.jpg",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/crop/crop_Ocean-Spirit-Cruises-1eCmqexSdBqj90k.jpg",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/thumb/thumb_Ocean-Spirit-Cruises-1eCmqexSdBqj90k.jpg",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/preview/preview_Ocean-Spirit-Cruises-1eCmqexSdBqj90k.jpg",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/large/large_Ocean-Spirit-Cruises-1eCmqexSdBqj90k.jpg",
        "xlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xlarge/xlarge_Ocean-Spirit-Cruises-1eCmqexSdBqj90k.jpg",
        "xxlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xxlarge/xxlarge_Ocean-Spirit-Cruises-1eCmqexSdBqj90k.jpg",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/200/200_Ocean-Spirit-Cruises-1eCmqexSdBqj90k.jpg",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/400/400_Ocean-Spirit-Cruises-1eCmqexSdBqj90k.jpg",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/800/800_Ocean-Spirit-Cruises-1eCmqexSdBqj90k.jpg",
        "imageCaption": "Aboard 32 metre sailing cat Ocean Spirit"
      },
      {
        "imageId": "3817",
        "entryDate": "2014-08-05 18:00:30",
        "xcropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xcrop/xcrop_Ocean-Spirit-Cruises-Nl4zms0tTNn971j.jpg",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/crop/crop_Ocean-Spirit-Cruises-Nl4zms0tTNn971j.jpg",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/thumb/thumb_Ocean-Spirit-Cruises-Nl4zms0tTNn971j.jpg",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/preview/preview_Ocean-Spirit-Cruises-Nl4zms0tTNn971j.jpg",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/large/large_Ocean-Spirit-Cruises-Nl4zms0tTNn971j.jpg",
        "xlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xlarge/xlarge_Ocean-Spirit-Cruises-Nl4zms0tTNn971j.jpg",
        "xxlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xxlarge/xxlarge_Ocean-Spirit-Cruises-Nl4zms0tTNn971j.jpg",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/200/200_Ocean-Spirit-Cruises-Nl4zms0tTNn971j.jpg",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/400/400_Ocean-Spirit-Cruises-Nl4zms0tTNn971j.jpg",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/800/800_Ocean-Spirit-Cruises-Nl4zms0tTNn971j.jpg",
        "imageCaption": "Safe snorkelling from the protected shallow waters"
      },
      {
        "imageId": "3818",
        "entryDate": "2014-08-05 18:01:11",
        "xcropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xcrop/xcrop_Ocean-Spirit-Cruises-s977ccQXi4D5xbE.jpg",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/crop/crop_Ocean-Spirit-Cruises-s977ccQXi4D5xbE.jpg",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/thumb/thumb_Ocean-Spirit-Cruises-s977ccQXi4D5xbE.jpg",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/preview/preview_Ocean-Spirit-Cruises-s977ccQXi4D5xbE.jpg",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/large/large_Ocean-Spirit-Cruises-s977ccQXi4D5xbE.jpg",
        "xlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xlarge/xlarge_Ocean-Spirit-Cruises-s977ccQXi4D5xbE.jpg",
        "xxlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xxlarge/xxlarge_Ocean-Spirit-Cruises-s977ccQXi4D5xbE.jpg",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/200/200_Ocean-Spirit-Cruises-s977ccQXi4D5xbE.jpg",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/400/400_Ocean-Spirit-Cruises-s977ccQXi4D5xbE.jpg",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/800/800_Ocean-Spirit-Cruises-s977ccQXi4D5xbE.jpg",
        "imageCaption": "Discover the island bird life"
      },
      {
        "imageId": "4942",
        "entryDate": "2016-01-13 13:18:01",
        "xcropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xcrop/xcrop_Ocean-Spirit-Cruises-2yJfmEUXx7xX1Zf.jpg",
        "cropImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/crop/crop_Ocean-Spirit-Cruises-2yJfmEUXx7xX1Zf.jpg",
        "thumbImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/thumb/thumb_Ocean-Spirit-Cruises-2yJfmEUXx7xX1Zf.jpg",
        "previewImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/preview/preview_Ocean-Spirit-Cruises-2yJfmEUXx7xX1Zf.jpg",
        "largeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/large/large_Ocean-Spirit-Cruises-2yJfmEUXx7xX1Zf.jpg",
        "xlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xlarge/xlarge_Ocean-Spirit-Cruises-2yJfmEUXx7xX1Zf.jpg",
        "xxlargeImagePath": "//dmxhl5sgly8nk.cloudfront.net/op_91/xxlarge/xxlarge_Ocean-Spirit-Cruises-2yJfmEUXx7xX1Zf.jpg",
        "image200Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/200/200_Ocean-Spirit-Cruises-2yJfmEUXx7xX1Zf.jpg",
        "image400Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/400/400_Ocean-Spirit-Cruises-2yJfmEUXx7xX1Zf.jpg",
        "image800Path": "//dmxhl5sgly8nk.cloudfront.net/op_91/800/800_Ocean-Spirit-Cruises-2yJfmEUXx7xX1Zf.jpg",
        "imageCaption": "OCEAN SPIRIT Micahelmas Cay"
      }
    ],
    "productVideo": null,
    "productFeatures": null
  },
  "bookingData": {
    "bookingPlatform": "Respax",
    "bookingPlatformNickname": "respax",
    "bookingPlatformMapping": "operatorPreferred",
    "bookingCodes": [
      {
        "id": "RP:751:2526",
        "label": "Standard / 8:30 - 17:00 - Standard",
        "time": null,
        "duration": 1440
      }
    ],
    "productOptions": [
      {
        "id": 1,
        "label": "Adult",
        "price": null,
        "currency": null
      },
      {
        "id": 2,
        "label": "Infant",
        "price": null,
        "currency": null
      },
      {
        "id": 3,
        "label": "Child",
        "price": null,
        "currency": null
      },
      {
        "id": 4,
        "label": "Family Child",
        "price": null,
        "currency": null
      }
    ],
    "productTimes": [
      {
        "id": 486,
        "time": "08:30:00",
        "default": true
      }
    ],
    "paymentMethods": [
      {
        "id": "FULL_SUPPLIER",
        "detail": "Full payment to supplier paid to supplier on day.",
        "default": false
      }
    ],
    "bookingCodesCount": 1,
    "productOptionsCount": 4,
    "productTimesCount": 1,
    "paymentMethodsCount": 1
  },
  "success": true,
  "cacheTime": "24",
  "queryTime": "6668.29ms"
}
```

This endpoint retrieves the details for this operator's product.
Basic product information is returned along with the important booking information.

### HTTP Request

`GET https://connect.narnoo.com/v1/product/details/<id>/<productId>`

### Query Parameters

Parameter | Required | Description
--------- | ------- |  -----------
id | true | We need to pass the operator's Narnoo ID
productId | true | We need to pass the operator's Narnoo product ID

### Response Parameters

<aside class="notice">
The bookingData array in the response contains all the information needed to make further product calls down the pipeline.
</aside>

Parameter |  Type |  Description
--------- | ------- | -------
bookingCodes | Array |  These are the booking codes which need to be passed in future API calls. These identify the bookable product.
productTimes | Array |  If productTimes is not NULL then a productTimes 'id' must be appended to the bookingCode 'id' for future API calls. Reservation systems such as Respax and Website Travel require times when checking availability and pricing.
paymentMethods | Array | This is your agents payment method options. See Payment Methods for detailed descriptions of these.

<aside class="warning">
If productTimes exists in the response then future bookingsCode ID need to be in the format bookingCode['id']:productTimes['id']
</aside>
