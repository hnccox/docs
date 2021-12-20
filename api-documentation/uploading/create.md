# Create

{% swagger baseUrl="https://videodocker.io" path="/videos/" method="post" summary="Create video" %}
{% swagger-description %}
This endpoint allows you to create a new video.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authentication token.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="payload" type="object" %}

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

