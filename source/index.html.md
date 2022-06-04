---
title: API Reference

toc_footers:

- <a href='#'>Sign Up for a Developer Key</a>
- <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:

- errors

search: true

code_clipboard: true

meta:

- name: description content: Documentation for the EnayaPay API

---

# Introduction

Welcome to the EnayaPay API! You can use our API to access EnayaPay API endpoints.

# Public

## services

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/services/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd"
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/services/`

### Description

`the use of this endpoint to get all services limtations per transactions .`

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | [{"id": 4,"name": "Zain Topup","local_limate": 1000,"international_limate": 2500,"enable": true},{"id": 5,"name": "Zain Bill",
"local_limate": 5000,"international_limate": 10000,"enable": true}] | all services

## sudan banaks

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.0/sudan/banks/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd"
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.0/sudan/banks/`

### Description

`the use of this endpoint to get all sudan banaks .`

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | [{"id": 1,"bank_name_en": "Abu Dhabi Islamic Bank","bank_name_ar": "مصرف ابوظبي الاسلامي","bank_code": "581858","bank_image": "Abu_dabi.png"},{"id": 2,"bank_name_en": "Agricultural Bank of Sudan","bank_name_ar": "البنك الزراعي السوداني",
"bank_code": "639255","bank_image": "alzera3y.png"    },] | all sudan banaks

## rate

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/rate/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd"
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/rate/`

### Description

`the use of this endpoint to get rate Doller .`

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | {"rate": 452} | rate done

# User Account Management

## Register

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/register/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd"
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/register/`

### Description

`the use of this endpoint to register new user using phone number as id verification .`

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg"
}

```

### Body

```json
 {
  "user_phone": "2499++++++++",
  "user_name": "doctor",
  "device_id":"dafsafsafdsagdsgdssdgdsdsgdsgdsgsdgdsg"
  "user_password": "calicofdhfdsfsd"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
user_phone | required | user phone number | String
user_name | required | userName of user | String
user_password | required | user password | String
device_id | required | device id for notifications | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | None | user created and otp will send in phone number
302 | None | user already registered
406 | `` {"response_code": 2,"reponse_message" : "your number not valid"} ``| phone number of user not valid
400 | `` { "details": {"user_password": [ "This field is required."]} } `` | Bad request occurred when forget parameter
502 | ```{"details" : "bad getway" }``` |  bad getway of sms getway
503 | ``` {"details" :"service not available"} ``` | when service not available



## update profile 

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/customer/profile/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd"
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key.

### HTTP Request

`PUT https://sandbox.enayapay.com/api/v2.1/customer/profile/`

### Description

`the use of this endpoint to update users.`

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg"
}

```

### Body

```json
 {
  "user_name": "doctor",
  "user_email": "bakheet@enay.com"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
user_name | required | userName of user | String
user_password | required | user password | String
user_email  | required | user email | Email

### Response

StatusCode | Response Data                         | Description
--------- |---------------------------------------| ---------
200 | ``{"user_name": "beko safy","user_email": "bakheet@enayatech.com"` | profile updated successfully
400 | `` { "details": {"user_email": [ "This field is required."]} } `` | Bad request occurred when forget parameter
401 | ``{"details": "your api key not valid"}`` | api key not valid
503 | ``` {"details" :"service not available"} ``` | when service not available


## verify

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/verify/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd"
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/verify/`

### Description

``the use of this endpoint to verification user phone number that he used``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg"
}

```

### Body

```json
 {
  "user_phone": "2499++++++++",
  "user_otp": "454345"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
user_phone | required | user phone number | String
user_otp | required | otp of user | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ``` {"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6IjU3NTMwNyIsImV4cGlyeSI6IjIwMjEtMTEtMTMifQ.2uU8eOnw8biYxH55EblrTHOz5nM4rcP1kiIa7S46mFs","user_name": "doctor"} ```| user verified
203 | None | wrong otp
400 | ``{ "details": {"user_otp": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | ``` {"details": "user not registered"} ``` | user not register
503 | ``` {"details" :"service not available"} ``` | when service not available

## login

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/login/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd"
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/login/`

### Description

`` this endpoint use to access user account using password``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg"
}

```

### Body

```json
 {
  "user_phone": "2499++++++++",
  "user_password": "dfdfsdfdsfs"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
user_phone | required | user phone number | String
user_password | required | password of user | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ``` {"user_name": "doctor","status": "active"} ```| user authorized
203 | None | wrong password
400 | ``{ "details": {"user_password": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | ``` {"details": "user not registered"} ``` | user not register
503 | ``` {"details" :"service not available"} ``` | when service not available

## rest password

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/rest/password/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/rest/password/`

### Description

`` this endpoint use to rest user password when he forget``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworioweir"
}

```

### Body

```json
 {
  "user_phone": "2499++++++++",
  "user_password": "dfdfsdfdsfs"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
user_phone | required | user phone number | String
user_password | required | password of user | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ``` {"user_name": "doctor","status": "active"} ```| user rest his password successful
203 | None | not valid token
400 | ``{ "details": {"user_password": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | ``` {"details": "user not registered"} ``` | user not register
503 | ``` {"details" :"service not available"} ``` | when service not available

## change password

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/change/password/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/change/password/`

### Description

``this endpoint use to change user password that he used to access apllication .``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "current_password": "gfgfdgdfg",
  "new_password": "dfdfsdfdsfs"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
current_password | required | old password that user need to change | String
new_password | required | new_password that user need to change to it | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"details": "password updated successful"} ```| user changed his password successfully
203 | ``{"details": "wrong current password"}``| invalid old password
400 | ``{ "details": {"new_password": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | ``` {"details": "user not registered"} ``` | user not register
503 | ``` {"details" :"service not available"} ``` | when service not available

## pan check

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/pan/4242424242424242/check/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/pan/4242424242424242/check/`

### Description

``this endpoint use to get pan informations.``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg"
}

```

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"scheme": "visa","type": "credit","brand": "Traditional","prepaid": false,"length":16}```| user changed his password successfully
503 | ``` {"details" :"service not available"} ``` | when service not available

# Virtual Card

## register virtual card

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/virtual/register/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/virtual/register/`

### Description

``this endpoint use to create new virtual card using phone number``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "phone_no": "0905450784"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
phone_no | required | number used to register virtual card| String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"phone_no": "0905450785","response_status": "Successful","response_message": "Approved","response_code": 0}```| card added successfully
400 | ``{ "details": {"phone_no": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | ``{"details": " user not registered"}`` | user not register
406 | ```{"phone": "090545078","response_status": "Failed","response_message": "Wrong Phone Number","response_code": 56}``` |
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

## change ipin 

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/change/ipin/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/change/ipin/`

### Description

``this endpoint use to change ipin of Customers Cards``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
 "pan":"4242424242424242",
 "ipin":"fdfdfdgdsgdsgndsgdsngndsgdsgmgnmdsnmgdsgdsngnmds",
 "new_ipin":"fdfdfdgdsgdsgndsgdsngndsgdsgmgnmdsnmgdsgdsngnmds",
 "expiration_date":"0424",
 "uuid":"dsfsfsdfdskfdskfkskfskflksfslkfslksfsfslk"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | card number customer need to change ipin of it| String
ipin | required | old ipin of card| String
new_ipin | required | new ipin of card| String
expiration_date | required | expiry date of card| String
uuid | required | uuid that use used in encription| String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```"pan": "4242442424242424","response_code": 0,"response_message":"Approved","response_status": "Successful,"uuid": "sfdgdsgsdgsgsgsdgsgsg","date_time": "3432432432532532532523"```| ipin changed successfully
400 | ``{ "details": {"pan": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | ``{"details": " user not registered"}`` | user not register
406 | ```{"response_message": "Wrong pan","response_code": 50}``` |
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user



<<<<<<< HEAD

# Favorites

## add new favorites

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/favorites/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/favorites/`

### Description

``this endpoint allow to customers to add favorites phone numbers and meters``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "key": "PHONE_NO",
  "value": "0905450785",
  "label": "my number"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
key | required | type of favorites | String
value | required | value customers needs to add| String
label | required | name of favorites

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"key": "PHONE_NO","value": "0905450789","label": "my number"}```|
400 | ``{ "details": {"label": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token not valid"}``` | your token or api key not valid
302 | ```{"details":"your favorite already assgined"}``` |
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

## get favorites

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/favorites/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds , key: PHONE_NO"
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`GET https://sandbox.enayapay.com/api/v2.1/favorites/`

### Description

``this endpoint allow to customers to get favorites base on key``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe",
  "key": "PHONE_NO"
}

```

### Body

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```[{"id": 2,"user_id": 1,"key": "PHONE_NO","value": "0905450789","label": "my number"},{"id": 1,"user_id": 1,"key": "PHONE_NO","value": "0905450785","label": "my number"}]```|
400 | ``{ "details": "forget key" }``| Bad request occurred when forget parameter
401 | ```{"details": "your token not valid"}``` | your token or api key not valid
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

## update favorite

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/favorite/1/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`PUT https://sandbox.enayapay.com/api/v2.1/favorite/1/`

### Description

``this endpoint allow to customers to update favorite phone numbers or meters``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "key": "PHONE_NO",
  "value": "0905450785",
  "label": "my number"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
key | required | type of favorites | String
value | required | value customers needs to add| String
label | required | name of favorites

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"key": "PHONE_NO","value": "0905450789","label": "my number"}```|
400 | ``{ "details": {"label": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token not valid"}``` | your token or api key not valid
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

## get favorite

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/favorite/1/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`GET https://sandbox.enayapay.com/api/v2.1/favorite/1/`

### Description

``this endpoint allow to customers to GET  favorite by id``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"key": "PHONE_NO","value": "0905450789","label": "my number"}```|
401 | ```{"details": "your token not valid"}``` | your token or api key not valid
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

## delete favorite

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/favorite/1/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`DELETE https://sandbox.enayapay.com/api/v2.1/favorite/1/`

### Description

``this endpoint allow to customers to DELETE  favorite by id``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
204 | None| Favorite deleted successfuly
401 | ```{"details": "your token not valid"}``` | your token or api key not valid
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

=======
> > > > > > > 55db536512ec3cf82e8c7c0398b49791c56014d7



# Entertainment 

## all gift cards and entertainment

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.0.1/gift/cards/" \
<<<<<<< HEAD
  -H "x-api-key: gffdgdfgdfgdfgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdgd` with your API key and Token.
=======
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.
>>>>>>> dcf239121400a4f7477742d115f60f8425791005

### HTTP Request

`GET https://sandbox.enayapay.com/api/v2.0.1/gift/cards/`

### Description

<<<<<<< HEAD
``this endpoint allow to customers to GET all gift cards and entertainments``
=======
``this endpoint allow to customers to GET  get  all gift cards and entertainments``
>>>>>>> dcf239121400a4f7477742d115f60f8425791005

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```[{"id": 1,"name": "google card","amount_sdg": 333.0,"amount_usd": 45.0,"type": "gift card","logo": "logo.png"}]```| get all 
401 | ```{"details": "your token not valid"}``` | your token or api key not valid
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

## Pay Gift Card
```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.0.1/gift/cards/2/pay/" \
<<<<<<< HEAD
  -H "x-api-key: gffdgdfgdfgdf , token: ffdfdsfsdfds "
=======
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
>>>>>>> dcf239121400a4f7477742d115f60f8425791005
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/api/v2.0.1/gift/cards/2/pay/`

### Description

``this endpoint use to pay for gift card or entertainment``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "pan": "45456789456798893",
  "ipin": "rtewrrtertretretrtrwtwrt",
  "uuid": "fdfregregergerlkfjerfklerjfkgerjgjre",
  "expiry_date": "0824"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want pay by it | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
uuid | required | string

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"pan": "4343543645645745745","expiry_date": "0222,"amount_sdg": 45,"amount_usd":5,"code": 342342342,"response_code": 0,"response_message": "Successful}```| account user informations
400 | ``{ "details": {"pan": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
422 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ```{"details": "service unvailable"}``` | when service provider down

# Notifiactions 

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/notifications/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`GET https://sandbox.enayapay.com/api/v2.1/notifications/`

### Description

``this endpoint allow to customers to GET  get  notifications``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```[{"id": 1,"notify_user_id": 109,"title_en": "gift card","body_en": "new service available","title_ar": "gift card","body_ar": "new service available","timestamp": "2021-08-22T10:12:29.122025Z"}]```| get all messages
401 | ```{"details": "your token not valid"}``` | your token or api key not valid
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

# Virtual Card

## register virtual card

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/virtual/register/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/virtual/register/`

### Description

``this endpoint use to create new virtual card using phone number``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "phone_no": "0905450784"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
phone_no | required | number used to register virtual card| String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"phone": "0905450785","response_status": "Successful","response_message": "Approved","response_code": 0, "uuid":"1027e40c-9a49-4212-b896-dcfda7afae70"}```|
400 | ``{ "details": {"phone_no": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | ``{"details": " user not registered"}`` | user not register
406 | ```{"phone": "090545078","response_status": "Failed","response_message": "Wrong Phone Number","response_code": 56}``` |
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

## virtual card verification

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/virtual/verify/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/virtual/verify/`

### Description

``this endpoint use to verify registeration of virtual card``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
 "otp":"8834",
 "label":"bakheet",
 "uuid":"ec5d39b4-ed67-4f90-b60c-d472322ba078",
 "original_tran_uuid":"b8ebf7d4-c33b-4e92-9195-5d83d59fbdac",
 "phone_no":"0905450785",
 "ipin":"ttttttttttttttttttttttttttttttttttttttttt",
 "password":"B4_e"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
phone_no | required | number used to register virtual card| String
otp | required | verification code that sent to customer
ipin | required | ipin of virtual card
label | required | card label | String
uuid | required | should be used in encryption | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"phone_no": "0905450785","pan": "3234324324324434","expiration_date": "0422","response_status": "Successful","response_message": "Approved","response_code": 0}```| card created successfully
400 | ``{ "details": {"phone_no": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | ``{"details": " user not registered"}`` | user not register
406 | ```{"phone_no": "090545078","pan": 0,"expiration_date": "","response_status": "Failed","response_message": "Phone Number Already Assigned To Account","response_code": 50}``` |
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

# Cards

## add card

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/cards/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/cards/`

### Description

``this endpoint use to add new card to your account``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "pan": "454567894567988",
  "label": "bakheet",
  "expiration_date": "0824",
  "default": 1
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to add | String
label | required | display name of card | String
expiration_date | required | expiration  date of card| String
default | required | to set card as default in use| string

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"id" :1}```| card added successfully
400 | ``{ "details": {"pan": ["This field is required."]} }``| Bad request occurred when forget parameter
302 | None | card already added
401 | None | your api key not valid
404 | ``{"details": " user not registered"}`` | user not register
406 | ```{"response_code": 5, "response_message": "unknown card number"}``` | user card number not valid
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user


## update card

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/card/1/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`PUT https://sandbox.enayapay.com/api/v2.1/card/1/`

### Description

``this endpoint use to update users cards.``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "pan": "454567894567988",
  "label": "bakheet",
  "expiration_date": "0824",
  "default": 1
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to add | String
label | required | display name of card | String
expiration_date | required | expiration  date of card| String
default | required | to set card as default in use| string

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"pan": "54645645645645645745","expiration_date": "0422","label": "bakheet alsafy","default": 1}```| card updated
401 | None | your api key not valid
404 | ``{"details": " user not registered"}`` | user not register
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

## get cards

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/cards/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`GET https://sandbox.enayapay.com/api/v2.1/cards/`

### Description

``this endpoint use views all cards that user assgin to his account``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```[{"id": 1,"card_pan": "454567894567988","card_expiry": "0824","card_label": "bakheet","card_type": "International","card_image": "Screenshot_from_2021-07-08_14-33-58.png","default": 1}]```| all cards that user assign to his account
401 | None | your api key not valid
404 | ``{"details": " user not registered"}`` | user not register
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

## get card

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/card/1/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`GET https://sandbox.enayapay.com/api/v2.1/card/1/`

### Description

``this endpoint use view one card  base on card id that user assgin to his account``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```[{"id": 1,"card_pan": "454567894567988","card_expiry": "0824","card_label": "bakheet","card_type": "International","card_image": "Screenshot_from_2021-07-08_14-33-58.png","default": 1}]```|  view one card that user assign to his account
401 | None | your api key not valid
404 | ``{"details": " user not registered"}`` | user not register
503 | ``` {"details" :"service unvailable for now"} ``` | service disable for user

## delete card

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/card/1/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`DELETE https://sandbox.enayapay.com/api/v2.1/card/1/`

### Description

``this endpoint use remove card  base on card id that user assgin to his account``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
204 | ```{"details":"card has been deleted successfully"}```|  view one card that user assign to his account
401 | None | your api key not valid
404 | ``{"details": " user not registered"}`` | user not register

## balance inquiry

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/balance/inquiry/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/balance/inquiry/`

### Description

``this endpoint use to provide information on the customer account balance``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "pan": "45456789456798893",
  "ipin": "rtewrrtertretretrtrwtwrt",
  "uuid": "fdfregregergerlkfjerfklerjfkgerjgjre",
  "expiration_date": "0824"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to known its balance | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
uuid | required | string

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"response_code": 0,"balance": 400,"response_status": "Successful","uuid": "fdfregregergerlkfjerfklerjfkgerjgjre"}```| account user informations
400 | ``{ "details": {"pan": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
502 | ``` {"details" :"bad getway"} ``` | when service provider down

# Telecoms

## Local

### Topup

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/telecom/110010001/topup/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/telecom/110010001/topup/`

### Description

``this endpoint use to provide topup to customer base on payeeid ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "pan": "43443455656653465",
  "ipin": "reretertrterty5rt45",
  "expiration_date": "0824",
  "phone_no": "0905450785",
  "amount": 300,
  "uuid": "rerrwerwerwerwerwerwrweRWrwrwr",
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to py topup by it | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
amount | required | amount of topup that customer need to pay | Float
phone_no | required | phone number want to charge it | String
uuid | required | the key used to encrypt ipin| string
platform | required | platform that customer used to charge phone number | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"pan": "43443455656653465","acq_tran_fee": 0,"dynamic_fees": 0,"issuer_tran_fee": 0,"payment_info": "MPHONE= 2490905450785","response_message": "Approved","response_status": "Successful","amount": 300,tran_date_time": 55665455444,"uuid": "rerrwerwerwerwerwerwrweRWrwrwr","response_code": 0}```| Transaction done successfully
400 | ``{ "details": {"pan": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | | customer not registered
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

### Inquiry

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/telecom/1100055511/inquiry/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/telecom/1100055511/inquiry/`

### Description

``this endpoint use to provide information of cutomer account invoice ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "phone_no": "0905450785"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------

phone_no | required | phone number that customer want to known invoice for it | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"total_amount": 400,"contract_number": 34234235345,"acq_tran_fee": 0,"dynamic_fees": 0,"issuer_tran_fee": 0,"tran_date_time": 65475475}```| Transaction done successfully
400 | ``{ "details": {"phone_no": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | | customer not registered
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

### Bill Payment

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/telecom/110010001/topup/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/telecom/110010001/topup/`

### Description

``this endpoint use by customers bill they invoices ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "pan": "43443455656653465",
  "ipin": "reretertrterty5rt45",
  "expiration_date": "0824",
  "phone_no": "0905450785",
  "amount": 300,
  "uuid": "rerrwerwerwerwerwerwrweRWrwrwr",
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to py topup by it | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
amount | required | amount of topup that customer need to pay | Float
phone_no | required | phone number want to charge it | String
uuid | required | the key used to encrypt ipin| string
platform | required | platform that customer used to charge phone number | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"pan": "43443455656653465","acq_tran_fee": 0,"dynamic_fees": 0,"issuer_tran_fee": 0,"payment_info": "MPHONE= 2490905450785","response_message": "Approved","response_status": "Successful","amount": 300,tran_date_time": 55665455444,"uuid": "rerrwerwerwerwerwerwrweRWrwrwr","response_code": 0}```| Transaction done successfully
400 | ``{ "details": {"pan": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | | customer not registered
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Telecoms Create Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/paypal/telecom/110011001/topup/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/paypal/telecom/110011001/topup/`

### Description

``this endpoint use to create order to pay topup to customer base on payeeid with paypal``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "phone_no": "0905450785",
  "amount": 300,
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
amount | required | amount of topup that customer need to pay | Float
phone_no | required | phone number want to charge it | String
platform | required | platform that customer used to charge phone number | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"approval_url": "https://www.paypal.com/checkoutnow?token=45R87131522395454","order_id": "45R87131522395454"}```| order created  successfully
400 | ``{ "details": {"amount": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
402 | ```{"details": "your amount less than 1$"}``` | your amount less than 1$
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Telecoms approve Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/telecom/approve/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/telecom/approve/`

### Description

``this endpoint use to provide topup to customer base on payeeid with paypal``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "approve_order_id": "45R87131522395454"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
45R87131522395454 | required | order that used in payment process in paypal | String

### response Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
acq_tran_fee | 0.0 | static fee | Float
dynamic_fee | 0.0 | dynamic fee | Float
issuer_tran_fee | 0.0 | issuer transaction fee | Float
response_message | depend on response code |message of transaction | String
response_status | Successful / Failed | status of transaction | String
amount_sdg | 0.0 | amount of transaction in sdg | Float
amount_usd | 0.0 | amount of transaction in usd | Float
tran_date_time | 124244 | date time of transaction | String
response_code | 0 | code of transaction | Integer

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"acq_tran_fee": 0.0,"dynamic_fees": 0.0,"issuer_tran_fee": 0.0,"payment_info": "MPHONE=0905450785","response_message": "Approved","response_status": response_status,"amount_sdg": 300,"amount_usd": 1.5,"service_type": Zain Topup,"tran_date_time": 344234324,"uuid": "asdadafafsaf334eadasdsadadasdq3","response_code": 0}```| transaction done  successfully
400 | ``{ "details": {"approve_order_id": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
422 | ```{"details": "your order id not valid"}```|  user used not valid order
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

# Electricity

## Electricity Local

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/electricity/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/electricity/`

### Description

``this endpoint use by customers to charge they meters ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "pan": "43443455656653465",
  "ipin": "reretertrterty5rt45",
  "expiration_date": "0824",
  "meter_no": "0905450785",
  "amount": 300,
  "uuid": "rerrwerwerwerwerwerwrweRWrwrwr",
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to charge | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
amount | required | amount of topup that customer need to pay | Float
meter_no | required | meter number want to charge it | String
uuid | required | the key used to encrypt ipin| string
platform | required | platform that customer used to charge meter number | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"acq_tran_fee": 0,"dynamic_fees": 0,"issuer_tran_fee": 0,"pan": "43443455656653465","payment_info": "METER=024354364645","response_message": "Approved","response_status": "Successful", "amount": 300, "tranDateTime": 3343432432432, "uuid": "rerrwerwerwerwerwerwrweRWrwrwr", "response_code": 0, "account_no": 3423432423, "customer_name": "bakheet", "meter_fees": 1,"meter_number": "024354364645", "net_amount": 0, "operator_message": "Credit Purchase", "token": "47310897576729505616","units_in_kwh": 34, "water_fees": 1}```| Transaction done successfully
400 | ``{ "details": {"pan": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | | customer not registered
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Electricity Create Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/paypal/electricity/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST  https://sandbox.enayapay.com/api/v2.1/paypal/electricity/`

### Description

``this endpoint use to create order to pay Electricity with paypal``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "meter_no": "0905450785",
  "amount": 300,
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
amount | required | amount of topup that customer need to pay | Float
meter_no | required | meter number want to charge it | String
platform | required | platform that customer used to charge meter number | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"approval_url": "https://www.paypal.com/checkoutnow?token=45R87131522395454","order_id": "45R87131522395454"}```| order created  successfully
400 | ``{ "details": {"amount": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
402 | ```{"details": "your amount less than 1$"}``` | your amount less than 1$
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Electricity approve Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/electricity/approve/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/electricity/approve/`

### Description

``this endpoint use to approve order that customer created``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "approve_order_id": "45R87131522395454"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
45R87131522395454 | required | order that used in payment process in paypal | String

### response Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
acq_tran_fee | 0.0 | static fee | Float
dynamic_fee | 0.0 | dynamic fee | Float
issuer_tran_fee | 0.0 | issuer transaction fee | Float
response_message | depend on response code |message of transaction | String
response_status | Successful / Failed | status of transaction | String
amount_sdg | 0.0 | amount of transaction in sdg | Float
amount_usd | 0.0 | amount of transaction in usd | Float
tran_date_time | 124244 | date time of transaction | String
response_code | 0 | code of transaction | Integer

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{ "acq_tran_fee": 0.0,"dynamic_fees": 0.0,"issuer_tran_fee": 0.0,"payment_info": "METER_NO= 2342342343","response_message": "Approved","response_status": "Successful","amount_sdg": 500,"amount_usd": 1,tran_date_time": 43434324324234,"uuid": "fdfsdfsdfsdsaedeseadasdasdas","response_code": 0,"account_no": 34433,"customer_name": "bakheet","meter_fees": 0.0,"meter_number": 2342342343,"net_amount": 4.0,"operator_message": "pay","token": "45345345353453532532532","units_in_kwh": 45.0,"water_fees": 0.0}```| transaction done  successfully
400 | ``{ "details": {"approve_order_id": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
422 | ```{"details": "your order id not valid"}```|  user used not valid order
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

# Government

## government Inquiry

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/government/inquiry/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/government/inquiry/`

### Description

``this endpoint use by customers to inquiry for invoice ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "invoice_number": 435345345888,
  "phone_number": "0905450785"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
invoice_number | required | number of custom invoice | String
phone_number | required | phone number of payer | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ``{"reference_id": 342434325,"unit_name": "government","service_name": "e-15","payer_name": "bakheet","total_amount": 50000,"due_amount": 200,"response_code": 0,"response_message": "Approved","response_status": "Successful"}``| Transaction done successfully
400 | ``{ "details": {"phone_number": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details":"you api key not valid"}``` | your api key not valid
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## government payment

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/government/pay/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/government/pay/`

### Description

``this endpoint use by customers to pay invoice ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
{
  "amount": 500,
  "pan": 43454534217689456,
  "ipin": "etretewtwetewgtrwqgtrwgtfqgsrewgsfgsgdsgdsgdsgdsgds",
  "expiration_date": "0423",
  "uuid": "sfdsdfdsgsddsgdsgdsgdssdgdsg",
  "serviced": "sudan",
  "invoice_number": 435345345888,
  "phone_number": "0905450785",
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to charge | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
invoice_number | required | number of custom invoice | String
phone_number | required | phone number of payer | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ``{"pan": "43454534217689456","acq_tran_fee": 0,"dynamic_fees": 0,"issuer_tran_fee": 0,"serviced": 6,"invoice_number": "435345345888","phone_number": "0905450785","response_message": "Approved","response_status": "Successful","amount": 500,"tran_date_time": 4545325235325,"uuid": "sfdsdfdsgsddsgdsgdsgdssdgdsg","response_code": 0}``| Transaction done successfully
400 | ``{ "details": {"phone_number": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details":"you api key not valid"}``` | your api key not valid
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Governments Create Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/paypal/government/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/paypal/government/`

### Description

``this endpoint use to create order to pay invoice  by using  paypal``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
      {
  "invoice_number": 33253453532,
  "phone_number": "0905450785",
  "amount": 5000,
  "platform": "web"
}
```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
amount | required | amount of topup that customer need to pay | Float
invoice_number | required | number of custom invoice | String
phone_number | required | phone number of payer | String
platform | required | platform that customer used to charge phone number | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"approval_url": "https://www.paypal.com/checkoutnow?token=45R87131522395454","order_id": "45R87131522395454"}```| order created  successfully
400 | ``{ "details": {"amount": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
402 | ```{"details": "your amount less than 1$"}``` | your amount less than 1$
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Governments approve Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/government/approve/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/government/approve/`

### Description

``this endpoint use to approve order that client created.``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "approve_order_id": "45R87131522395454",
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
approve_order_id | required | order that used in payment process in paypal | String
platform  | required | client type | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"serviced": 6,"invoice_number": "33253453532","phone_number": "0905450785","response_message": "Approved","response_status": "Successful","amount": "459.0","tran_date_time": 4545325235325,"uuid": "da13ee84-a4fa-47af-8b3b-1c8bafede961","response_code": 0}```| transaction done  successfully
400 | ``{ "details": {"approve_order_id": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
422 | ```{"details": "your order id not valid"}```|  user used not valid order
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

# Education

## Admission

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/admissions/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`GET https://sandbox.enayapay.com/api/v2.1/admissions/`

### Description

``this endpoint use to get all available  admissions for students  ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ``[{"id": 1,"admission_kind_en": "General admission-first round","admission_kind_ar": "القبول الدور الأول – قبول عام","fees": "9000"},{"id": 2,"admission_kind_en": "Special admission","admission_kind_ar": "القبول الخاص","fees": "200"}]``| request done successfully
401 | ```{"details":"you api key not valid"}``` | your api key not valid
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Courses

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/courses/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`GET https://sandbox.enayapay.com/api/v2.1/courses/`

### Description

``this endpoint use to get all available  courses for students  ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ``[{"id": 1,"description_en": "Academic","description_ar": "اكاديمي"},{"id": 2,"description_en": "Agricultural","description_ar": "زراعي"}]``| request done successfully
401 | ```{"details":"you api key not valid"}``` | your api key not valid
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Education Inquiry

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/education/inquiry/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/education/inquiry/`

### Description

``this endpoint use by customers to inquiry for invoice ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json

{
  "set_number": 6546436436436436,
  "stud_course_id": 4,
  "stud_from_kind": "4543543576676767676"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
set_number | required | number of student seat | String
stud_course_id | required | id of course | String
stud_from_kind | required | kind from

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | `` "form_no": 324324234,"receipt_no": 34423432423,"english_name": "bakheet","arabic_name": "bakheet","due_amount": 10000,"response_status": "Successful","response_code": 0,"response_message": "Approved"``| Transaction done successfully
400 | ``{ "details": {"set_number": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details":"you api key not valid"}``` | your api key not valid
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Education Payment

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/education/pay/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/education/pay/`

### Description

``this endpoint use by customers to pay  invoice ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json

{
  "amount": 500,
  "pan": 43454534217689456,
  "ipin": "etretewtwetewgtrwqgtrwgtfqgsrewgsfgsgdsgdsgdsgdsgds",
  "expiration_date": "0423",
  "uuid": "sfdsdfdsgsddsgdsgdsgdssdgdsg",
  "set_number": 6546436436436436,
  "stud_course_id": 4,
  "stud_from_kind": "4543543576676767676",
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to charge | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
set_number | required | number of student seat | String
stud_course_id | required | id of course | String
stud_from_kind | required | kind from

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ``{"pan": "43454534217689456","acq_tran_fee": 0,"dynamic_fees": 0,"issuer_tran_fee": 0,"form_no": 35435435435,"receipt_no": 453535345435,"english_name": "bakheet","arabic_name": "alsafy","response_status": "Successful","response_message": "Approved","response_code": 0}``| Transaction done successfully
400 | ``{ "details": {"set_number": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details":"you api key not valid"}``` | your api key not valid
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Educations Create Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/paypal/education/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/paypal/education/`

### Description

``this endpoint use to create order to pay for courses  by using  paypal``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json

{
  "set_number": "33253453532",
  "stud_course_id": 1,
  "stud_from_kind": 2,
  "amount": 500,
  "platform": "web"
}
```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
amount | required | amount of topup that customer need to pay | Float
set_number | required | number of student seat | String
stud_course_id | required | id of course | String
stud_from_kind | required | kind from
platform | required | platform that customer used to charge phone number | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"approval_url": "https://www.paypal.com/checkoutnow?token=45R87131522395454","order_id": "45R87131522395454"}```| order created  successfully
400 | ``{ "details": {"amount": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
402 | ```{"details": "your amount less than 1$"}``` | your amount less than 1$
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Educations approve Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/education/approve/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/education/approve/`

### Description

``this endpoint use to approve order that client created.``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "approve_order_id": "45R87131522395454",
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
approve_order_id | required | order that used in payment process in paypal | String
platform  | required | client type | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"form_no": 35435435435,"receipt_no": 453535345435,"english_name": "bakheet","arabic_name": "alsafy","response_status": "Successful","response_message": "Approved","response_code": 0}```| transaction done  successfully
400 | ``{ "details": {"approve_order_id": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
422 | ```{"details": "your order id not valid"}```|  user used not valid order
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

# Customs

## Custom Inquiry

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/custom/inquiry/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/custom/inquiry/`

### Description

``this endpoint use by customers to inquiry for invoice ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "declarant_code": 432423525,
  "bank_code": 435345345344
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
declarant_code | required | number of custom invoice | String
bank_code | required | the code of bank | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | `` { "bank_code": "435345345344","declarant_code": "432423525","amount": 10000,"proc_status": "Success","proc_error": "","registration_number": 43244,"year": "2019","total_amount": 1050,"status": "Successful","response_code": 0,"response_message": "Approved"}``| Transaction done successfully
400 | ``{ "details": {"bank_code": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details":"you api key not valid"}``` | your api key not valid
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Custom Payment

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/custom/pay/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/custom/pay/`

### Description

``this endpoint use by customers to pay invoice ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "amount": 500,
  "pan": 43454534217689456,
  "ipin": "etretewtwetewgtrwqgtrwgtfqgsrewgsfgsgdsgdsgdsgdsgds",
  "expiration_date": "0423",
  "uuid": "sfdsdfdsgsddsgdsgdsgdssdgdsg",
  "declarant_code": 432423525,
  "bank_code": 435345345,
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to charge | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
declarant_code | required | number of custom invoice | String
bank_code | required | the code of bank | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | `` {"bank_code": "435345345","declarant_code": "432423525","amount_sdg": 500,"proc_status": "success","receipt_number": 4454333,"receipt_serial": 23454545,"receipt_date": 42343354667,"status": "success","e_15_receipt_number": 45534534534,"response_code": 0,"response_message": "Approved"}``| Transaction done successfully
400 | ``{ "details": {"bank_code": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details":"you api key not valid"}``` | your api key not valid
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Customs Create Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/paypal/custom/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/paypal/custom/`

### Description

``this endpoint use to create order to pay invoice  by using  paypal``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
{
  "bank_code": 33253453532,
  "declarant_code": "0905450785",
  "amount": 1,
  "platform": "web"
}
```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
amount | required | amount of topup that customer need to pay | Float
declarant_code | required | number of custom invoice | String
bank_code | required | the code of bank | String
platform | required | platform that customer used to charge phone number | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"approval_url": "https://www.paypal.com/checkoutnow?token=45R87131522395454","order_id": "45R87131522395454"}```| order created  successfully
400 | ``{ "details": {"amount": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
402 | ```{"details": "your amount less than 1$"}``` | your amount less than 1$
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Customs approve Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/custom/approve/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/custom/approve/`

### Description

``this endpoint use to approve order that client created.``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "approve_order_id": "45R87131522395454",
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
approve_order_id | required | order that used in payment process in paypal | String
platform  | required | client type | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"bank_code": "33253453532","declarant_code": "0905450785","amount_sdg": "459.0","proc_status": "success","receipt_number": 4454333,"receipt_serial": 23454545,"receipt_date": 42343354667,"status": "success","e_15_receipt_number": 45534534534,"response_code": 0,"response_message": "Approved"}```| transaction done  successfully
400 | ``{ "details": {"approve_order_id": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
422 | ```{"details": "your order id not valid"}```|  user used not valid order
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

# Transfer

## Cash out Create Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/paypal/cashout/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST  https://sandbox.enayapay.com/api/v2.1/paypal/cashout/`

### Description

``this endpoint use to create order to send money  with paypal``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
       {
  "receiver_first_name": "bakheet",
  "receiver_last_name": "alsafy",
  "receiver_phone_number": "249905450785",
  "card_no": "2424242421424234234",
  "transfer_type": "card",
  "amount": 500,
  "platform": "web"
}


```

### request Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
receiver_first_name |required | first name of receiver | String
receiver_last_name | required | last name of receiver | String
receiver_phone_number | required | phone number of receiver | String
card_no | required | card number of receiver | String
transfer_type | required | type of transfer that customer used | String
amount | required | amount that customer need to send  | Float
platform | required | platform that customer used to charge | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"approval_url": "https://www.paypal.com/checkoutnow?token=45R87131522395454","order_id": "45R87131522395454"}```| order created  successfully
400 | ``{ "details": {"amount": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
402 | ```{"details": "your amount less than 1$"}``` | your amount less than 1$
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## cash out approve Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/paypal/cashout/approve/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/paypal/cashout/approve/`

### Description

``this endpoint use to approve order that customer created``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "approve_order_id": "45R87131522395454"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
45R87131522395454 | required | order that used in payment process in paypal | String

### response Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
acq_tran_fee | 0.0 | static fee | Float
issuer_tran_fee | 0.0 | issuer transaction fee | Float
dynamic_fee | 0.0 | dynamic fee | Float
response_message | depend on response code |message of transaction | String
response_status | Successful / Failed | status of transaction | String
amount_sdg | 0.0 | amount of transaction in sdg | Float
amount_usd | 0.0 | amount of transaction in usd | Float
tran_date_time | 124244 | date time of transaction | String
response_code | 0 | code of transaction | Integer

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"acq_tran_fee": 0.0,"dynamic_fees": 0.0,"issuer_tran_fee": 0.0,"response_message": "Approved","response_status": "Successful,"amount_sdg": 500.0,"amount_usd": 1.5,"tran_date_time": 232324341,"uuid": "sdasfsafsfsfs4edesfsefaefae","response_code": 0}```| transaction done  successfully
400 | ``{ "details": {"approve_order_id": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
422 | ```{"details": "your order id not valid"}```|  user used not valid order
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Cash In

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/paypal/cashin/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/paypal/cashin/`

### Description

``this endpoint use by customers to charge they paypal accounts ``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "pan": "3432423425235235235",
  "expiration_date": "0324",
  "ipin": "adasdaslf;skadfsdlfjsdkjlfdskjlfjsdkgsd",
  "amount": 5,
  "email": "bakheet12343@gmail.com",
  "platform": "web",
  "uuid": "sfsdfjsjkfskdjkjgfsdkjgkjsdkgkjdskjgkjskjgkjs"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to charge by it | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
email | required | email that customer to charge it | Email
amount | required | amount  that customer need to charge | Float
uuid | required | the key used to encrypt ipin| string
platform | required | platform that customer used to charge  | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"pan": "3432423425235235235","amount_sdg": 2914.65,"amount_usd": 5,"email": "bakheet12343@gmail.com","response_message": "Approved","response_code": 0,"transaction_status": "Pending"a}```| Transaction done successfully
400 | ``{ "details": {"pan": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
402 | ```{"details": "your amount less than 1$"}``` | your amount less than 1$
404 | | customer not registered
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

## Local Transfer

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/transfer/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/transfer/`

### Description

``this endpoint use by customers to send money using cards``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "from_card": "3432423425235235235",
  "to_card": "34324324234324324",
  "expiration_date": "0324",
  "ipin": "adasdaslf;skadfsdlfjsdkjlfdskjlfjsdkgsd",
  "amount": 600,
  "platform": "web",
  "uuid": "sfsdfjsjkfskdjkjgfsdkjgkjsdkgkjdskjgkjskjgkjs"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
from card | required | number of card that user want to send from  it | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
to_card | required | card number of receiver | String
amount | required | amount  that customer need to send | Float
uuid | required | the key used to encrypt ipin| string
platform | required | platform that customer used to charge  | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"acq_tran_fee": 0,"dynamic_fees": 0,"issuer_tran_fee": 0,"from_card": "***************3445","to_card": "***************24324","amount": 600,"response_message": "Approved","response_status": "Successful","tran_date_time": 344234324,"uuid": "wer44sd3rw3edesfdfsf43rsfsdfsdfdsfds","response_code": 0}```| Transaction done successfully
400 | ``{ "details": {"from_card": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | None | your api key not valid
404 | | customer not registered
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now

# Zain Topup

## Zain Local and international

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/zain/topup/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST  https://sandbox.enayapay.com/api/v2.1/zain/topup/`

### Description

``this endpoint for pay zain topup with local or international cards``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
       {
         "pan":"9222060104017709",
          "ipin":"314",
          "expiration_date":"0823",
          "to_card":"4242424242424242",
          "amount":345,
          "phone_no":"0905450785",
          "platform":"web",
          "payment_method":"Local",
          "uuid":"dsgfhgsfdhfdfdjgfjfgjfg87788"
}


```

### request Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to charge by it | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
phone_no | required | phone number that customer to charge it | Email
amount | required | amount  that customer need to charge | Float
uuid | required | the key used to encrypt ipin| string
platform | required | platform that customer used to charge  | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 |```{"pan": "4242424242424242424","acq_tran_fee": 0,"dynamic_fees": 0,"issuer_tran_fee": 0,"payment_info": "MPHONE=0905450785","response_message": "Approved","response_status": "Successful,"amount": 300,"tran_date_time": '121312321321',"uuid": fsr4r342423e2d23d2t2f2f34435,"response_code": 0}```| Transaction Done successfully
400 | ``{ "details": {"amount": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
402 | ```{"details": "your amount less than 1$"}``` | your amount less than 1$
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now


## Zain Create Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/paypal/telecom/110011001/topup/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/zain/topup/create/order/`

### Description

``this endpoint use to create order to pay topup to customer base on payeeid with paypal``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "phone_number": "0905450785",
  "amount": 300,
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
amount | required | amount of topup that customer need to pay | Float
phone_number | required | phone number want to charge it | String
platform | required | platform that customer used to charge phone number | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"approval_url": "https://www.paypal.com/checkoutnow?token=45R87131522395454","order_id": "45R87131522395454"}```| order created  successfully
400 | ``{ "details": {"amount": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
402 | ```{"details": "your amount less than 1$"}``` | your amount less than 1$
503 | ``` {"details" :"service unavailable"} ``` | service disable for now



## Zain Topup approve Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/zain/topup/approve/order/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/zain/topup/approve/order/`

### Description

``this endpoint use to provide topup to customer base on payeeid with paypal``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "approve_order_id": "45R87131522395454"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
45R87131522395454 | required | order that used in payment process in paypal | String

### response Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
acq_tran_fee | 0.0 | static fee | Float
dynamic_fee | 0.0 | dynamic fee | Float
issuer_tran_fee | 0.0 | issuer transaction fee | Float
response_message | depend on response code |message of transaction | String
response_status | Successful / Failed | status of transaction | String
amount_sdg | 0.0 | amount of transaction in sdg | Float
amount_usd | 0.0 | amount of transaction in usd | Float
tran_date_time | 124244 | date time of transaction | String
response_code | 0 | code of transaction | Integer

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"acq_tran_fee": 0.0,"dynamic_fees": 0.0,"issuer_tran_fee": 0.0,"payment_info": "MPHONE=0905450785","response_message": "Approved","response_status": response_status,"amount_sdg": 300,"amount_usd": 1.5,"service_type": Zain Topup,"tran_date_time": 344234324,"uuid": "asdadafafsaf334eadasdsadadasdq3","response_code": 0}```| transaction done  successfully
400 | ``{ "details": {"approve_order_id": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
422 | ```{"details": "your order id not valid"}```|  user used not valid order
503 | ``` {"details" :"service unavailable"} ``` | service disable for now






# Sudani Topup

## Sudani Local and international

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/sudani/topup/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST  https://sandbox.enayapay.com/api/v2.1/sudani/topup/`

### Description

``this endpoint for pay sudani topup with local or international cards``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
       {
         "pan":"9222060104017709",
          "ipin":"314",
          "expiration_date":"0823",
          "to_card":"4242424242424242",
          "amount":345,
          "phone_no":"0905450785",
          "platform":"web",
          "payment_method":"Local",
          "uuid":"dsgfhgsfdhfdfdjgfjfgjfg87788"
}


```

### request Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
pan | required | number of card that user want to charge by it | String
ipin | required | credential of customer | String
expiration_date | required | expiration  date of card| String
phone_no | required | phone number that customer to charge it | Email
amount | required | amount  that customer need to charge | Float
uuid | required | the key used to encrypt ipin| string
platform | required | platform that customer used to charge  | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 |```{"pan": "4242424242424242424","acq_tran_fee": 0,"dynamic_fees": 0,"issuer_tran_fee": 0,"payment_info": "MPHONE=0905450785","response_message": "Approved","response_status": "Successful,"amount": 300,"tran_date_time": '121312321321',"uuid": fsr4r342423e2d23d2t2f2f34435,"response_code": 0}```| Transaction Done successfully
400 | ``{ "details": {"amount": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
402 | ```{"details": "your amount less than 1$"}``` | your amount less than 1$
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
503 | ``` {"details" :"service unavailable"} ``` | service disable for now


## Zain Create Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/sudani/topup/create/order/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/sudani/topup/create/order/`

### Description

``this endpoint use to create order to pay topup to customer base on payeeid with paypal``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "phone_number": "0905450785",
  "amount": 300,
  "platform": "web"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
amount | required | amount of topup that customer need to pay | Float
phone_number | required | phone number want to charge it | String
platform | required | platform that customer used to charge phone number | String

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
201 | ```{"approval_url": "https://www.paypal.com/checkoutnow?token=45R87131522395454","order_id": "45R87131522395454"}```| order created  successfully
400 | ``{ "details": {"amount": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
402 | ```{"details": "your amount less than 1$"}``` | your amount less than 1$
503 | ``` {"details" :"service unavailable"} ``` | service disable for now



## Sudani Topup approve Order

```shell
# With shell, you can just pass the correct header with each request
curl "https://sandbox.enayapay.com/api/v2.1/sudani/topup/approve/order/" \
  -H "x-api-key: gffdgdfgdfgdfgdfgdgd , token: ffdfdsfsdfds "
```

> Make sure to replace `gffdgdfgdfgdfgdfgdgd` with your API key and Token.

### HTTP Request

`POST https://sandbox.enayapay.com/api/v2.1/sudani/topup/approve/order/`

### Description

``this endpoint use to provide topup to customer base on payeeid with paypal``

### Headers

```json
 {
  "x-api-key": "fddfgdfgdfgdfgdfg",
  "token": "fsfsfkwoieriworiewriweiriwerieworiowe"
}

```

### Body

```json
 {
  "approve_order_id": "45R87131522395454"
}


```

### Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
45R87131522395454 | required | order that used in payment process in paypal | String

### response Parameters Description

Parameter | Default | Description | Type
--------- | ------- | ----------- | ----------
acq_tran_fee | 0.0 | static fee | Float
dynamic_fee | 0.0 | dynamic fee | Float
issuer_tran_fee | 0.0 | issuer transaction fee | Float
response_message | depend on response code |message of transaction | String
response_status | Successful / Failed | status of transaction | String
amount_sdg | 0.0 | amount of transaction in sdg | Float
amount_usd | 0.0 | amount of transaction in usd | Float
tran_date_time | 124244 | date time of transaction | String
response_code | 0 | code of transaction | Integer

### Response

StatusCode | Response Data | Description
--------- | ------- | ---------
200 | ```{"acq_tran_fee": 0.0,"dynamic_fees": 0.0,"issuer_tran_fee": 0.0,"payment_info": "MPHONE=0905450785","response_message": "Approved","response_status": response_status,"amount_sdg": 300,"amount_usd": 1.5,"service_type": Zain Topup,"tran_date_time": 344234324,"uuid": "asdadafafsaf334eadasdsadadasdq3","response_code": 0}```| transaction done  successfully
400 | ``{ "details": {"approve_order_id": ["This field is required."]} }``| Bad request occurred when forget parameter
401 | ```{"details": "your token or api key not in header"}``` | your api key not valid or token
406 | ```{"response_code": 696,"response_message": "SYSTEM_ERROR"}``` | service provider errors with code
422 | ```{"details": "your order id not valid"}```|  user used not valid order
503 | ``` {"details" :"service unavailable"} ``` | service disable for now