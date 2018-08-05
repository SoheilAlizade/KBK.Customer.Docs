## KBK Customer API Docs

<div dir='rtl'>

ثبت نام     
</div>
<br />
<p dir='rtl'>
پس از این که ثبت نام تکمیل شود یک اس ام اس حاوی یک کد به شماره ثبت نام کننده ارسال می شود.     
</p>

URL

```
POST /api/v1/account/register 
```

Form

```
{
  "PhoneNumber": "string",
  "FirstName": "string",
  "LastName": "string"
}
```

Response

```
{
  "StatusCode": 201,
  "Message": "The Resource Successfully created ;)",
  "IsSuccess": true
}
```

Status codes

> 400

```
The passed form is not valid please check response

```

Example:

```
{
  "ModelState": {
    "$id": "2",
    "IsValid": false,
    "ErrorCount": 1,
    "Errors": [
      {
        "$id": "3",
        "Key": "createAccount.PhoneNumber",
        "Error": [
          "The field PhoneNumber is not valid"
        ]
      }
    ]
  },
  "ErrorMessage": [
    "Bad Request! please check your parameters"
  ],
  "HttpStatus": 400,
  "IsSuccess": false
}
```

> 409

```
The phoneNumber that you are passed to api is already taken.
```

Example:

```
{
  "ErrorMessage": [
    "Name 09198143732 is already taken."
  ],
  "HttpStatus": 409,
  "IsSuccess": false
}
```

<div dir='rtl'>
احراز هویت
</div>

URL

```
POST /api/v1/account/verify 
```

Form

```
{
  "VerifyCode": "string",
  "PhoneNumber": "string",
  "PlayerId": "string"
}
```

Response:

```
{
  "access_token": "token",
  "token_type": "bearer",
  "expires_in": 35999999,
  "refresh_token": "refreshtoken"
}
```

Example:

```
{
  "access_token": "eyJhbGciOiJodHRwOi8vd3d3LnczLm9yZy8yMDAxLzA0L3htbGRzaWctbW9yZSNobWFjLXNoYTI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiMDkzOTYyODI3MDMiLCJodHRwOi8vc2NoZW1hcy5taWNyb3NvZnQuY29tL3dzLzIwMDgvMDYvaWRlbnRpdHkvY2xhaW1zL3NlcmlhbG51bWJlciI6IjI0M2EwOThmNzExYTRhN2FhOGVjYjMwNGZhYzA4NTU5IiwiaHR0cDovL3NjaGVtYXMubWljcm9zb2Z0LmNvbS93cy8yMDA4LzA2L2lkZW50aXR5L2NsYWltcy91c2VyZGF0YSI6IjQyYmNjODMzLTkwOTgtZTgxMS1hOTQzLTkwMWIwZWU1NTViMyIsIm5iZiI6MTUzMzQ2MDYwOSwiZXhwIjoxNTY5NDYwNjA5LCJpc3MiOiJodHRwOi8vbG9jYWxob3N0LyIsImF1ZCI6IkFueSJ9.Q4eVSstoFEqqoe_06mqnJxRQOW0gNI2KBqu98R4Js8M",
  "token_type": "bearer",
  "expires_in": 35999999,
  "refresh_token": "d1ff08f8245740ed9749cc189ffe246f"
}
```

<div dir='rtl'>
 ارسال مجدد کد
</div>
<br/>
<p dir='rtl'>
در حالت توسعه، سروریس گیرنده میتواند از طریق body یا یک هدر به نام x-verify-code کد تایید را دریافت کند.
</p>
URL

```
/api/v1/account/retry-verify
```

Response:

```
{
  "$id": "1",
  "StatusCode": 200,
  "Message": "The code successfully sent. code:406690",
  "IsSuccess": true
}
```

Headers

```
{
  "connection": "keep-alive",
  "content-length": "97",
  "content-type": "application/json; charset=utf-8",
  "date": "Sun, 05 Aug 2018 09:16:28 GMT",
  "x-verify-code": "The code successfully sent. code:406690"
}
```