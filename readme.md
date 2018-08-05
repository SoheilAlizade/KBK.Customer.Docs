## KBK Customer API Docs

<div dir='rtl'>
ثبت نام     
</div>

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
  "$id": "1",
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
