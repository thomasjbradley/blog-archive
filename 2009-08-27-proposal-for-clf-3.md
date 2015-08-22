---
updated: 2011-12-23
---

# A Proposal for CLF 3.0

**All Canadian web developers have had a run-in with CLF and its frustrations. CLF 2.0 has a few issues—many less than CLF 1—that could be solved in the next version.**

## Good in Theory

The theory behind the [Government of Canada’s Common Look and Feel for the Internet (CLF)](http://www.tbs-sct.gc.ca/clf2-nsi2/index-eng.asp) is great: a set of standards and templates that all Government of Canada sites need to adhere to and use. One of the best things the Treasury Board did for CLF 2.0 was to consult local web professionals during development and it’s very apparent in the HTML/CSS code. The set-up, accessibility and standards in CLF are fantastic and I applaud GC for it… but nothing is perfect.

## Biggest Strength/Weakness

CLF’s biggest strength is also it’s biggest weakness: the templates. All GC web sites look the same! Yes, we as Canadians instantly know we are looking at a government site, but it could be a little more subtle and less restrictive. CLF 2 isn’t as strict as CLF 1 in the main content area of the site, allowing designers to show off some creativity. For informational sites allowing creativity in the content area works, but for web apps there still isn’t enough space.

## Creative CLF 2 Examples

I have wrangled up a few great examples that push the CLF envelope to the edge and could benefit from a more flexible CLF 3.0.

### [Service Canada](http://www.servicecanada.gc.ca/eng/home.shtml)

![]({{"img2"|env}}/articles/clf3/service-canada.jpg)

First up is [Service Canada](http://www.servicecanada.gc.ca/eng/home.shtml), which follows CLF to a tittle but has a few extra flourishes that sets it apart from other GC sites.

The most noticeable and refreshing aspect is the rounded corners on all the content boxes. Rounded corners can be too much sometimes but in the case of CLF it is a nice touch over the boxy feel of all the other CLF sites.

There is a lot of content on this site and the CLF template makes if feel very full. It’s nice to see that light colours were chosen, they give the site a slightly less stuffy feel.

It’s disappointing that the heaviest item on the page is the common menu bar. The common menu bar draws all the attention away from everything else on the page. Yes, it reminds us that we are on a GC site, but it’s too heavy and draws our eyes away from the content of the site.

Service Canada is a refreshing example of creativity in the CLF world. It looks great in CLF but could use more white space and some creativity to remove weight from the common menu bar.

### [Natural Sciences and Engineering Research Council of Canada](http://www.nserc-crsng.gc.ca/Index_eng.asp)

![Whoa, what’s wrong with the colour of the flag?]({{"img2"|env}}/articles/clf3/natural-sciences.jpg)

The [Natural Sciences and Engineering](http://www.nserc-crsng.gc.ca/Index_eng.asp) web site breaks the mould a little bit. Web 2.0 gradients are prominent all over the web site—maybe even a little too much—but it is nice to see something that looks different. All the page elements fit the template but have had a slight makeover.

The major difference from the downloadable templates is the masthead. The default CLF template has a common menu bar that is black with bold, white, left-aligned links; Natural Sciences menu bar is grey with regular weight, black, centre-aligned links. I don’t know if this change is ‘legal’ within CLF but it provides a simple variation from the template and helps lighten the masthead which would look too heavy in black.

Along with the colour difference the common menu has also been bumped down by the small colourful boxes. I suppose Natural Sciences did this to add some interest instead of using graphics in the banner.

A couple other notable features are the Javascript slideshow and the browser functionality duplicating toolbar. I am completely against the toolbar, being a firm believer of teaching users how to use their browsers instead of in page hacks.

The Natural Science web site pushes the envelope enough that is isn’t lost in all the other Government of Canada sites yet is still obviously associated with the government.

### [Canada’s Air Force Aircraft Micro-site](http://www.airforce.forces.gc.ca/v2/equip/ch148/index-eng.asp)

![Designed by my colleague, [Chrys Moll](http://www.linkedin.com/pub/chrys-moll/3/704/38b).]({{"img2"|env}}/articles/clf3/aircraft.jpg)

Finally an example that takes the customization of the content area to the extreme is the [aircraft micro-site](http://www.airforce.forces.gc.ca/v2/equip/ch148/index-eng.asp). You will find that the elements of the site still fit into the grid of CLF but look nothing like CLF. The left navigation is completely CLF but the content area has no indication of CLF.

The content area is styled like a paper folder with tabs. Since the site is information about all the aircraft in the air force’s fleet the metaphor is fitting. The surrounding CLF template detracts some of the impact of the paper folder style but the designer has done an excellent job combining the elements of CLF into a coherent presentation. The common menu, as an example, fits well into the design without looking too heavy.

If the micro-site was set free from its CLF prison the design could be pushed further—that is what my proposed CLF is attempting to accomplish.

<small>In the act of full disclosure: I was the front-end developer (while working at [gordongroup](http://gordongroup.com/)) on the aircraft micro-site when it was launched a few years ago; though I see it has been changed a little since then.</small>

## CLF’s Failure: Web Applications

The above examples are just the most outstanding examples of CLF web sites I could find, but the rest of the government web sites are full of [mundane repetition and strict adherence to CLF 2](http://canada.gc.ca/depts/major/depind-eng.html).

There is one class of web sites that could really benefit from having a more flexible CLF: web applications. Web-apps usually require more screen real estate and differing grids from what is proposed by the current CLF.

### [NRCan Library](http://catalogue.nrcan.gc.ca/opac/en-CA/skin/nrcan-rncan/xml/)

![]({{"img2"|env}}/articles/clf3/nrcan.jpg)

The [Natural Resources Canada Library](http://catalogue.nrcan.gc.ca/opac/en-CA/skin/nrcan-rncan/xml/) is currently going through the process of transferring their library system from an old proprietary system to the open-source [Evergreen](http://www.open-ils.org/) system.

This is a perfect example of where CLF isn’t appropriate. Evergreen is meant to be a liquid layout and it presents too much information (even when much of it is hidden) to squeeze into the CLF template. Though the final result is good looking and usable, it lacks a decent amount of whitespace and looks cluttered. The NRCan Library could really benefit from using my proposed CLF 3 templates.

<small>Again with the active disclosure thing: I was the developer who took Evergreen and crammed it into the CLF templates while working with [Wirespeak](http://www.wirespeak.com/).</small>

## The Proposal

Common Look and Feel 2.0 stepped in the right direction by enforcing web standards. My proposal for CLF isn’t to remove many of the standards restrictions that CLF imposes—in fact I am very happy those restrictions exist—just to allow a little more flexibility in the CLF templates for web-apps and sites that may want to get creative.

![The GC Omnibar.]({{"img2"|env}}/articles/clf3/omnibar.jpg)

Ok, so we are finally at the proposal: make the template a toolbar across the top of the page with the pertinent information. Still enforce web standards and accessibility but allow the site to have an individual design and layout (fixed, fluid or elastic—fixed width sites may still have a maximum width imposed by CLF). The Treasury Board could still provide templates similar to the current CLF that has a pre made grid for departments that don’t want/need to get creative. But for those designers who thrive on creativity CLF shouldn’t impose any major layout or design constraints except those based on web standards and accessibility practices (I’m looking at you Flash sites).

[Check out the example I mocked up.](/lab/clf3/)

You may notice that home and contact us are no longer part of the black common menu bar; these could be links that web sites are forced to add into their site navigation by CLF. I removed the link to <i>canada.gc.ca</i> because I felt the Canada word-mark has the same function and there is no point wasting space.

### Why is it Still Black?

I feel that black is the appropriate colour. Yes, it’s heavy, but the common menu bar has been black since CLF 1 and it fits with the branding of the government (all the street signs for government building have black bars). Also for those users who currently rely on the common menu bar the black reminds them that it still serves the same purpose but in a different location.

### Mega Drop-downs?

I considered having mega drop-downs integrated into the GC Omnibar (yes, that’s what I’m calling it) but in the end I wasn’t sure if that was a good solution. The help menu could benefit from mega drop-downs by providing some quick help topics and links.

### Integrated Global Search

A search field has been placed right into the omnibar replacing the search link. An interesting addition to this is providing a global search that returns results for the current GC site as well as results from all other government sites.

### Global History & Social Aspects

If the omnibar was a global include of some kind it would be interesting if it tracked government site surfing history. Maybe it could recommend good resources other people have voted for pertaining to what you are looking at.

### Strict Doctypes or HTML5

Another thing that would be nice for CLF is to not force developers to use XHTML. Just a strict doctype should be enforced, whether it be HTML or XHTML. If the Treasury Board is feeling adventurous the HTML5 doctype would also be a welcome addition.

## The GC Omnibar: Complete Integration

The new CLF could be more than just templates. It could be a combined government-wide system and action bar that integrates the sites visually and functionally. Currently all the government sites are individual entities and Google is your only aid when trying to find the information you want between all the silos. But with some creativity it could also have global integration and social aspects that could help users find information throughout the government sites. This is not a perfect solution but it would add a great deal of flexibility when building CLF web sites.

<small>On a fun side note, you’d think I was a football fan the amount of times I typed CFL instead of CLF in this post.</small>

## Some CLF Resources

- [Common Look and Feel](http://www.tbs-sct.gc.ca/clf2-nsi2/index-eng.asp)
- [CommonLookandFeel.ca](http://commonlookandfeel.ca/clf/)
- [CLF Drupal Theme](http://clf.openconcept.ca/)

---

## Updates

CLF 3 has been released, it’s been split into two sections:

- [Standard on Web Accessibility](http://www.tbs-sct.gc.ca/pol/doc-eng.aspx?section=text&id=23601),
- [Standard on Web Usability](http://www.tbs-sct.gc.ca/pol/doc-eng.aspx?section=text&id=24227),

and

- [Web Experience Toolkit](http://ircan-rican.gc.ca/projects/gcwwwtemplates).
