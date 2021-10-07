# PHP

With Standalone PHP the embedding code is exactly the same as with HTML. The only difference is that you can supply a video ID in the embedding URL by using a variable \(e.g. $\_GET\['videoID'\]\).

Using a serverside language, it is possible to embed the videos on your page without exposing your APIKey to the public.

{% tabs %}
{% tab title="Public" %}
```markup
<iframe width="512" height="288"
    src="https://embed.videodocker.io/videos/<?php echo $_GET[videoId];?>?APIKey=YOUR-PUBLIC-APIKEY"
    frameborder="0" 
    allowfullscreen>
</iframe>

```
{% endtab %}

{% tab title="Private" %}
```markup
<iframe width="512" height="288"
    src="embed.php?videoId=<?php echo $_GET[videoId];?>" 
    frameborder="0" 
    allowfullscreen>
</iframe>
```
{% endtab %}

{% tab title="Secured" %}
```php
require("embed.php")


```
{% endtab %}
{% endtabs %}

{% code title="embed.php?videoId=" %}
```php
<?php

function embed_videodocker($videoId) {
		if(!$videoId) { echo "No videoId supplied!"; exit; }
		
		$domain = "https://www.videodocker.com/"; // Enter your domain here
		$domainId = "59efa5cc944434081cbab3c4"; // Enter your domainId here
		$APIKey = "22222222"; // Enter your Private API key here
		$url = "https://embed.videodocker.io/";
		
		$data = array(
			'domainId' => $domainId, 
			'APIKey' => $APIKey, 
			'videoId' => $videoId
		);

		$options = array(
	   		'http' => array(
    		'header'  => array(
    			"Content-type: application/x-www-form-urlencoded",
    			"Referer: ".$domain,
    		),
    		'method'  => "POST",
    		'content' => http_build_query($data)
    		)
		);
		
		$context  = stream_context_create($options);
		$result = file_get_contents($url, false, $context);
		if ($result === FALSE) { /*Do something*/ }
		return $result;
}

echo embed_videodocker($_GET['videoId']);

?>
```
{% endcode %}

