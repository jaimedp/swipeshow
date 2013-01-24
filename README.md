Swipeshow
=========

The unassuming touch-enabled JavaScript slideshow.

 * __Showcase anything.__ You're not limited to images: any markup will do.
 * __Touch-enabled.__ Swipe away on your iPad, iPhone, Android device, or 
 anything touch-enabled.
 * __Style-it-yourself.__ The default CSS has nothing in it except laying out 
 your slides side-by-side. You'd be in charge of figuring out how to add borders 
 or anything else you like.

Markup
------

### JavaScript

``` js
$(".slideshow").swipeshow();
```

### HTML

``` html
<div class="slideshow">
  <ul class="slides">
    <li class="slide"> ... </il>
    <li class="slide"> ... </li>
    <li class="slide"> ... </li>
  </ul>
</div>
```

### CSS

``` css
.slideshow,
.slideshow .slides,
.slideshow .slide {
  display: block;
  width: 200px;  /* Change me */
  height: 200px; /* Change me */
  margin: 0;
  padding: 0;
  list-style: none;
  transform: translate3d(0, 0, 0);
}

.slideshow {
  overflow: hidden;
  position: relative;
}

.slideshow .slides {
  width: 99999px;
  position: absolute;
  top: 0;
  left: 0;
}

.slideshow .slide {
  float: left;
}
```

Options
-------

``` js
$(".slideshow").swipeshow({
  autostart: true,
  interval: 3000,     /* Time between movement (ms) */
  initial: 0,         /* First slide's index */
  speed: 700,         /* Animation speed (ms) */
  friction: 0.3,      /* What happens when you swipe out of bounds? */
  mouse: true,        /* enable mouse dragging controls? */

  onactivate: function(){},
  onpause: function(){},
});
```

Next/previous buttons
---------------------

Add some buttons with the class `.next` and `.previous` inside `.slideshow`.
They will work as expected.
(style them yourself)

``` html
<div class="slideshow">
  <ul class="slides">
    <li class="slide"> ... </il>
    <li class="slide"> ... </li>
    <li class="slide"> ... </li>
  </ul>

  <!-- optional controls: -->
  <button class="next"></button>
  <button class="previous"></button>
</div>
```

If you prefer them to be elsewhere, you can pass them as jQuery objects to 
the options:

``` js
$(".slideshow").swipeshow({
  $next: $("button.next"),
  $previous: $("button.previous")
});
```

Programmatic usage
------------------

Access them using `$(".slideshow").swipeshow()`:

``` js
$(".slideshow").swipeshow().next();
$(".slideshow").swipeshow().previous();
$(".slideshow").swipeshow().goTo(2);

$(".slideshow").swipeshow().pause();
$(".slideshow").swipeshow().start();
```

License
-------

MIT
