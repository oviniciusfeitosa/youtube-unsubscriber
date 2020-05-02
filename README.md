# Youtube Unsubscriber

# Unsubscriber

- Access the link : `https://www.youtube.com/feed/channels`
- Press **F12**
- Insert the code below in your console

```javascript
var count = document.querySelectorAll("ytd-channel-renderer:not(.ytd-item-section-renderer)").length;
var randomDelay = 500;

function unsubscriber(randomDelay) {

    if (count == 0) return false;

    unsubscribeButton = document.querySelector('.ytd-subscribe-button-renderer');
    unsubscribeButton.click();

    setTimeout(function () {
        document.getElementById("confirm-button").click()
        count--;
        console.log("Remaining: ", count);

        setTimeout(function () {
            unsubscribedElement = document.querySelector("ytd-channel-renderer");
            unsubscribedElement.parentNode.removeChild(unsubscribedElement);
            unsubscriber(randomDelay)
        }, randomDelay);
    }, randomDelay);
}

unsubscriber(randomDelay);
```

## References

- https://stackoverflow.com/questions/48874382/how-to-unsubscribe-from-all-the-youtube-channels-at-once
- https://gitmoji.carloscuesta.me/
