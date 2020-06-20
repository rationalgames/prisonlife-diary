+++
title = "2020 06 20 Alpha Access"
date = 2020-06-20T19:51:08+02:00
+++

In order to try out the alpha release of the API:

## Create your user

You can use the Signup POSTMAN request, or manually with curl...
```
curl --location --request POST 'https://static.133.34.69.159.clients.your-server.de:8443/user/<your-user-here>/<your-password-here>'
```

This call will give you back this response

```
{
    "data": {
        "type": "user",
        "id": "test",
        "attributes": {
            "apiKey": "fc246829719f916c4587e55cc6e520fb7e6ed517",
            "createdAt": "Sat, 20 Jun 2020 17:57:11 +0000"
        },
        "meta": {
            "warnings": [
                "DO NOT LOOSE YOUR PASSWORD: If you forget your user ID or your password you will not be able to use it anymore. We do not store any personal detail and for that reason we cannot recover your account.",
                "DO NOT LOOSE YOUR API KEY: API Key is the token that you need to use to access the game. DO NOT SHARE IT!"
            ],
            "info": [
                "You can change your password any time from your user profile section",
                "You can regenerate your API key any time from your user profile section",
                "To play the game you must add the PrisonLifeKey header with your API key as the value in each request"
            ]
        },
        "links": {
            "self": "/user/test/your-password-here",
            "play": {
                "method": "POST",
                "href": "/play/v1/{your-prisoner-name}"
            }
        }
    }
}
```

## Download POSTMAN (no UI yet, sorry!)
You can play using simple REST calls.

Postman sample collection: https://static.133.34.69.159.clients.your-server.de:8443/postman/prisonlife.json

### Configure your postman collection

Import the collection and select EDIT.

Under edit section, make sure to configure

### Authorization
* API key: 
    * Key = PrisonLifeKey
    * Value = YourAPIKey 

### Variables
* host: https://static.133.34.69.159.clients.your-server.de:8443
* character_id: the character ID that you want to play with after you create one.

## Example of Request using CURL

If you do not want to use Postman, you can use curl like this
```
curl --location --request GET 'https://static.133.34.69.159.clients.your-server.de:8443/play/v1/1' \
--header 'PrisonLifeKey: ThisIsYourAPIKeyValue'
```