# Update

{% swagger baseUrl="https://videodocker.io" path="/videos/:id" method="put" summary="Update video" %}
{% swagger-description %}
This endpoint allows you to update a video.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
ID of the video to update.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authentication token to track down who is emptying our stocks.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="recipe" type="string" %}
The API will do its best to find a cake matching the provided recipe.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="gluten" type="boolean" %}
Whether the cake should be gluten-free or not.
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

