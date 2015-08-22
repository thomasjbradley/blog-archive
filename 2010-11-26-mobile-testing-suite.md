---
updated: 2010-12-20
---

# Mobile Testing Suite

**Since the mobile internet is growing at an extremely quick pace I felt it was prudent to start testing/developing sites on mobile devices.**

I started by downloading a bunch of emulators including Android, WebOS, BlackBerry and Windows Phone 7. But quickly found limitations to this approach.

The main limitation of the emulators is that they can’t be open at the same time as my virtual versions of IE. Another issue I quickly found was the lack of Nokia emulators and since Nokia is the most popular handset maker in the world, this is a major issue. I did find the [Nokia Remote Device Access](http://www.developer.nokia.com/Devices/Remote_device_access/), but the idea of scheduling a time and waiting wasn’t something I was excited about.

And we all know that emulators are far from perfect, so actual devices are what I needed.

## Researching the Phones

I have been [reading a lot of articles](http://www.quirksmode.org/blog/), [watching a lot videos](http://www.lukew.com/ff/entry.asp?1137) and [clicking through a lot of slideshows](http://www.slideshare.net/bryanrieger/rethinking-the-mobile-web-by-yiibu) trying to wrap my head around the extremely complex and fractured mobile web market.

One article that was extremely helpful was ‘[A Practical Guide to Nokia Browsers](http://yiibu.com/articles/practical-guide-to-nokia-browsers/)’ which is a great overview and explanation of the different Symbian browser versions and gives a smattering of Nokia phones that would be good for testing.

The rest of the mobile market isn’t as difficult to handle, assuming that you rule out a bunch of feature phones that people don’t likely surf the internet on anyways; but if they do, they are crazy.

I compiled a list of the browsers and operating systems that I wanted to support and from that determined what phones to get. It took a lot of comparing phone specifications and looking around online to find devices for sale (four days to be exact) to find the phones that would fit into my test suite.

I didn’t want to spend too much money, so I was always conscious of the prices. Continued cost was also very important and I didn’t want to have to support multiple mobile data plans. All of the phones I have in my test suite, therefore, are WiFi equipped.

## List of Browsers, OSs, Phones

So, without further adieu, here is the final list of phones I have purchased and where I got them from and how much they cost:

{% include mobile-table.html %}

## Missing Browsers

You’ll Likely notice a few missing from the list. The first is the venerable mobile browser: [Opera](http://www.opera.com/mobile/). I didn’t go looking specifically for Opera because it can be installed on nearly any phone. I also didn’t go looking for a [Brew MP](http://www.brewmp.com/) phone because Opera is the primary browser. Opera is already installed an a couple of the Nokia phones, I have it on my iPhone and I downloaded it to an Android phone.

I would like to support iPhone 4 with the double pixel ratio and am thinking of getting an iPod Touch to fill that gap. (Or maybe I’ll be bad just upgrade my iPhone.) Also, I’m unsure as to how much testing I should do on older versions of iOS.

[Samsung Bada](http://www.bada.com/) and [Nokia Maemo/MeeGo](http://maemo.nokia.com/) only have one device each so there isn’t a huge market share. I’ll follow them and see where they go, but I’m not too worried since they are both Webkit-based and Gecko-based respectively.

Another Webkit-based browser, [BlackBerry OS 6](http://us.blackberry.com/apps-software/blackberry6/), definitely needs to be supported, but the devices are still new and expensive, so I thought I would wait a while. Similarly, [Windows Phone 7](http://www.microsoft.com/windowsphone/en-us/default.aspx) needs to be supported but is very new and very expensive: also a waiter.

I thought about supporting older browsers, but decided it was a waste of my time since nobody in their right mind would surf the web on them anyways. I’m aware of the mobile Internet’s popularity in developing counties, but don’t really know what types of phones are being used and whether they are feature phones, smart phones, or anything about them except the [majority are Opera and Symbian](http://gs.statcounter.com/#mobile_browser-ww-yearly-2008-2010).

## Unlocking, Debranding, Flashing & Other Frustrations

I was lucky that all the phones I got in Canada worked over WiFi without a SIM card. Unfortunately the two phones I got from the United States did not.

The processes I describe below may seem simple, but it was my first time with all this stuff (and jargon) and it took me more than two frustrating hours, *full of swearing*, per phone, to get them functional.

### Sony Ericsson Xperia X10

When I received the phone it was locked to AT&T and completely locked out. I couldn’t get in to turn on WiFi, it would only allow emergency phone calls. I first tried [unlocking](http://unlocking.com) the phone but couldn’t get a code. I then looked around and found out about debranding, which yielded the results I wanted.

<dfn>Debranding</dfn> is the process of replacing the carrier’s custom firmware, AKA ‘flashing’, with the generic firmware supplied by the manufacturer. And it was the AT&T firmware restricting the phone’s use without a connection to AT&T’s network.

I basically had to [download a debranding kit](http://forum.xda-developers.com/showthread.php?t=825201) and replace the firmware on the phone with the supplied generic one to remove the restrictions. It was a little scary—and very hacky—but worked.

### HTC myTouch (Magic)

The HTC myTouch came a day after the major Xperia X10 frustrations but presented a different set of problems. When turning the phone on I was asked to sign in to my Google Account to set up the phone. I couldn’t skip the account sign in, the phone had no data plan, and there was no way to get WiFi turned on so I couldn’t get past this screen.

After doing some researching I discovered that I should have access to WiFi *and* should be able to skip the Google Account sign in, but T-Mobile’s firmware was restricting the phone and forcing a mobile data connection over their network.

Since I was successful at debranding the Xperia X10, I thought I would start there. Unfortunately I couldn’t find a straight forward process like I did for the X10, so I went back to unlocking.

<dfn>Unlocking</dfn> is the process of allowing the phone to work on other networks. The myTouch was locked to T-Mobile, but I thought that if I unlocked it I could stick in my iPhone’s SIM and use it’s data connection to get past the Google Account screen.

After putting the $15 unlock code in and adding the [APN network connection for Fido](http://androidforums.com/hero-support-troubleshooting/26867-setting-up-hero-fido.html), I got past the account screen. After taking the SIM out, all’s good.

## Next Steps

So, next I just need to figure out how to implement the mobile first approach on my web sites and how to support all the different platforms and screen sizes in a simple way. Off to the drawing board I go…

## Helpful Resources

- [Nokia Device Specifications](http://www.forum.nokia.com/Devices/Device_specifications/?filter=all)
- [Google Android Phones](http://www.google.com/phone/)
- [BlackBerry Product List](http://en.wikipedia.org/wiki/List_of_BlackBerry_products)
- [jQuery Mobile Graded Browser Support](http://jquerymobile.com/gbs/)
- [QuirksMode Mobile](http://quirksmode.org/mobile/)
- [QuirksMode Mobile Browsers](http://quirksmode.org/mobile/browsers.html)
- [John Resig: Testing Mobile Javascript](http://www.webdirections.org/resources/john-resig-testing-mobile-javascript/)
- [A List Apart: Smartphone Browser Landscape](http://www.alistapart.com/articles/smartphone-browser-landscape/)

---

## Updates

- **Nov 30, 2010**—Updated the total cost to include some customs fees and taxes.
- **Dec 3, 2010**—Added the section about unlocking and debranding. Added more customs fees to the total.
- **Dec 15, 2010**—Added some new links. Added the iPod Touch with iOS 3.
- **Dec 20, 2010**—Added Webkit versions.

