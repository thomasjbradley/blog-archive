# First Lab Project: Signature Pad

**Signature Pad is a jQuery plugin for assisting in the creation of an HTML5 canvas based signature pad. Records the drawn signature in JSON for later regeneration.**

Signature Pad is the first official project posted to my [lab section](/lab/) (and there are two more projects in the queue). Getting something posted on labs has been a long time coming, but it’s finally here.

## A Little History

Signature Pad started out using Flash and ExternalInterface instead of HTML5 Canvas. It worked, but wasn’t easily configured and—of course—*relied* on Flash. The signature bits were a little slow on my Mac and saving out the signature as an image wasn’t as reliable as I hoped.

I wanted to make something faster, simpler and more reliable and preferably standards based. So I set out to duplicate the functionality in Javascript/Canvas.

I was surprised at how quickly it came together in canvas, but not without a few IE related hick-ups. After making the first prototype I decided that it would be a great [jQuery plugin](http://plugins.jquery.com/).

## Making a jQuery Plugin

Making a jQuery plugin was a rewarding experience and I found it to be fairly simple. It really helped me understand a few things about Javascript that I had never used before.

Here are a couple resources that helped:

- [jQuery Plugin Authoring Docs](http://docs.jquery.com/Plugins/Authoring)
- [Learning jQuery: A Plugin Development Pattern](http://www.learningjquery.com/2007/10/a-plugin-development-pattern)
- [Snook: Developing a jQuery Plugin](http://snook.ca/archives/javascript/jquery_plugin)

I also found it really helpful to look at other jQuery plugins and see how they did things.

## The Major Hick-ups

There were a few major hick-ups, related to IE, while developing the plugin.

The first plagued IE7 and IE8 and was related to initially drawing the grey signature line on the canvas. I had it working for a while and then it stopped and I had a long drawn battle to figure out why.

Through my debugging I discovered that only on the first call to the `drawSigLine()` method, the line wasn’t drawn, but every subsequent time it worked.

I don’t fully remember how I came to the solution, but the solution was just to not draw the line immediately on page load. Instead I created a timeout of 50 milliseconds that would then draw the line when it fired. Problem solved.

The second major issue plagued IE8 only and was related to [Explorer Canvas](http://code.google.com/p/explorercanvas/). In IE8 strict mode, I couldn’t draw on the canvas. By couldn’t draw, I mean I could draw, it just wouldn’t display.

Through some online digging I found that excanvas sets `overflow: hidden` on the VML div that it creates. This prompted me to add a *wonderful* hack to my code that checks for the div with `overflow: hidden` and set it’s overflow to visible.

## Documentation and Examples

The lab section has complete examples, documentation and tutorials on the Signature Pad.

- [Documentation & Tutorials](/lab/signature-pad/)
- [Demo of Accepting a Signature](/lab/signature-pad/accept)
- [Demo of Regenerating a Signature](/lab/signature-pad/regenerate)
