---
description: Public/Private/Secured
---

# Availability

There are 2 types of API Keys:  
- Public; Use the public key for client side GET Requests  
- Private; Use the private key for server side POST Requests.

Video's can have 3 access tiers:  
- Public; video can be accessed using a HTTP GET Request.  
- Private; video can be accessed using a HTTP GET Request or HTTP POST Request.  
- Secured; video can only be accessed using a HTTP POST Request using the Private API Key.

{% hint style="info" %}
In order to protect your Private API Key from being publicly visible, a server side request has to be made to https://embed.videodocker.io/.
{% endhint %}

{% api-method method="get" host="https://embed.videodocker.io" path="/videos/:id" %}
{% api-method-summary %}
Public
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to embed a video on your domain.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of the video to get.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token of the domain.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="APIKey" type="string" %}
Public API key.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{    "name": "Cake's name",    "recipe": "Cake's recipe name",    "cake": "Binary cake"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://embed.videodocker.io" path="/videos/:id" %}
{% api-method-summary %}
Private/Secured
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to embed a video on your domain.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of the video to get.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token of the domain.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="APIKey" type="string" required=true %}
Private API key.
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://embed.videodocker.io" path="/videos/:id" %}
{% api-method-summary %}
Secured
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to embed a video on your domain.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
ID of the video to get.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token of the domain.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="APIKey" type="string" required=true %}
Private API key.
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

