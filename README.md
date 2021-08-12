## FloppySend Email API

Floppy Email API is RESTful, fully-featured, and easy to integrate with. You can use HTTP/REST API for your programming language to make HTTP calls.

To use our Email API, you need an API key in order to be identified within our system. It is provided to you at registration.
Your API token is a request payload token that can be found for change in your API page in your [dashboard](https://email.floppysend.com/).
The API token does not change with every request, so make sure to make it safe like your password.

### New List

Create a new list with FloppyEmail API, Follow the instructions and ingrate our API with your system or application

Request Types
 - POST METHOD
```
https://email.floppysend.com/api/v1/lists
```
```
https://email.floppysend.com/api/v1/lists?api_token={your_api_token}
&name={new-list_name}&
from_email={list_from_email}&
from_name={list_from_nam}&
default_subject={list_default_subjet}&
contact[company]={list_contact_company}&
contact[state]={list_contact_state}&
contact[address_1]={list_contact_address_1}&
contact[address_2]={list_contact_address_2}&
contact[city]={list_contact_city}&
contact[zip]={list_contact_zip_code}&
contact[phone]={list_contact_phone}&
contact[country_id]={list_country_id}&
contact[email]={list_contact-email}&
contact[url]={list_contact-website}&
subscribe_confirmation={1_or_0}&
send_welcome_email={1_or_0}&
unsubscribe_notification={1_or_0}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |
  | name | String | Yes | New list name |
  | from_email | String | Yes | List from email |
  | from_name | String | Yes | List from name |
  | default_subject | String | Optional | List email subject |
  | contact[company] | String | Yes | List company name |
  | contact[state] | String | Yes | List contact state |
  | contact[address_1] | String | Yes | List contact first address |
  | contact[address_2] | String | Optional | List contact second address |
  | contact[city] | String | Yes | List contact city |
  | contact[zip] | String | Yes | List contact zip code |
  | contact[phone] | String | Optional | List contact phone |
  | contact[country_id] | String | Yes | List contact country id |
  | contact[email] | String | Yes | List contact email |
  | contact[url] | String | Optional | List contact website |
  | subscribe_confirmation | String | Optional | List subscribe send confirmation(boolean) |
  | send_welcome_email | String | Optional | List send welcome email(boolean) |
  | unsubscribe_notification | String | Optional | List notification(boolean) |

#### New List API Responses
```JSON
{
    "status": 1,
    "message": "List was successfully created",
    "list_uid": "60e3c41469"
}
```

#### New List API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/lists?api_token={your_api_token}&name={list_name}&from_email={list_from_email}&from_name={list_from_name}&default_subject={list_default_subject}&contact%5Bcompany%5D={list_contact_company}&contact%5Bstate%5D={list_contact_state}&contact%5Baddress_1%5D={list_ontact_address_1}&contact%5Baddress_2%5D={list_contact_address_2}&contact%5Bcity%5D={list_ontact_city}&contact%5Bzip%5D={list_contact_zip_code}&contact%5Bphone%5D={list_contact_phone}&contact%5Bcountry_id%5D={list_contact_country_id}&contact%5Bemail%5D={list_contact_email}&contact%5Burl%5D={list_contact_website}&subscribe_confirmation={1_or_0}&send_welcome_email={1_or_0}&unsubscribe_notification={1_or_0}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_HTTPHEADER => array(
    'Cookie: XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/lists?api_token={your_api_token}&name={list_name}&from_email={list_from_email}&from_name={list_from_name}&default_subject={list_default_subject}&contact[company]={list_contact_company}&contact[state]={list-contact_state}&contact[address_1]={list_contact_address_1}&contact[address_2]={list_contact_address_2}&contact[city]={list_contact_city}&contact[zip]={list_contact_zip_code}&contact[phone]={list_contact_phone}&contact[country_id]={list_contact_country_id}&contact[email]={list_contact_email}&contact[url]={list_contact_website}&subscribe_confirmation={1_or_0}&send_welcome_email={1_or_0}&unsubscribe_notification={1_or_0}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Post.new(url)
request["Cookie"] = "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D"

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "");
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/lists?api_token={your_api_token}&name={list_name}&from_email={list_from_email}&from_name={list_from_name}&default_subject={list_default_subject}&contact[company]={list_contact_company}&contact[state]={list-contact_state}&contact[address_1]={list_contact_address_1}&contact[address_2]={list_contact_address_2}&contact[city]={list_contact_city}&contact[zip]={list_contact_zip_code}&contact[phone]={list_contact_phone}&contact[country_id]={list_contact_country_id}&contact[email]={list_contact_email}&contact[url]={list_contact_website}&subscribe_confirmation={1_or_0}&send_welcome_email={1_or_0}&unsubscribe_notification={1_or_0}")
  .method("POST", body)
  .addHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D")
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/lists?api_token={your_api_token}&name={list_name}&from_email={list_from_email}&from_name={list_from_name}&default_subject={list_default_subject}&contact[company]={list_contact_company}&contact[state]={list-contact_state}&contact[address_1]={list_contact_address_1}&contact[address_2]={list_contact_address_2}&contact[city]={list_contact_city}&contact[zip]={list_contact_zip_code}&contact[phone]={list_contact_phone}&contact[country_id]={list_contact_country_id}&contact[email]={list_contact_email}&contact[url]={list_contact_website}&subscribe_confirmation={1_or_0}&send_welcome_email={1_or_0}&unsubscribe_notification={1_or_0}");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'post',
  url: 'https://email.floppysend.com/api/v1/lists?api_token={your_api_token}&name={list_name}&from_email={list_from_email}&from_name={list_from_name}&default_subject={list_default_subject}&contact[company]={list_contact_company}&contact[state]={list-contact_state}&contact[address_1]={list_contact_address_1}&contact[address_2]={list_contact_address_2}&contact[city]={list_contact_city}&contact[zip]={list_contact_zip_code}&contact[phone]={list_contact_phone}&contact[country_id]={list_contact_country_id}&contact[email]={list_contact_email}&contact[url]={list_contact_website}&subscribe_confirmation={1_or_0}&send_welcome_email={1_or_0}&unsubscribe_notification={1_or_0}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```


### All Lists

Get all your lists with one click with FloppyEmail API, Follow the instructions and ingrate our API with your system or application

Request Types
 - GET METHOD
```
https://email.floppysend.com/api/v1/lists
```
```
https://email.floppysend.com/api/v1/lists?api_token={your_api_token}

```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |


#### All Lists API Responses
```JSON
[
    {
        "id": {list_id},
        "uid": "{list_uid}",
        "name": "{list_name}",
        "default_subject": "{list_default_subject}",
        "from_email": "{list_from_email}",
        "from_name": "{list_from_name}",
        "status": null,
        "created_at": "2021-06-23 03:00:06",
        "updated_at": "2021-07-06 03:04:28"
    },
    {
        "id": {list_id},
        "uid": "{list_uid}",
        "name": "{list_name}",
        "default_subject": "{list_default_subject}",
        "from_email": "{list_from_email}",
        "from_name": "{list_from_name}",
        "status": null,
        "created_at": "2021-07-02 06:36:39",
        "updated_at": "2021-07-06 03:04:28"
    }
]
```

#### All Lists API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/lists?api_token={your_api_token}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Cookie: XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/lists?api_token={your_api_token}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Cookie"] = "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D"

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/lists?api_token={your_api_token}")
  .method("GET", null)
  .addHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D")
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/lists?api_token={your_api_token}");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://email.floppysend.com/api/v1/lists?api_token={your_api_token}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```

### Show A Specific List

Grt all specific lists with one click with FloppyEmail API, Follow the instructions and ingrate our API with your system or application

Request Types
 - GET METHOD
```
https://email.floppysend.com/api/v1/lists/{uid}
```
```
https://email.floppysend.com/api/v1/lists/{list_uid}?api_token={your_api_token}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | {uid} | String | Yes | List Id |
  | api_token | String | Yes | Your api token |


#### Show A Specific List API Responses
```JSON
"list": {
        "uid": "{list_uid}",
        "name": "{list_name}",
        "default_subject": "{list_default_subjet}",
        "from_email": "{list_from_email}",
        "from_name": "{list_from_name}",
        "remind_message": null,
        "status": null,
        "created_at": "2021-06-23T03:00:06.000000Z",
        "updated_at": "2021-07-06T03:04:28.000000Z",
        "fields": [
            {
                "key": "EMAIL",
                "label": "Email",
                "type": "string",
                "tag": "EMAIL",
                "default_value": "",
                "visible": "1",
                "required": true,
                "custom_order": "0"
            },
            {
                "key": "FIRST_NAME",
                "label": "First name",
                "type": "string",
                "tag": "FIRST_NAME",
                "default_value": "",
                "visible": "1",
                "required": false,
                "custom_order": "0"
            },
            {
                "key": "LAST_NAME",
                "label": "Last name",
                "type": "string",
                "tag": "LAST_NAME",
                "default_value": "",
                "visible": "1",
                "required": false,
                "custom_order": "0"
            },
            {
                "key": "CUSTOM_FIELD_1",
                "label": "Custom",
                "type": "string",
                "tag": "CUSTOM_FIELD_1",
                "default_value": "test",
                "visible": "0",
                "required": false,
                "custom_order": "0"
            }
        ]
    },
    "contact": {
        "company": "{list_contact_company}",
        "address_1": "{list_contact_address_1}",
        "address_2": "{list_contact_address_2}",
        "country": "{list_contact_country}",
        "state": "{list_contact_state}",
        "zip": "{list_contact_zip_code}",
        "phone": "{list_contact_phone}",
        "url": "{list_contact_website",
        "email": "{list_contact_email}",
        "city": "{list_contact_city}"
    },
    "statistics": {
        "subscriber_count": 1,
        "open_uniq_rate": 0,
        "click_rate": 0,
        "subscribe_rate": 0,
        "unsubscribe_rate": 0,
        "unsubscribe_count": 0,
        "unconfirmed_count": 1
    }
}
```

#### Show A Specific List API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/lists/{list_uid}?api_token={your_api_token}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Cookie: XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/lists/{list_uid}?api_token={your_api_token}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Cookie"] = "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D"

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/lists/{list_uid}?api_token={your_api_token}")
  .method("GET", null)
  .addHeader("Cookie", "XSRF-TOKEN= {auto_generated}; laravel_session={auto_generated}")
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/lists/{list_uid}?api_token={your_api_token}");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://email.floppysend.com/api/v1/lists/{list_uid}?api_token={your_api_token}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```


### All Campaigns

Get all your Campaigns with one click with FloppyEmail API, Follow the instructions and ingrate our API with your system or application

Request Types
 - GET METHOD
```
https://email.floppysend.com/api/v1/campaigns
```
```
https://email.floppysend.com/api/v1/campaigns?api_token={your_api_token}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |


#### All Campaigns API Responses
```JSON
[
    {
        "uid": "{campaign_uid}",
        "name": "{campaign_name}",
        "type": "{campaign_type}",
        "subject": "{campaign_subject}",
        "html": "{campaign_html_template}",
        "plain": "{campaign_plain}",
        "from_email": "{campaign_frm_email}",
        "from_name": "{campaign_from_name}",
        "reply_to": "{email_reply_to}",
        "status": "{campaign_status}",
        "delivery_at": "2021-06-23 03:04:01",
        "created_at": "2021-06-23 03:00:41",
        "updated_at": "2021-07-06 04:49:30"
    },
    {
        "uid": "{campaign_uid}",
        "name": "{campaign_name}",
        "type": "{campaign_type}",
        "subject": "{campaign_subject}",
        "html": "{campaign_html_template}",
        "plain": "{campaign_plain}",
        "from_email": "{campaign_frm_email}",
        "from_name": "{campaign_from_name}",
        "reply_to": "{email_reply_to}",
        "status": "{campaign_status}",
        "delivery_at": "2021-07-02 07:30:01",
        "created_at": "2021-06-29 02:31:04",
        "updated_at": "2021-07-06 04:49:30"
    }
]
```

#### All Campaigns API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/campaigns?api_token=GvwKoUEIVEGCU8DZvC0qi3Q5s',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Cookie: XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/campaigns?api_token={your_api_token}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Cookie"] = "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D"

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/campaigns?api_token={your_api_token}")
  .method("GET", null)
  .addHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D")
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/campaigns?api_token={your_api_token}");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://email.floppysend.com/api/v1/campaigns?api_token={your_api_token}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```


### Show A Specific Campaign

Get a specific Campaign with one click with FloppyEmail API, Follow the instructions and ingrate our API with your system or application

Request Types
 - GET METHOD
```
https://email.floppysend.com/api/v1/campaigns/{uid}
```
```
https://email.floppysend.com/api/v1/campaigns/{uid}?api_token={your_api_token}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |


#### Show A Specific Campaign API Responses
```JSON
{
    "campaign": {
        "uid": "{campaign_uid}",
        "name": "{campaign_name}",
        "list": "{campaign_list}",
        "segment": "{campaign_segment}",
        "default_subject": {campaign_default_subject},
        "from_email": "{campain_from_email}",
        "from_name": "{campaign_from_list}",
        "remind_message": null,
        "status": "{campaign_status}",
        "created_at": "2021-06-23T03:00:41.000000Z",
        "updated_at": "2021-07-06T04:49:30.000000Z"
    },
    "statistics": {
        "subscriber_count": 1,
        "uniq_open_rate": 0,
        "delivered_rate": 0,
        "open_count": 0,
        "uniq_open_count": 0,
        "last_open": "",
        "click_rate": 0,
        "click_per_uniq_open": 0,
        "click_count": 0,
        "abuse_feedback_count": 0,
        "last_click": "",
        "bounce_count": 0,
        "unsubscribe_count": 0,
        "links": [],
        "top_locations": [],
        "top_open_subscribers": []
    }
}
```

#### Show A Specific Campaign API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/campaigns/{campign_uid}?api_token={your_api_token}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Cookie: XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/campaigns/{campign_uid}?api_token={your_api_token}'")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Cookie"] = "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D"

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/campaigns/{campign_uid}?api_token={your_api_token}'")
  .method("GET", null)
  .addHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D")
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/campaigns/{campign_uid}?api_token={your_api_token}'");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://email.floppysend.com/api/v1/campaigns/{campign_uid}?api_token={your_api_token}'',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```

### Custom Feild List

Add a custo field to a specific list with one click with FloppyEmail API, Follow the instructions and ingrate our API with your system or application

Request Types
 - POST METHOD
```
https://email.floppysend.com/api/v1/lists/{uid}/add-field
```
```
https://email.floppysend.com/api/v1/lists/{uid}/add-field?api_token={your_api_token}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |
  | type | String | Yes | text, number, datetime |
  | label | String | Yes | Field label |
  | tag | String | Yes | Field unique tag |
  | default_value | String | Optional | Field default value |


#### Custom Feild List API Responses
```JSON
{
    "status": 1,
    "message": "List's field was created",
    "field": {
        "mail_list_id": "{list_id}",
        "type": "{new_field_type}",
        "label": "{new_field_label}",
        "tag": "{new_field_tag}",
        "default_value": "{new_field_value}",
        "uid": "{uid}",
        "updated_at": "2021-07-06 07:46:29",
        "created_at": "2021-07-06 07:46:29",
        "id": "{new_field_id}"
    }
}
```

#### Custom Feild List API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/lists/{list_uid}/add-field?api_token={your_api_token}&type={field_type}&label={field_label}&tag={field_tag}&default_value={field-value}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_HTTPHEADER => array(
    'Cookie: XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/lists/{list_uid}/add-field?api_token={your_api_token}&type={field_type}&label={field_label}&tag={field_tag}&default_value={field-value}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Post.new(url)
request["Cookie"] = "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D"

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "");
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/lists/{uid}/add-field?api_token={your_api_token}&type={field_type}&label={field_label}&tag={field_tag}&default_value={field-value}")
  .method("POST", body)
  .addHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D")
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/lists/{list_uid}/add-field?api_token={your_api_token}&type={field_type}&label={field_label}&tag={field_tag}&default_value={field-value}");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'post',
  url: 'https://email.floppysend.com/api/v1/lists/{list_uid}/add-field?api_token={your_api_token}&type={field_type}&label={field_label}&tag={field_tag}&default_value={field-value}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```


### Subscribers List

Get all subscribers from a specific list with one click with FloppyEmail API, Follow the instructions and ingrate our API with your system or application

Request Types
 - GET METHOD
```
https://email.floppysend.com/api/v1/subscribers
```
```
https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |
  | list_uid | String | Yes | List uid |
  | open | yes or no | Optional | yes - opened some campaigns, no - not opened any campaign |
  | click | yes or no | Optional | yes - clicked some campaigns, no - not clicked any campaign |


#### Subscribers API Responses
```JSON
{
    "uid": "{uid}",
    "email": "{subscriber_email}",
    "status": "subscribed",
    "FIRST_NAME": "{subsriber_first_name}",
    "LAST_NAME": "{subscriber_last_name}"
}
```

#### Subscribers API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/subscribers?open=yes&click%20%20%20=yes&api_token={your_api_token}&list_uid={list_uid}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Cookie: XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/subscribers?open=yes&click=yes&api_token={your_api_token}&list_uid={list_uid}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Cookie"] = "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D"

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/subscribers?open=yes&click=yes&api_token={your_api_token}&list_uid={list_uid}")
  .method("GET", null)
  .addHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D")
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/subscribers?open=yes&click=yes&api_token={your_api_token}&list_uid={list_uid}");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```

### Add Subscriber

Add a subscriber to a specific list with one click with FloppyEmail API, Follow the instructions and ingrate our API with your system or application

Request Types
 - POST METHOD
```
https://email.floppysend.com/api/v1/subscribers
```
```
https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}&EMAIL={ubscriber_email}&tag={subscriber_tag}&FIRST_NAME={subscriber_first_name}&LAST_NAME={subscriber_last_name}&CUSTOM_FIELD_1={subscriber_ustom-field}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |
  | list_uid | String | Yes | List uid |
  | EMAIL | String | Yes | Subscriber email |
  | tag | String | Optional | Subscriber's tags, seperated by a comma |
  | FIRST_NAME | String | Optional | Subscriber's firt name |
  | LAST_NAME | String | Optional | Subscriber's last name |
  | CUSTOM_FIELD_1 | String | Optional | Subscriber's custom field |


#### Add Subscriber API Responses
```JSON
{
    "status": 1,
    "message": "Confirmation email sent to the subscriber",
    "subscriber_uid": "{subscriber_uid}"
}
```

#### Add Subscriber API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}&tag={subscriber_tag}&FIRST_NAME={subscriber_first_name}&LAST_NAME={subscriber_last_name}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_HTTPHEADER => array(
    'Cookie: XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}&tag={subscriber-tag}&FIRST_NAME={subscriber-first_name}&LAST_NAME={subscriber_last_name}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Post.new(url)
request["Cookie"] = "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D"

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "");
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}&tag={subscriber-tag}&FIRST_NAME={subscriber-first_name}&LAST_NAME={subscriber_last_name}")
  .method("POST", body)
  .addHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D")
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}&tag={subscriber-tag}&FIRST_NAME={subscriber-first_name}&LAST_NAME={subscriber_last_name}");
client.Timeout = -1;
var request = new RestRequest(Method.POST);
request.AddHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'post',
  url: 'https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}&EMAIL={subscriber_email}&{subscriber-tag}&FIRST_NAME={subscriber-first_name}&LAST_NAME={subscriber_last_name}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```

### Specific Subscriber

Get a specific subsriber from a list with one click with FloppyEmail API, Follow the instructions and ingrate our API with your system or application

Request Types
 - GET METHOD
```
https://email.floppysend.com/api/v1/subscribers/{uid}

```
```
https://email.floppysend.com/api/v1/subscribers?list_uid={lidt_if}&id={subscriber_id}&api_token={your_api_token}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |
  | list_uid | String | Yes | List uid |
  | id | String | Yes | Subscriber id |


#### Specific Subscriber API Responses
```JSON
[
    {
        "uid": "{list_uid}",
        "email": "{subsriber_email}",
        "status": "{subscriber_status}",
        "FIRST_NAME": "{subscriber-first_name}",
        "LAST_NAME": "{subscriber_last_name}",
        "CUSTOM_FIELD_1": {subscriber_custom_field}
    }
]
```

#### Specific Subscriber API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
  CURLOPT_HTTPHEADER => array(
    'Cookie: XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D'
  ),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Cookie"] = "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D"

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}")
  .method("GET", null)
  .addHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D")
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Cookie", "XSRF-TOKEN={auto_generated}%3D%3D; laravel_session={auto_generated}%3D");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://email.floppysend.com/api/v1/subscribers?list_uid={list_uid}&api_token={your_api_token}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```


### Update Subscriber

Update a specific subsriber information from a list with one click with FloppyEmail API,
Follow the instructions and ingrate our API with your system or application

Request Types
 - PATCH METHOD
```
https://email.floppysend.com/api/v1/subscribers/{uid}
```
```
https://email.floppysend.com/api/v1/subscribers/{subscriber_uid}?api_token={your-api-token}&EMAIL={subscriber_email}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |
  | subscriber_uid | String | Yes | Subscriber uid |
  | EMAIL | String | Yes | Subscriber email |


#### Update Subscriber API Responses
```JSON
{
    "status": 1,
    "message": "Subscriber was successfully updated",
    "subscriber_uid": "{subscriber_uid}"
}
```

#### Update Subscriber API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/subscribers/{subscriber_uid}?api_token={your_api_token}&EMAIL={subscriber_new_email}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'PATCH',
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/subscribers/{subscriber_uid}?api_token={your_api_token}&EMAIL={subscriber_new_email}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Patch.new(url)

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "");
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/subscribers/{subscriber_uid}?api_token={your_api_token}&EMAIL={subscriber_new_email}")
  .method("PATCH", body)
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/subscribers/{subscriber_uid}?api_token={your_api_token}&EMAIL={subscriber_new_email}");
client.Timeout = -1;
var request = new RestRequest(Method.PATCH);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'patch',
  url: 'https://email.floppysend.com/api/v1/subscribers/{subscriber_uid}?api_token={your_api_token}&EMAIL={subscriber_new_email}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```

### Subscriber Per Email

Update a specific subsriber information from a list with one click with FloppyEmail API,
Follow the instructions and ingrate our API with your system or application

Request Types
 - GET METHOD
```
https://email.floppysend.com/api/v1/subscribers/email/{email}
```
```
https://email.floppysend.com/api/v1/subscribers/email/{subsriber_email}?api_token={your_api_token}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |
  | subscriber_email | String | Yes | Subscriber email |


#### Subscriber Per Email API Responses
```JSON
{
    "subscribers": [
        {
            "uid": "{subscriber-uid}",
            "list_uid": "{list_uid}",
            "email": "{subscriber_email}",
            "status": "{subscriber_status}",
            "source": {subscriber_source},
            "ip_address": "{subscriber_ap_address}",
            "FIRST_NAME": "{subscriber_first_name}",
            "LAST_NAME": "{subscriber_last_name}"
        }
    ]
}
```

#### Subscriber Per Email API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/subscribers/email/{subscriber_email}?api_token={your-api_token}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'GET',
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/subscribers/email/{subscriber_email}?api_token={your-api_token}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Get.new(url)

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/subscribers/email/{subscriber_email}?api_token={your-api_token}")
  .method("GET", null)
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/subscribers/email/{subscriber_email}?api_token={your-api_token}");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'get',
  url: 'https://email.floppysend.com/api/v1/subscribers/email/{subscriber_email}?api_token={your-api_token}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```

### Subscribe A Subscriber

Subsriber a subsriber to a list with one click with FloppyEmail API,
Follow the instructions and ingrate our API with your system or application

Request Types
 - PATCH METHOD
```
https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{uid}/subscribe
```
```
https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/subscribe?api_token={your_api_token}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |
  | subscriber_uid | String | Yes | Subscriber uid |
  | list_uid | String | Yes | List uid |

#### Subscribe A Subscriber API Responses
```JSON
{
    "status": 1,
    "message": "Subscribed"
}
```

#### Subscribe A Subscriber API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/subscribe?api_token={your_api_token}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'PATCH',
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/subscribe?api_token={your_api_token}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Patch.new(url)

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "");
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/subscribe?api_token={your_api_token}")
  .method("PATCH", body)
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/subscribe?api_token={your_api_token}");
client.Timeout = -1;
var request = new RestRequest(Method.PATCH);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'patch',
  url: 'https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/subscribe?api_token={your_api_token}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```

### Unsubscribe A Subscriber

Unsubsriber a subsriber from a list with one click with FloppyEmail API,
Follow the instructions and ingrate our API with your system or application

Request Types
 - PATCH METHOD
```
https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{uid}/unsubscribe
```
```
https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/unsubscribe?api_token={your_api_token}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |
  | subscriber_uid | String | Yes | Subscriber uid |
  | list_uid | String | Yes | List uid |

#### Unsubscribe A Subscriber API Responses
```JSON
{
    "status": 1,
    "message": "Unsubscribed"
}
```

#### Unsubscribe A Subscriber API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/unsubscribe?api_token={your_api_token}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'PATCH',
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/unsubscribe?api_token={your_api_token}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Patch.new(url)

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "");
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/unsubscribe?api_token={your_api_token}")
  .method("PATCH", body)
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/unsubscribe?api_token={your_api_token}");
client.Timeout = -1;
var request = new RestRequest(Method.PATCH);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'patch',
  url: 'https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/unsubscribe?api_token={your_api_token}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```

### Delete A Subscriber

Delete a subsriber from a list with one click with FloppyEmail API,
Follow the instructions and ingrate our API with your system or application

Request Types
 - DELETE METHOD
```
https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{uid}/delete
```
```
https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/delete?api_token={your_api_token}
```

#### Parameters
  | Parameter | Type | Required | Description |
  | --------- | ---- | -------- | ----------- |
  | api_token | String | Yes | Your api token |
  | subscriber_uid | String | Yes | Subscriber uid |
  | list_uid | String | Yes | List uid |

#### Delete A Subscriber API Responses
```JSON
{
    "status": 1,
    "message": "Deleted"
}
```

#### Delete A Subscriber API Code Sample

If api_token was missing you will be redirect to login page

```PHP
//PHP

<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/delete?api_token={your_api_token}',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'DELETE',
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;
```

```ruby
//Ruby

require "uri"
require "net/http"

url = URI("https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/delete?api_token={your_api_token}")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Delete.new(url)

response = https.request(request)
puts response.read_body
```

```Java
//JAVA

//The OkHttpClient is an external package, you need to install it before making the request, 
//And don't forget to add user permission for the internet inside "\MyApplication\app\src\main\AndroidManifest.xml"
//Also, you need to add required dependencies inside "MyApplication\app\build.gradle"

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "");
Request request = new Request.Builder()
  .url("https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/delete?api_token={your_api_token}")
  .method("DELETE", body)
  .build();
Response response = client.newCall(request).execute();
```

```C#
//C#

var client = new RestClient("https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/delete?api_token={your_api_token}");
client.Timeout = -1;
var request = new RestRequest(Method.DELETE);
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

```JavaScript
//NodeJs
//Make sure to import Axios and install npm packages before doing the request

var axios = require('axios');

var config = {
  method: 'delete',
  url: 'https://email.floppysend.com/api/v1/lists/{list_uid}/subscribers/{subscriber_uid}/delete?api_token={your_api_token}',
  headers: { }
};

axios(config)
    .then(function (response) {
      console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
      console.log(error);
    });
```
