# Park Finder: A Mobile First Application

**A small, location-based application using Ottawa’s open data and mobile first ideas.**

## A little history’ll do ya good

The [Ottawa Dog Park Finder](http://parkfinder.ottawadogblog.ca/) was originally created for the [Ottawa Open Data](http://opendataottawa.ca/) movement to show to the city what is possible. [Read more about the original process in the Open Data blog post.](/articles/open-data-ottawa)) But, it was also created to help Ottawa dog owners find the best parks in the city.

There was one feature that I felt was missing from Park Finder since it launched: a mobile version. When the [City of Ottawa](http://ottawa.ca/) decided to host an [application contest for Open Data apps](http://apps4ottawa.ca/) I decided to enter Park Finder, but first make it mobile ready.

## The open web platform

I’m a web developer at heart and don’t have much interest in doing native applications, so the only logical choice was to make a mobile web app. The concept of [Mobile First](http://www.lukew.com/ff/entry.asp?933) is exactly the solution I wanted. The idea behind Mobile First, a concept envisioned by [Luke Wroblewski](http://www.lukew.com/), was to design for mobile—first—then design for other platforms. Forcing designers to determine what features are really important.

Though, we shouldn’t stop at design with Mobile First; when creating web sites and web applications, the same ideas can be applied to code. Why not default to mobile, then if conditions are right, expand to desktop versions. That’s exactly what I did when re-developing Park Finder in December.

## The supported devices

My goal from the start was to make the app browser agnostic (the goal of any *real* web developer). So, [using my mobile testing suite](/articles/mobile-testing-suite/), I set out to make Park Finder work on all those devices.

The project was a success, I was able to support all the browsers listed in my mobile testing suite (forget BB OS 4, it sucks!) and all the major desktop browsers.

In the spirit of Mobile First, and mobile in general, I simplified the application on mobile to just the essentials:

- displaying the parks nearest you (geo-location, please);
- searching for a park;
- and rating parks.

The only major feature that was removed was park filtering.

The original application was a one page app, clicking on parks just displayed them on the Google Map. Since I needed to support mobiles without Google Maps, the app turned into a multi-page app (as it should have been from the beginning) and used [Google Static Maps](http://code.google.com/apis/maps/documentation/staticmaps/) for the geo-location functionality.

### Device classification

I segregated devices into a few classifications: basic, enhanced and enhanced wide. Basic includes all mobile phones and IE 6. Enhanced includes tablet size devices and screens with widths less than 1000 px. Enhanced wide includes all larger screens.

I had originally planned to put Google Maps onto the mobile phones that supported it (Android, iPhone, BB OS 6, Bada), but the usability just wasn’t as great as I had hoped, so Google Maps got relegated to enhanced and enhanced wide only devices (tablets and desktops).

## Technical set up

The general idea was to send the basic version of the site to all browsers to minimize download time (and because I am not the biggest fan of browser sniffing). Then using [Modernizr](http://www.modernizr.com/) and a few other techniques, dynamically load the other resources as required.

### The loading process

#### 1. Basic

- HTML, `basic.css`, `basic.js`, Modernizr, [Geo.js](http://code.google.com/p/geo-location-javascript/)
- **No Javascript frameworks for basic, too heavy.**

#### 2. Enhanced

- **Only executed if the browser supports Google Maps**
- Dynamically include `enhanced.css` and `enhanced-wide.css` (with `@media min-width: 1000px`)
- Dynamically include Google Maps
- Dynamically include `enhanced.min.js`, a bunch of Javascript files minified together to preserve loading order [jQuery](http://jquery.com), [Marker Manager](http://code.google.com/p/google-maps-utility-library-v3/), [LatLng](http://www.movable-type.co.uk/scripts/latlong.html), <code>enhanced.js</code>)

#### 3. Enhanced wide

- Enhanced wide does not have any feature differences than enhanced, it only looks different: parks are listed beside the map instead of below.

### Some code bits

There were a couple other things I needed to detect to fully support my Mobile First idea.

#### Modernizr.xhr

A Modernizr test to check for XMLHttpRequest support. Used to distinguish between desktop IE 6 and Windows Mobile 6.5 IE 6.

{% highlight js %}
Modernizr.addTest('xhr', function () {
  return !(typeof XMLHttpRequest == 'undefined');
});
{% endhighlight %}

#### Modernizr.mediaqueries

A Modernizr test to check for very basic media query support. **As of Modernizr version 2, similar code is already included.**

{% highlight js %}
Modernizr.addTest('mediaqueries', function () {
  var ret = false
    , test = document.createElement('div')
    , styles = document.createElement('style')
    , styledef = document.createTextNode('#modernizr-mq-tester{top:-999em;position:absolute;display:none;} @media screen and (min-width:5px){#modernizr-mq-tester{display:block;}}')
    , head = document.getElementsByTagName['head'](0)
  ;

  test.id = 'modernizr-mq-tester';
  test.innerHTML = '&nbsp;';
  styles.id = 'modernizr-mq-styles';

  try {
    styles.appendChild(styledef);
    head.appendChild(styles);
    document.documentElement.appendChild(test);
    ret = getComputedStyle(test, null).getPropertyValue('display') == 'block';
    head.removeChild(styles);
    document.documentElement.removeChild(test);
  } catch (e) {}

  return ret;
});
{% endhighlight %}

#### Modernizr.googlemaps

Though not completely accurate, used to detect Google Map support on devices. The code below doesn’t detect mobile phones because it’s looking for a minimum width of 660 px; just change that to 320 px for phone support.

{% highlight js %}
Modernizr.addTest('googlemaps', function () {
  var cw = document.documentElement.clientWidth
    , isIE7 = document.documentElement.className.indexOf('ie7') > -1
    , isIE8 = document.documentElement.className.indexOf('ie8') > -1
    , isIEMobile = document.documentElement.className.indexOf('ie7mobile') > -1
  ;

  if (cw < 600 || !Modernizr.xhr || isIEMobile) return false;

  if (
    (cw < 780 && Modernizr.touch && Modernizr.mediaqueries)
    || (cw >= 780 && (Modernizr.mediaqueries || isIE8 || isIE7))
  ) return true;

  return false;
});
{% endhighlight %}

## The final app

I’m very happy with the final application, it turned out amazing. I’m super excited because **I won bronze in my category in the [Apps4Ottawa](http://apps4ottawa.ca/) competition**!

### A couple niggles

I’m not the biggest fan of the flash that happens just before the enhanced wide layout displays. I think the solution is to detect enhanced wide using media queries inside <code>basic.css</code> and hide the whole application, then after <code>enhanced-wide.css</code> is loaded, fade the application back in.

Also, since the app is now a many-page application, when you load a specific park’s URL in a desktop browser it should immediately show it in Google Maps, but does not.

## The future for Mobile First

This technique works great for many web sites. Where the most important information is sent as a basic package, then detect features client side, and, if required, dynamically load other assets. Think about a site with a heavy sidebar: don’t send the sidebar to mobile, but AJAX it in for desktop clients.

This mobile first idea, coupled with responsive design, is the way forward for many sites and is what I am exploring on all my future projects.
