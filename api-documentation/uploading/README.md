---
description: REpresentational State Transfer
---

# REST API

{% swagger baseUrl="https://videodocker.io" path="/videos/" method="post" summary="Create video" %}
{% swagger-description %}
This endpoint allows you to create a new video.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authentication token to track down who is emptying our stocks.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payload" type="object" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="APIKey" type="string" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="domainId" type="string" %}

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

{% swagger baseUrl="https://videodocker.io" path="/videos/:id" method="get" summary="Read video" %}
{% swagger-description %}
This endpoint allows you to retrieve a video.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="JSON Response" %}
```javascript
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://videodocker.io" path="/videos/:id" method="put" summary="Update video" %}
{% swagger-description %}
This endpoint allows you to update an existing video.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://videodocker.io" path="/videos/:id" method="delete" summary="Delete video" %}
{% swagger-description %}
This endpoint allows you to delete an existing video
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}
