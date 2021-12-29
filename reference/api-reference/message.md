---
description: Messages can be stored on the block chain
---

# Message

## Creating a new message

{% swagger baseUrl="https://permastore.app/api/v1" method="post" path="/message/create" summary="Create a new message." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="contents" required="true" type="string" %}
The message you want to store (max. 64 characters)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="format" required="true" type="string" %}
The format of the contents ('plaintext' or 'hex')
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" %}
Your API key
{% endswagger-parameter %}

{% swagger-response status="200" description="Request successfully created" %}
Sample request

```javascript
{
  "data": {
    "request": {
      "contents": "Happy new year!",
      "format": "plaintext"
    }
  }
}
```

Response

```
{
  "status": "ok",
  "message": "Request stored and resolved",
  "success": true,
  "data": {
    "request": {
      "transaction_id": "1d3ff543-a15b-454c-bf53-1dea526cff52",
      "contents": "Happy new year!",
      "received_at": "2021-12-26 13:33:22",
      "sent_at": "2021-12-26 13:33:22",
      "returned_at": null,
      "status": "resolved",
      "result": {
        "transaction_id": "0x8eb7f0fff28fcc5f862e7a6d803916fd8ff5d29b0820914f31ef785e0de3d8ae",
        "received_at": "2021-12-26 13:33:22"
      }
    }
  }
}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="Error with the request" %}
Please check the request you submitted and try again

```
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="503: Service Unavailable" description="Service interruption" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

## Check status of a message

{% swagger method="get" path="/message/status/{transaction_id}" baseUrl="https://permastore.app/api/v1" summary="Check the status of your message" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="transaction_id" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" %}
Your API Key
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}
