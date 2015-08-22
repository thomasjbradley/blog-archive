# The Web is Not Microsoft Word

**Rich text editors are all over the web, dumbing down users and proliferating WYSIWYG content. The following is a proposal for a semantic text editor, AKA a WYSIWYM editor.**

Rich text editors are taking over the web—they are in every application, every CMS, every blog engine and every web site. There are [many](http://ckeditor.com/) [different](http://tinymce.moxiecode.com/) [rich](http://developer.yahoo.com/yui/editor/) [text](http://nicedit.com/) [editors](http://dojocampus.org/explorer/#Dijit_Editor_Basic) that you can download and use in your web application. They are all excellently crafted and coded but have one major flaw: they are mimicking Microsoft Word.

Why are all the editors trying to be Microsoft Word? We have all seen the Microsoft Word [toolbar madness](http://www.codinghorror.com/blog/archives/000523.html). But have you noticed the [dutiful](http://tinymce.moxiecode.com/examples/full.php) [duplication](http://ckeditor.com/demo) in online editors. It is time we remind everyone, the web is not Microsoft Word.

## What’s Wrong With Rich Text Editors?

Well, nothing, if they are used in the right situation. And that situation is when emulating Microsoft Word *is the goal*, [Google Docs](http://docs.google.com), as an example. When editing content in Google Docs, the goal is not to create valid HTML mark up that *means* something but rather the goal is to create a document that looks a specific way and contains specific content.

### Too Much Concentration on Look and Not Semantics

When editing web content there are many variables that need to be taken into account, including: the limited tag set, search engine optimization, code simplification and of course the idea that we aren’t creating a *look* we are creating a *meaning*.

Most of the tools in current rich text editors prompt the user to create a specific look for their content with buttons like bold, italic, underline, strikethrough, alignment, font, colour, background colour, etc. But the look should not be controlled by the content editor. The look is controlled by the web site’s theme and the designer who created the theme. How many designers want content editors to change the colour, font or alignment of text? Oh, and why does underline even exist? Isn’t that only for links?

### Too Many Features and Over Generalization

Maybe this is just another Windows (generalized) vs. Unix (specialized) idea but most rich text editors offer too many options and are completely over generalized. All those options dilute what the actual goal is: to create and edit text based content. Not to insert shapes or tables or videos. It even seems like many rich text editors are trying to provide a substitute for Dreamweaver or FrontPage.

### Poor or No Education

Many rich text editors try to dumb down the web and allow users to bring their (poor) education of using Microsoft Word to the web. I firmly believe in educating users. Many users don’t understand how and why the web works and by using these rich text editors we are just perpetuating their lack of education. That needs to be changed and it only requires a little bit of education.

## My Proposal: A Semantic Text Editor

Instead of using rich text editors in places where they don’t belong we should start using semantic editors with the intent to educate users into thinking about making text that *means* something and delegate all the look related stuff to the designers.

A semantic text editor would have the same look and be used the same way but the toolbar buttons would be completely different. The toolbar buttons would directly represent HTML tags and not abstract the tags away to fit the Microsoft Word ideology. Users need to learn that they are creating meaning in their text not making it look a certain way.

### Proposed Toolbar Buttons

- <img src="{{"img2"|env}}/articles/web-not-word/a.gif" width="21" height="20" alt=""> `<a>` Create a link. Allow the user to add a URL and an optional title. (Lets not try to abstract away what a link is with globes and chain icons)
- <img src="{{"img2"|env}}/articles/web-not-word/em.gif" width="20" height="20" alt=""> `<em>` Emphasize the text.
- <img src="{{"img2"|env}}/articles/web-not-word/strong.gif" width="20" height="20" alt=""> `<strong>` Strongly emphasize the text.
- <img src="{{"img2"|env}}/articles/web-not-word/small.gif" width="20" height="20" alt=""> `<small>` Mark the text as fine print.
- <img src="{{"img2"|env}}/articles/web-not-word/abbr.gif" width="20" height="20" alt=""> `<abbr>` Mark the text as an abbreviation and add a definition.
- <img src="{{"img2"|env}}/articles/web-not-word/sub.gif" width="20" height="20" alt=""> `<sub>` Make the text subscript.
- <img src="{{"img2"|env}}/articles/web-not-word/sup.gif" width="20" height="20" alt=""> `<sup>` Make the text superscript.
- <img src="{{"img2"|env}}/articles/web-not-word/i.gif" width="20" height="20" alt=""> `<i>` Mark the text as being in an alternate voice (e.g. a thought, a technical term, a phrase in another language, etc).
- <img src="{{"img2"|env}}/articles/web-not-word/b.gif" width="20" height="20" alt=""> `<b>` Mark the text as a keyword.
- <img src="{{"img2"|env}}/articles/web-not-word/mark.gif" width="20" height="20" alt=""> `<mark>` Highlight the text for reference purposes.
- <img src="{{"img2"|env}}/articles/web-not-word/ins.gif" width="20" height="20" alt=""> `<ins>` Mark the text as being newly inserted.
- <img src="{{"img2"|env}}/articles/web-not-word/del.gif" width="20" height="20" alt=""> `<del>` Mark the text as being deleted.
- <img src="{{"img2"|env}}/articles/web-not-word/cite.gif" width="20" height="20" alt=""> `<cite>` Mark the text as being the title of a work (e.g. a book, a poem, a song, a film, a TV show, a game, etc).
- <img src="{{"img2"|env}}/articles/web-not-word/time.gif" width="20" height="20" alt=""> `<time>` Mark the text as being a time and get the user to add a date-time.

Each of the above toolbar buttons directly correspond to an HTML element. Paragraphs would be created from breaks in the text.

A couple other buttons could be included for `<code>` (computer code), `<var>` (a variable, either computer or math), `<samp>` (sample output from a computer program) and `<kbd>` (sample input for a computer program). But those would be for specialized applications, not for the general public.

You may have noticed that none of the buttons are recognizable from their Word counterparts. No more bold, or italic and definitely no more colour changing. Instead the goal is to teach users that they need to think about the meaning of the text, not the visual representation of the text.

### Remove the Extra Cruft

The semantic text editor would have one specialized task: editing body content. We should remove all the extra stuff: no more tables, no more graphics, no more videos—these tasks should be relegated to other specialized tools. We need a specialized tool that looks after generating tables. A specialized tool that looks after inserting videos. *Even* make a specialized tool that creates lists (we could then allow sorting and other modern thingies).

### What About Headings and Block Quotes?

Specialization. Headings could easily be integrated into the semantic text editor, but instead think of the semantic text editor as a single piece in a greater content building system (a body builder?). There could be specialized tools for headings, text content (semantic text editor), block quotes, tables, images and other page elements. The tools could be added to the body builder and rearranged more easily than Word would ever allow. Since the tools are specialized they would show only the options needed.

Instead of the users thinking of how the content looks in this kind of system, they should be more concerned about ordering and marking up their content properly—the look is taken care of by the designer.

### HTML5 Definitions

One caveat, of course, is that the semantic text editor relies on elements and the definitions of the elements as specified in [HTML5](http://www.w3.org/TR/html5/).

## WYSIWYM

First, let me define WYSIWYM. It very simply means: what you see is what you **mean**. I can’t say I was clever enough to come up with this myself. There is already a project that is thinking along the same lines that I am, [WYMEditor](http://www.wymeditor.org/), the only problem is they didn’t take the idea far enough.

The project still maintains *visual* icons taken from Microsoft Word—not *meaning* based icons. (What does a globe with the chain do?) And some of the demos show that other semantic elements can be added, but then users are exposed to the code.

The perfect solution would allow addition of all the semantic elements and completely hide the HTML code from the users.

Let’s push ourselves to abandon the current rich text editors and start implementing semantic text editors. We should be training our users for the web not adapting the web to our users.
