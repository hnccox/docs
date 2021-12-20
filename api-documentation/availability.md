---
description: Public/Private/Secured
---

# Availability

There are 2 types of API Keys:\
\- Public; Use the public key for client side GET Requests\
\- Private; Use the private key for server side POST Requests.

Video's can have 3 access tiers:\
\- Public; video can be accessed using a HTTP GET Request.\
\- Private; video can be accessed using a HTTP GET Request or HTTP POST Request.\
\- Secured; video can only be accessed using a HTTP POST Request using the Private API Key.

{% hint style="info" %}
In order to protect your Private API Key from being publicly visible, a server side request has to be made to https://embed.videodocker.io/.
{% endhint %}

{% swagger baseUrl="https://embed.videodocker.io" path="/videos/:id" method="get" summary="Public" %}
{% swagger-description %}
This endpoint allows you to embed a video on your domain.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
ID of the video to get.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authentication token of the domain.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="APIKey" type="string" %}
Public API key.
{% endswagger-parameter %}

{% swagger-response status="200" description="Cake successfully retrieved." %}
```
{    "name": "Cake's name",    "recipe": "Cake's recipe name",    "cake": "Binary cake"}
```
{% endswagger-response %}

{% swagger-response status="404" description="Could not find a cake matching this query." %}
```
{    "message": "Ain't no cake like that."}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://embed.videodocker.io" path="/videos/:id" method="post" summary="Private/Secured" %}
{% swagger-description %}
This endpoint allows you to embed a video on your domain.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
ID of the video to get.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authentication token of the domain.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="APIKey" type="string" %}
Private API key.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://embed.videodocker.io" path="/videos/:id" method="post" summary="Secured" %}
{% swagger-description %}
This endpoint allows you to embed a video on your domain.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
ID of the video to get.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authentication token of the domain.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="APIKey" type="string" %}
Private API key.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}
