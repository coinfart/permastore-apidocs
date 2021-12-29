# Quick Start

## Get your API keys

Create an account on permastore.app (coming soon!). All API requests are authenticated using API keys. Any request that doesn't include an API key will return an error.

You can generate an API key from your Dashboard at any time (coming soon!).

## Make your first request

To make your first request, send an authenticated request to the request/create endpoint. This will create a new `message`, which will be stored on the block chain.

Take a look at how you might call this method:

{% tabs %}
{% tab title="curl" %}
```
curl https://permastore.app/api/v1/request/create
    -u YOUR_API_KEY:
    -d contents='My first message'
    -d format='plaintext'
```
{% endtab %}

{% tab title="php" %}
```
// php example coming soon!
```
{% endtab %}
{% endtabs %}

Please refer to the API Reference for more detailed information.
