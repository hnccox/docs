# JavaScript

Using JavaScript, the code traverses the DOM and checks for iframe elements containing the data attribute `data-videodocker = "videoID"`, where videoID is the ID of the video to get.

```markup
<!-- Global video tag (videodocker.js) - VideoDocker -->
<script src="https://videodocker.io/embed/js" defer></script>
<script type="text/javascript">
    window.videodocker = {
        "apikey": { 
            "public": "YOUR-PUBLIC-APIKEY" 
        }
    }
</script>    
<script type="text/javascript" defer>
    window.addEventListener("load", function () {
        const iframes = document.querySelectorAll("iframe[data-videodocker]");
        iframes.forEach((iframe) => {
            iframe.width = "100%";
            iframe.height = "100%";
            iframe.src = "https://videodocker.io/videos/"+iframe.dataset.videodocker+"?APIKey="+window.videodocker.apikey.public;
            iframe.style.position = "absolute";
            iframe.style.top = iframe.style.right = iframe.style.bottom = iframe.style.left = "0";
            iframe.style.width = "100%";
            iframe.style.height = "100%";
            iframe.setAttribute("frameborder", "0");
            iframe.setAttribute("allowfullscreen");            
        })
    }
</script>
⋮
<iframe data-videodocker="videoID"></iframe>
```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}



