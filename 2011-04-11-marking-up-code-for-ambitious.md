# Marking Up Code for the Ambitious

**Code markup in online content and documentation can be improved. Here’s a proposal for the ambitious semanticists out there.**

As web developers we write a lot of code, we also take the time to properly select the most semantically appropriate HTML elements for our content. When writing tutorials and articles with code, why don’t we also take the time to properly mark up our code samples in HTML?

Most developers take the route of using a Javascript syntax highlighter or using a server side solution, like [Pygments](http://pygments.org/). These aren’t bad solutions, in fact they are pretty great, but they just use a bunch of <code class="language-html">&lt;<b>span</b>&gt;</code> elements with classes to syntax highlight. We can do better, semantically.

## The Elements

We still need to use the trusty <code class="language-html">&lt;<b>pre</b>&gt;&lt;<b>code</b>&gt;</code> as used by the above mentioned scripts. But for the code inside, we can do so much better than meaningless <code class="language-html">&lt;<b>span</b>&gt;</code>s.

Looking at the HTML specification we have a bunch of elements that make sense within our code blocks:

- <code class="language-html">&lt;<a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/text-level-semantics.html#the-var-element" rel="external"><b>var</b></a>&gt;</code>: variables
- <code class="language-html">&lt;<a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/text-level-semantics.html#the-b-element" rel="external"><b>b</b></a>&gt;</code>: keywords; like built in functions and properties
- <code class="language-html">&lt;<a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/text-level-semantics.html#the-i-element" rel="external"><b>i</b></a>&gt;</code>: taxonomy, technical term, designation; like properties, methods, attributes
- <code class="language-html">&lt;<a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/text-level-semantics.html#the-small-element" rel="external"><b>small</b></a>&gt;</code>: fine print or comments
- <code class="language-html">&lt;<a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/edits.html#the-del-element" rel="external"><b>del</b></a>&gt;</code>: code that is removed
- <code class="language-html">&lt;<a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/edits.html#the-ins-element" rel="external"><b>ins</b></a>&gt;</code>: code that is added
- <code class="language-html">&lt;<a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/text-level-semantics.html#the-mark-element" rel="external"><b>mark</b></a>&gt;</code>: important, highlighted code
- <code class="language-html">&lt;<a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/text-level-semantics.html#the-samp-element" rel="external"><b>samp</b></a>&gt;</code>: computer output
- <code class="language-html">&lt;<a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/text-level-semantics.html#the-kbd-element" rel="external"><b>kbd</b></a>&gt;</code>: user input

And we still use the <code class="language-html">&lt;<a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/text-level-semantics.html#the-span-element" rel="external"><b>span</b></a>&gt;</code>, but only for things that have no meaning in the context, like a regular old string.

## Some Examples

Lets walk through some samples to see how to use these elements in our code samples.

### HTML

<strong>What you want to see:</strong><br><small>(view source to see it in practice)</small>

<div class="highlight">
<pre><code class="code-block language-html">&lt;<b>div</b> <i>class</i>=<span>"group"</span>&gt;
&lt;<b>h1</b>&gt;Sample HTML&lt;/<b>h1</b>&gt;
&lt;<b>p</b>&gt;Some super awesome content!&lt;/<b>p</b>&gt;
&lt;/<b>div</b>&gt;<small>&lt;!-- end group --&gt;</small></code></pre>
</div>

<strong>What HTML you would write:</strong>

<div class="highlight">
<pre><code class="code-block language-html"><i>&amp;lt;</i>&lt;<b>b</b>&gt;div&lt;/<b>b</b>&gt; &lt;<b>i</b>&gt;class&lt;/<b>i</b>&gt;=&lt;<b>span</b>&gt;"group"&lt;/<b>span</b>&gt;<i>&amp;gt;</i>
<i>&amp;lt;</i>&lt;<b>b</b>&gt;h1&lt;/<b>b</b>&gt;<i>&amp;gt;</i>Sample HTML<i>&amp;lt;</i>/&lt;<b>b</b>&gt;h1&lt;/<b>b</b>&gt;<i>&amp;gt;</i>
<i>&amp;lt;</i>&lt;<b>b</b>&gt;p&lt;/<b>b</b>&gt;<i>&amp;gt;</i>Some super awesome content!<i>&amp;lt;</i>/&lt;<b>b</b>&gt;p&lt;/<b>b</b>&gt;<i>&amp;gt;</i>
<i>&amp;lt;</i>/&lt;<b>b</b>&gt;div&lt;/<b>b</b>&gt;<i>&amp;gt;</i>&lt;<b>small</b>&gt;<i>&amp;lt;</i>!-- end group --<i>&amp;gt;</i>&lt;/<b>small</b>&gt;</code></pre>
</div>

So, from a semantics point of view, I believe the above code is more appropriate. The notable additions are:

- <code class="language-html">&lt;<b>b</b>&gt;</code> for wrapping around the HTML elements; semantically the elements are keywords, in their context.
- <code class="language-html">&lt;<b>i</b>&gt;</code> for wrapping attributes on the HTML elements; I suppose that attributes are a taxonomies or designations.
- <code class="language-html">&lt;<b>span</b>&gt;</code> for wrapping around strings in code, since the string really doesn’t have any meaning.
- <code class="language-html">&lt;<b>small</b>&gt;</code> for wrapping around comments.

## CSS

<strong>What you want to see:</strong><br><small>(view source to see it in practice)</small>

<div class="highlight">
<pre><code class="code-block language-css"><small>/* Sectioning Elements */</small>
<i>.group</i> {
  <b>background-image</b>: url(<span>"pattern.png"</span>);
  <b>border</b>: 1px <b>solid</b> #000;
}</code></pre>
</div>

<strong>What HTML you would write:</strong>

<div class="highlight">
<pre><code class="code-block language-html">&lt;<b>small</b>&gt;/* Sectioning Elements */&lt;/<b>small</b>&gt;
&lt;<b>i</b>&gt;.group&lt;/<b>i</b>&gt; {
  &lt;<b>b</b>&gt;background-image&lt;/<b>b</b>&gt;: url(&lt;<b>span</b>&gt;"pattern.png"&lt;/<b>span</b>&gt;);
  &lt;<b>b</b>&gt;border&lt;/<b>b</b>&gt;: 1px &lt;<b>b</b>&gt;solid&lt;/<b>b</b>&gt; #000;
}</code></pre>
</div>

The same sorta rules apply for CSS, <code class="language-html">&lt;<b>b</b>&gt;</code> for keywords, aka properties; <code class="language-html">&lt;<b>i</b>&gt;</code> for selectors; <code class="language-html">&lt;<b>span</b>&gt;</code> for strings; and, of course, <code class="language-html">&lt;<b>small</b>&gt;</code> for comments.

### Javascript

Let’s look at something a little more complex for Javascript, including additions and deletions and important parts.

<strong>What you want to see:</strong><br><small>(view source to see it in practice)</small>

<div class="highlight">
<pre><code class="code-block language-javascript"><b>document</b>.<i>getElementById</i>(<span>'foo'</span>).<i>addEventListener</i>(<span>'click'</span>, <b>function</b>(<var>evt</var>)
{
<b>var</b> <var>myMessage</var> = <span>'Hello World!'</span>;

<del><b>alert</b>(<var>myMessage</var>)</del>
<ins><mark><b>console</b>.<i>log</i>(<var>myMessage</var>)</mark></ins>
}, <b>false</b>)</code></pre>
</div>

<strong>What HTML you would write:</strong>

<div class="highlight">
<pre><code class="code-block language-html">&lt;<b>b</b>&gt;document&lt;/<b>b</b>&gt;.&lt;<b>i</b>&gt;getElementById&lt;/<b>i</b>&gt;(&lt;<b>span</b>&gt;'foo'&lt;/<b>span</b>&gt;).&lt;<b>i</b>&gt;addEventListener&lt;/<b>i</b>&gt;(&lt;<b>span</b>&gt;'click'&lt;/<b>span</b>&gt;, &lt;<b>b</b>&gt;function&lt;/<b>b</b>&gt;(&lt;<b>var</b>&gt;evt&lt;/<b>var</b>&gt;)
{
&lt;<b>b</b>&gt;var&lt;/<b>b</b>&gt; &lt;<b>var</b>&gt;myMessage&lt;/<b>var</b>&gt; = &lt;<b>span</b>&gt;'Hello World!'&lt;/<b>span</b>&gt;;

&lt;<b>del</b>&gt;&lt;<b>b</b>&gt;alert&lt;/<b>b</b>&gt;(&lt;<b>var</b>&gt;myMessage&lt;/<b>var</b>&gt;)&lt;/<b>del</b>&gt;
&lt;<b>ins</b>&gt;&lt;<b>mark</b>&gt;&lt;<b>b</b>&gt;console&lt;/<b>b</b>&gt;.&lt;<b>i</b>&gt;log&lt;/<b>i</b>&gt;(&lt;<b>var</b>&gt;myMessage&lt;/<b>var</b>&gt;)&lt;/<b>mark</b>&gt;&lt;/<b>ins</b>&gt;
}, &lt;<b>b</b>&gt;false&lt;/<b>b</b>&gt;)</code></pre>
</div>

A few notable additions are the use of <code class="language-html">&lt;<b>var</b>&gt;</code> for wrapping around variables and arguments. The example uses <code class="language-html">&lt;<b>b</b>&gt;</code> around Javascript keywords; for <code class="language-javascript"><b>document</b></code> and <code class="language-javascript"><b>console</b></code>, it may be more technically correct to wrap them in <code class="language-html">&lt;<b>var</b>&gt;</code> elements, but I like to reserve <code class="language-html">&lt;<b>var</b>&gt;</code> for variables and arguments I have created.

When marking up objects and their properties, I feel that it’s more appropriate to mark up the parent as a <code class="language-html">&lt;<b>b</b>&gt;</code> or <code class="language-html">&lt;<b>var</b>&gt;</code> and all the child properties/functions as <code class="language-html">&lt;<b>i</b>&gt;</code> elements, as in <code class="language-javascript"><b>document</b>.<i>getElementById</i>()</code>.

Since the above code example is kinda like a tutorial, I decided to show that <code class="language-html">&lt;<b>del</b>&gt;</code> and <code class="language-html">&lt;<b>ins</b>&gt;</code> can be used to demonstrate code that should be deleted and code that should be inserted.

Using the <code class="language-html">&lt;<b>mark</b>&gt;</code> element we can highlight as passage of code that is important to the current step in the tutorial.

### PHP

What about going even further by integrating documentation with our code samples by linking to further resources.

<strong>What you want to see:</strong><br><small>(view source to see it in practice)</small>

<div class="highlight">
<pre><code class="code-block language-php"><small>&lt;?php</small>

<var>$db</var> = <b>new</b> <a href="http://php.net/pdo" rel="external"><b>PDO</b></a>(<span>'mysql:dbname=mydb;host=localhost'</span>, <span>'root'</span>, <span>''</span>);
<var>$db</var>-><a href="http://php.net/pdo.exec" rel="external"><i>exec</i></a>(<span>'DELETE FROM mytable'</span>);</code></pre>
</div>

<strong>What HTML you would write:</strong>

<div class="highlight">
<pre><code class="code-block language-html">&lt;<b>small</b>&gt;<i>&amp;lt;</i>?php&lt;<b>small</b>&gt;

&lt;<b>var</b>&gt;$db&lt;/<b>var</b>&gt; = &lt;<b>b</b>&gt;new&lt;/<b>b</b>&gt; &lt;<b>a</b> <i>href</i>=<span>"http://php.net/pdo"</span>&gt;&lt;<b>b</b>&gt;PDO&lt;/<b>b</b>&gt;&lt;/<b>a</b>&gt;(&lt;<b>span</b>&gt;'mysql:dbname=mydb;host=localhost'&lt;/<b>span</b>&gt;, &lt;<b>span</b>&gt;'root'&lt;/<b>span</b>&gt;, &lt;<b>span</b>&gt;''&lt;/<b>span</b>&gt;);
&lt;<b>var</b>&gt;$db&lt;/<b>var</b>&gt;-<i>&amp;gt;</i>&lt;<b>a</b> <i>href</i>=<span>"http://php.net/pdo.exec"</span>&gt;&lt;<b>i</b>&gt;exec&lt;/<b>i</b>&gt;&lt;/<b>a</b>&gt;(&lt;<b>span</b>&gt;'DELETE FROM mytable'&lt;/<b>span</b>&gt;);</code></pre>
</div>

Since the above sample is teaching about PDO and <code class="language-php"><i>exec</i>()</code>, why not link those functions to the PHP documentation, then readers can jump into deeper material at their discretion.

### Terminal

I’m not going to cover using <code class="language-html">&lt;<b>samp</b>&gt;</code> and <code class="language-html">&lt;<b>kbd</b>&gt;</code> because the <a href="http://www.whatwg.org/specs/web-apps/current-work/multipage/text-level-semantics.html#the-samp-element" title="Exmaples of using the &lt;kbd&gt; and &lt;samp&gt; elements" rel="external">HTML spec has some great examples.</a>

## Defining the Language

There is a [great question on Stack Overflow](http://stackoverflow.com/questions/5134242/sematics-standards-and-using-the-lang-attribute-for-source-code-in-markup) about what is the most semantically appropriate way to define the programming language for the code. I’m a fan of using <code class="language-html"><i>@class</i></code>, like so:

<div class="highlight">
<pre><code class="code-block language-html">&lt;<b>pre</b>&gt;&lt;<b>code</b> <i>class</i>=<span>"language-html"</span>&gt;…&lt;/<b>code</b>&gt;&lt;/<b>pre</b>&gt;</code></pre>
</div>

## Why Bother?

Well, I recognize many developers are lazy. And I recognize that the automated solutions have extra benefits such as copy-friendly versions and line numbers, etc. But code seems to be one of those places in online content and documentation where markup can be improved. It seems that web developers spend time choosing appropriate elements for general content, then just dump the code onto the page. True craftsmen would sweat all the details.

Am I over-the-top semantic crazy? Likely. But semantics and code are what we do, lets spend a little more time on our documentation samples.
