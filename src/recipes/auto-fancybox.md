title: Enhance image links on your site with FancyBox

----

version: 1.0.1

----

authors: Martijn Geerts

----

tags: modal, javascript, fancybox

----

problem:
You have got thumbnails in your body fields that link to larger versions of the image, but you want to avoid setting a class on each of them manually (or confront your customer with the Rich Text Editors settings window).

----

solution:
Find all links to image files (jpg, png, gif) that originate in the particular ProcessWire installation.
```JS
$("[href^='/site/assets/files/']").filter(function() {
    return this.href.match(/.*[jpg|png|gif]$/i);
}).addClass('to-fancy');
```

Init fancybox on this selection. You can supply an options object.
```JS
$('.to-fancy').fancybox();
```

----

resources:
* [Forum thread](https://processwire.com/talk/topic/5578-how-to-use-fancybox/?p=73141)
