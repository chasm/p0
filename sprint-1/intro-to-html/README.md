# Introduction to HTML

## Learning objectives

- What HTML is
- What HTML is used for
- How HTML works
- The essentials of HTML elements and attributes
- A first look at Uniform Resource Locators (URLs)
- The importance of standards-compliant HTML

## HyperText Markup Language

HTML is the Hypertext Markup Language. It is what we use to "mark up" text, images, etc. for use on a Web page.

The purpose of HTML is to describe the <strong style="color:red">structure</strong>, <strong style="color:red">function</strong>, or <strong style="color:red">semantics</strong> (meaning) of an element of a Web page.

Let's take the name one word at a time, starting with the last word:

### Language

A **language**, in the world of computers, is similar to a human language. It has a **syntax**, a **vocabulary**, and a set of **idioms**. If those sound scary, don't worry. Computer languages are much simpler than human languages. It is possible to learn a programming language in a small fraction of the time it would take to learn even the easiest human language.

And on a basic level, HTML is one of the easiest languages to learn. It also forms the foundation of the World Wide Web. Both of these are good reasons to start our learning process with HTML.

### Markup

HTML is <strong style="color:red">not a programming language</strong>. Programming languages are used to create algorithms, which are logic processes for solving problems. One of the programming languages that we'll be using in this course is **JavaScript**.

A <strong style="color:red">Markup language</strong>, in contrast, is essentially a system for labeling things on the page. For example, if I want to indicate that a block of text is a paragraph, I could mark it up like this:

```html
<p>
  Vestibulum ac diam sit amet quam vehicula elementum sed
  sit amet dui. Donec rutrum congue leo eget malesuada.
  Sed porttitor lectus nibh. Quisque velit nisi, pretium
  ut lacinia in, elementum id enim. Praesent sapien massa,
  convallis a pellentesque nec, egestas non nisi.
</p>
```

<p style="padding:20px 40px">**Note:** The fake Latin text in this sample paragraph is known as **Lorem ipsum** from the first two words in the classic version of it. It is mangled Latin that has been used for hundred of years to provide meaningless text. We use this text as a placeholder when we want to focus on things *around* the text, rather than on what the text says or means. You will see Lorem ipsum text a lot. There are also many amusing variations on it, such a Pirate text.</p>

You can think of the `<p>` and `</p>` as defining the sides of a *box*, and the paragraph text as sitting inside that box. The <strong style="color:red">p</strong> is the **label** on the box, indicating that it holds a *paragraph*.

Similarly, we could mark up an unordered list of items like this:

```html
<ul>
  <li>I am the first item</li>
  <li>Hey, I'm the second item, but I'm trying hard to be first</li>
  <li>Sigh... I am the third and final item</li>
</ul>
```

When we see this on a Web page, the HTML "tags" are invisible, but the browser sees them and renders the *contents* of these HTML elements accordingly. In this instance, it will use a *bulleted list*:

<ul>
  <li>I am the first item</li>
  <li>Hey, I'm the second item, but I'm trying hard to be first</li>
  <li>Sigh... I am the third and final item</li>
</ul>

Here, the <strong style="color:red">ul</strong> is the label on the outer element, which is the *unordered list* (ul) itself. Then each *list item* (li) in the list is labeled with <strong style="color:red">li</strong>. Put another way, each list item is in a box labeled <strong style="color:red">li</strong>. We indicate this by putting an `<li>` in front of the box contents, and an `</li>` (not the / mark) at the end of the box contents.

Hence, a **markup** language.

### Hypertext

HTML is the **HyperText** Markup Language. What this means is that HTML was initially intended to create "hypermedia".

**Hypermedia** is a set of resources&mdash;documents, images, videos, etc.&mdash;that are linked to each other by "traversable" links. That means that I can follow a link from one resource to the next.

Some of these links are visible and user-controlled. I can follow them by taking some action, most often by "clicking" on them, which means to place the screen pointer over the link and then clicking the mouse button.

But our Web-enabled devices have become dramatically more varied and complex. I might also tab through the page until the link is "highlighted" (we say that it is in "focus"), and then press the Enter key on my keyboard.

That's so old fashioned! More likely, I'm now using a smart phone and I simply tap the screen. Or perhaps I just say the link name out loud and my computer obeys and follows the link. However it is accomplished, I can move through a network of resources&mdash;Web pages, videos, downloadable files, etc.&mdash;with ease.

*That* is <strong style="color:red">hypermedia</strong>, and it has changed the way we interact with the world and with each other in ways we are only beginning to understand. And it all started with HTML.

Some of the links on the page are hidden and are used by the browser automatically. For example, images are not usually embedded in the page. Instead, the page links to them. The browser automatically follows those links, retrieves the images, and inserts them into the page in place of the HTML `<img>` element.

#### Attributes

We can add more information to our box labels (HTML elements) by adding <strong style="color:red">attributes</strong> to those elements. This is like writing a bit more information on the box.

Attributes each have a <strong style="color:red">name</strong> and, usually, a <strong style="color:red">value</strong>.

The pattern for adding an attribute is:

```html
<tag name="value">content</tag>
```

Where <strong style="color:red">tag</strong> is the name of the HTML element (e.g., p, ul, li), <strong style="color:red">name</strong> is the name of the attribute, <strong style="color:red">value</strong> is its value, and <strong style="color:red">content</strong> is the content of the HTML element, if any.

So, how would we add an image to a Web page? Well, we'll link to it. So we need to have a URL for our image. The URL, or <strong style="color:red">Uniform Resource Locator</strong>, is a string of characters that we use as an *address* to tell our browser where on the Web to find that resource. Let's look at one:

#### Uniform Resource Locators (URLs)

The URL is made up of several parts, each of which tells the computer something about the resource. <strong style="color:red">We need URLs because they tell us where to find resources on the network.</strong>

**Protocol**

The first part of our URL is the <strong style="color:red">protocol</strong>. A protocol is a set of rules for how something is handled. For example, diplomats use protocols all the time for formalizing ways to negotiate with other diplomats. It can be as simple as a seating chart for an important dinner, or very complex.

In programming, protocols are used in a similar manner: they dictate *how things get done*. The protocal for the World Wide Web is the HyperText Transfer Protocol (HTTP), which, unsurprisingly, is a *protocol* to determine how to *transfer* *hypertext* resources. Funny how names often tell you something about the things they name.

We'll learn HTTP pretty thoroughly later, but for now we just need to know that the HTTP protocol is indicated in our URLs with the following:

```
http://
```

You've probably seen this before, no?

**Domain name**

After the protocol, we need to tell the computer what "domain" to contact. The domain is the place on the Internet where the domain owner "rules", just as a king or queen rules over a domain.

Domains are "virtual", which means that they *may* correspond to a particular machine, or they may not. It doesn't really matter. All that counts is that the owner of a domain controls everything that happens in that domain.

So, for example, the folks at Google own the "google" domain. So everything that happens in the <strong style="color:red">google</strong> domain happens behind

```
http://google
```

Or, more likely:

```
https://google

```

Where `https` is the *secure* hypertext transfer protocol, and encrypted way to transfer hypermedia resources. That's an advanced topic, so for now just choose whichever of `http` or `https` works.

**Top level domains (TLDs)**

All domain names are grouped into "top leve domains" or TLDs, the most popular of which is the "com" domain, used for *commercial* websites. As you must know, there are many other top level domains, including "org" (for non-profit organizations), "net" (for network-related sites), "edu" (for educational institutions), "mil" (for the military), "gov" (for government), etc.

And each country has its own TLD, such as "nz" for New Zealand, "ca" for Canada, and "us" for the United States.

In our Google example, the TLD is the classic "com":

```
https://google.com
```

After that, we get into the Google domain itself and the rest of our URL describes a *location* within that domain&mdash;the location of the resource we're after.

Every Web site has a "root" folder: this is the folder in which the rest of the Web site resides. In the old days of the Web, this was usually a literal folder with literal contents, so if you saw a URL such as `http://mysite.com/some/path/to/an/image.jpg`, it meant that in the root folder of the "mysite.com" domain, there was a "some" folder, which held a "path" folder, which, in turn, held a "to" folder with an "an" folder in it, and, finally, in the "an" folder there was an image file called "image.jpg".

These days, we most likely are using a "virtual" URL, which means that the **server** (the program that holds and serves the Web site to your browser) takes this virtual URL apart and then responds based on instructions we gave it. The actual folders and file might not even exist&mdash;perhaps they are created on the fly.

But for our purposes, we'll assume for the moment that the rest of the URL represents a set of folders and files such that `/` is the root folder which serves the <strong style="color:red">home page</strong>, and that other pages are served from folders beneath that one.

#### Putting  it all together to add an image to the page

Remember <strong style="color:red">attributes</strong>? Yeah, way back up there we were talking about how we can add attributes to our HTML elements to help our browser to display exactly what we want it to.

Well, to add an image to a page, we use an interactive HTML element called `<img>`. And we tell the browser where to find that image by adding the `src` attribute, which is short for "source URL". For example, if we wanted to insert [this image](http://static.pratique.fr/images/unsized/gr/grumpy-cat.jpg) into our Web page, we'd add this HTML element at the point in the page that we wanted the image to appear:

```html
<img src="http://static.pratique.fr/images/unsized/gr/grumpy-cat.jpg">
```

The `<img>` element doesn't have any content&mdash;it links to it instead&mdash;so we **don't** need a closing `</img>` tag.

And that's how HTML works. Easy, is it not?

## HTML don't get no respect

Perhaps because HTML is easy to grasp and easy to use (though trickier to use properly), many programmers don't give it much respect. On site after site, blog post after blog post, book after book, it is depressingly easy to find horrible examples of bad HTML.

What a shame. HTML is actually a far more complex and powerful language, in some ways, than any programming language. In fact, HTML and it's big brother XML can be used to create complex "ontologies" (systems of knowledge) that can be used by "inference engines" to help computers to better understand the world and the things in it.

In other words, HTML is at the root of a system&mdash;sometimes called the <strong style="color:red">Semantic Web</strong>&mdash;that allows computers to reason about the world. Another name for this is <strong style="color:red">artificial intelligence</strong> or <strong style="color:red">AI</strong>. Take that, JavaScript!

HTML is also very important for making resources available to people with widely different abilities, whatever those abilities might be, and regardless of whether they are permanent or temporary. For example, properly used, HTML can make Web pages easily accessible by screen reader applications, often used by those who can't see the page.

Both <strong style="color:red">accessibility to persons with disabilities</strong> and <strong style="color:red">usability</strong>&mdash;two related but different concepts&mdash;are heavily dependent upon proper, standards-compliant use of HTML. For this reason (and others), we will be focusing strongly on standards-compliant HTML throughout this course.

It's not just a matter of standards, however. <strong style="color:red">It's a matter of justice.</strong> And it makes the World Wide Web that much more usable and user-friendly for everyone.

## Check yourself

Make sure that you can answer the following questions.

1. What is a "markup" language and what do we use it for?
2. What is hypermedia?
3. What is an HTML element?
4. How do HTML attributes differ from HTML elements?
5. How do we label content with an HTML element?
6. How do we add HTML attributes to an HTML element?
7. What is a URL and why do we need URLs?
8. What is a protocol and why do we need them?
9. What is the name of the protocol we use to transfer hypertext resources across the Internet?
10. What is a domain name? Which part is the top level domain name (TLD)?
11. Why is standards-compliant HTML so important?

## Glossary

<dl>
  <dt>markup language</dt>
  <dd>
    A markup language is a set of tags and/or a set of rules for creating tags that can be embedded in digital text to provide additional information about the text in order to facilitate automated processing of it, including editing and formatting for display or printing. [<cite>[LINFO](http://www.linfo.org/markup_language.html)</cite>]
  </dd>
  <dt>hypertext and hypermedia</dt>
  <dd>
    <strong style="color:red">Hypertext</strong> is text which contains links to other texts. The term was coined by Ted Nelson around 1965. <strong style="color:red">HyperMedia</strong> is a term used for hypertext which is not constrained to be text: it can include graphics, video, and sound, for example. [<cite>[WhatIs](http://www.w3.org/WhatIs.html)</cite>]
  </dd>
  <dt>HTML</dt>
  <dd>
    <strong style="color:red">HyperText Markup Language</strong>, commonly referred to as HTML, is the standard markup language used to create web pages. Web browsers can read HTML files and render them into visible or audible web pages. [<cite>[Wikipedia](https://en.wikipedia.org/wiki/HTML)</cite>]
  </dd>
  <dt>HTML element</dt>
  <dd>
    An HTML <strong style="color:red">element</strong> is an individual component of an HTML document or web page, once this has been parsed into the Document Object Model. HTML is composed of a tree of HTML elements and other nodes, such as text nodes. Each element can have HTML attributes specified. [<cite>[Wikipedia](https://en.wikipedia.org/wiki/HTML_element)</cite>]
  </dd>
  <dt>HTML attribute</dt>
  <dd>
    An HTML <strong style="color:red">attribute</strong> is a modifier of an HTML element type. An attribute either modifies the default functionality of an element type or provides functionality to certain element types unable to function correctly without them. In HTML syntax, an attribute is added to an HTML start tag. [<cite>[Wikipedia](https://en.wikipedia.org/wiki/HTML_attribute)</cite>]
  </dd>
  <dt>HTML5</dt>
  <dd>
    HTML5 is a markup language used for structuring and presenting content on the World Wide Web. It was finalized, and published, on 28 October 2014 by the World Wide Web Consortium (W3C). This is the fifth revision of the HTML standard since the inception of the World Wide Web. [<cite>[Wikipedia](https://en.wikipedia.org/wiki/HTML5)</cite>]
  </dd>
  <dt>lorem ipsum</dt>
  <dd>
    In publishing and graphic design, lorem ipsum (derived from Latin dolorem ipsum, translated as "pain itself") is a filler text commonly used to demonstrate the graphic elements of a document or visual presentation. Replacing meaningful content with placeholder text allows viewers to focus on graphic aspects such as font, typography, and page layout without being distracted by the content. It also reduces the need for the designer to come up with meaningful text, as they can instead use quickly-generated lorem ipsum. [<cite>[Wikipedia](https://en.wikipedia.org/wiki/Lorem_ipsum)</cite>]
  </dd>
  <dt>protocol</dt>
  <dd>
    An agreed-upon format for transmitting data between two devices. [<cite>[webopedia](http://www.webopedia.com/TERM/P/protocol.html)</cite>]
  </dd>
  <dt>HTTP</dt>
  <dd>
    Short for <strong style="color:red">HyperText Transfer Protocol</strong>, HTTP is the underlying protocol used by the World Wide Web. HTTP defines how messages are formatted and transmitted, and what actions Web servers and browsers should take in response to various commands. For example, when you enter a URL in your browser, this actually sends an HTTP command to the Web server directing it to fetch and transmit the requested Web page. [<cite>[webopedia](http://www.webopedia.com/TERM/H/HTTP.html)</cite>]
  </dd>
  <dt>URL</dt>
  <dd>
    A <strong style="color:red">Uniform Resource Locator</strong>&mdash;commonly informally referred to as a web address&mdash;is a reference to a web resource that specifies its location on a computer network and a mechanism for retrieving it. A URL is a specific type of Uniform Resource Identifier (URI), although many people use the two terms interchangeably. [<cite>[Wikipedia](https://en.wikipedia.org/wiki/Uniform_resource_locator)</cite>]
  </dd>
  <dt>software standard</dt>
  <dd>
    A software standard is a standard, protocol, or other common format of a document, file, or data transfer accepted and used by one or more software developers while working on one or more than one computer programs. <strong style="color:red">Software standards enable interoperability between different programs created by different developers.</strong> [<cite>[Wikipedia](https://en.wikipedia.org/wiki/Software_standard)</cite>]
  </dd>
</dl>

## Resources

You can learn more with the following resources. You may wish to bookmark these so that you can come back to them as necessary.

- [The <abbr title="World Wide Web Consortium">W3C</abbr> HTML5 Standard](http://www.w3.org/TR/html5/)
- [Guide to HTML5 on <abbr title="Mozilla Developer's Network">MDN</abbr>](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)
- [The W3C Web Accessibility Initiative](http://www.w3.org/WAI/) (WAI)
- [<abbr title="Web Accessibility in Mind">WebAIM</abbr>](http://webaim.org/)
- [Usability 101](http://www.nngroup.com/articles/usability-101-introduction-to-usability/)
- [The Web Standards Project](http://www.webstandards.org/)
- [Lorem Ipsum Generators](http://mashable.com/2013/07/11/lorem-ipsum/)
