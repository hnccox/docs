# HTML

Embedding a video with HTML is a fairly straightforward process:

{% tabs %}
{% tab title="Static" %}
This is the easiest method. The video ID will be static in the embedding URL, therefore you will have to embed each video separately on your website.
{% endtab %}

{% tab title="Responsive" %}
If you want to have responsive embedding, use a wrapper div and change the iframe attributes as seen below. The "padding-bottom" is very important! \(Ratio 16:9 = 56.25%\)
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Static" %}
```markup
<iframe width="512" height="288" 
    src="https://embed.videodocker.io/videos/59efa5f5944434081cbab3c5?APIKey=YOUR-PUBLIC-APIKEY" 
    style="position:absolute; top:0px; right:0px; bottom:0px; left:0px; width:100%; height:100%"
    frameborder="0" 
    allowfullscreen>
</iframe>
```
{% endtab %}

{% tab title="Responsive" %}
```markup
<div style="position:relative; width:100%; height:0px; padding-bottom:56.25%;">
    <iframe width="100%" height="100%" 
        src="https://embed.videodocker.io/videos/59efa5f5944434081cbab3c5?APIKey=YOUR-PUBLIC-APIKEY" 
        style="position:absolute; top:0px; right:0px; bottom:0px; left:0px; width:100%; height:100%" 
        frameborder="0" 
        allowfullscreen>
    </iframe>
</div>
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
For a minimum/maximum video size, add another wrapper around the example code above:
{% endhint %}

```markup
<div style="min-width:256px; width:100%; max-width:1920px; height:auto;">
⋮
</div>
```

