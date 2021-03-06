# Read: 04 - HTML Links, CSS Layout, JS Functions

## Creating Hyperlinks

Hyperlinks are really important — they are what makes the Web a web. This article shows the syntax required to make a link, and discusses link best practices.

Hyperlinks allow us to link documents to other documents or resources, link to specific parts of documents, or make apps available at a web address. Almost any web content can be converted to a link so that when clicked or otherwise activated the web browser goes to another web address (URL).

## Anatomy of a Link

A basic link is created by wrapping the text or other content, see Block level links, inside an <a> element and using the href attribute, also known as a Hypertext Reference, or target, that contains the web address.

<p>I'm creating a link to
<a href="https://www.mozilla.org/en-US/">the Mozilla homepage</a>.
</p>

Result: I'm creating a link to the Mozilla homepage.

## Adding supporting information with the title attribute

The title contains additional information about the link, such as which kind of information the page contains, or things to be aware of on the website.

<p>I'm creating a link to
<a href="https://www.mozilla.org/en-US/"
   title="The best place to find more information about Mozilla's
          mission and how to contribute">the Mozilla homepage</a>.
</p>

This gives us the following result and hovering over the link displays the title as a tooltip:

I'm creating a link to the Mozilla homepage.

### Block-level elements. If you have an image you want to make into a link, use the <a> element and reference the image file with the <img> element.

<a href="https://www.mozilla.org/en-US/">
  <img src="mozilla-image.png" alt="mozilla logo that links to the Mozilla homepage">
</a>

A URL, or Uniform Resource Locator 

### Creating Hyperlinks Directory.

The root of this directory structure is called creating-hyperlinks. When working locally with a website, you'll have one directory that contains the entire site. Inside the root, we have an index.html file and a contacts.html. In a real website, index.html would be our home page or landing page (a web page that serves as the entry point for a website or a particular section of a website.).

There are also two directories inside our root — pdfs and projects. These each have a single file inside them — a PDF (project-brief.pdf) and an index.html file, respectively. Note that you can have two index.html files in one project, as long as they're in different filesystem locations. The second index.html would perhaps be the main landing page for project-related information.

### Same directory: If you wanted to include a hyperlink inside index.html (the top level index.html) pointing to contacts.html, you would specify the filename that you want to link to, because it's in the same directory as the current file. The URL you would use is contacts.html:

<p>Want to contact a specific staff member?
Find details on our <a href="contacts.html">contacts page</a>.</p>

### Moving down into subdirectories: If you wanted to include a hyperlink inside index.html (the top level index.html) pointing to projects/index.html, you would need to go down into the projects directory before indicating the file you want to link to. This is done by specifying the directory's name, then a forward slash, then the name of the file. The URL you would use is projects/index.html:

<p>Visit my <a href="projects/index.html">project homepage</a>.</p>

### Moving back up into parent directories: If you wanted to include a hyperlink inside projects/index.html pointing to pdfs/project-brief.pdf, you'd have to go up a directory level, then back down into the pdf directory. To go up a directory, use two dots — .. — so the URL you would use is ../pdfs/project-brief.pdf:

<p>A link to my <a href="../pdfs/project-brief.pdf">project brief</a>.</p>

## Document fragments

It's possible to link to a specific part of an HTML document, known as a document fragment, rather than just to the top of the document. To do this you first have to assign an id attribute to the element you want to link to. It normally makes sense to link to a specific heading, so this would look something like the following:

<h2 id="Mailing_address">Mailing address</h2>

Then to link to that specific id, you'd include it at the end of the URL, preceded by a hash/pound symbol (#), for example:

<p>Want to write us a letter? Use our <a href="contacts.html#Mailing_address">mailing address</a>.</p>

## Absolute versus relative URLs

*absolute URL:* Points to a location defined by its absolute location on the web, including protocol and domain name. For example, if an index.html page is uploaded to a directory called projects that sits inside the root of a web server, and the website's domain is https://www.example.com, the page would be available at https://www.example.com/projects/index.html (or even just https://www.example.com/projects/, as most web servers just look for a landing page such as index.html to load if it isn't specified in the URL.)

*relative URL:* Points to a location that is relative to the file you are linking from, more like what we looked at in the previous section. For example, if we wanted to link from our example file at https://www.example.com/projects/index.html to a PDF file in the same directory, the URL would just be the filename — project-brief.pdf — no extra information needed. If the PDF was available in a subdirectory inside projects called pdfs, the relative link would be pdfs/project-brief.pdf (the equivalent absolute URL would be https://www.example.com/projects/pdfs/project-brief.pdf.)

A relative URL will point to different places depending on the actual location of the file you refer from — for example if we moved our index.html file out of the projects directory and into the root of the website (the top level, not in any directories), the pdfs/project-brief.pdf relative URL link inside it would now point to a file located at https://www.example.com/pdfs/project-brief.pdf, not a file located at https://www.example.com/projects/pdfs/project-brief.pdf.

Of course, the location of the project-brief.pdf file and pdfs folder won't suddenly change because you moved the index.html file — this would make your link point to the wrong place, so it wouldn't work if clicked on. You need to be careful!

## Link best practices

### Use clear link wording

Screen reader users like jumping around from link to link on the page, and reading links out of context.

Search engines use link text to index target files, so it is a good idea to include keywords in your link text to effectively describe what is being linked to.

Visual readers skim over the page rather than reading every word, and their eyes will be drawn to page features that stand out, like links. They will find descriptive link text useful.

Other tips:

Don't repeat the URL as part of the link text — URLs look ugly, and sound even uglier when a screen reader reads them out letter by letter.

Don't say "link" or "links to" in the link text — it's just noise. Screen readers tell people there's a link. Visual users will also know there's a link, because links are generally styled in a different color and underlined (this convention generally shouldn't be broken, as users are used to it).

Keep your link text as short as possible — this is helpful because screen readers need to interpret the entire link text.

Minimize instances where multiple copies of the same text are linked to different places. This can cause problems for screen reader users, if there's a list of links out of context that are labeled "click here", "click here", "click here".

## Linking to non-HTML resources — leave clear signposts

When linking to a resource that will be downloaded (like a PDF or Word document), streamed (like video or audio), or has another 
potentially unexpected effect (opens a popup window, or loads a Flash movie), you should add clear wording to reduce any confusion.

If you're on a low bandwidth connection, click a link, and then a multiple megabyte download starts unexpectedly.
If you don't have the Flash player installed, click a link, and then suddenly get taken to a page that requires Flash.

<p><a href="https://www.example.com/large-report.pdf">
  Download the sales report (PDF, 10MB)
</a></p>

<p><a href="https://www.example.com/video-stream/" target="_blank">
  Watch the video (stream opens in separate tab, HD quality)
</a></p>

<p><a href="https://www.example.com/car-game">
  Play the car game (requires Flash)
</a></p>


## Use the download attribute when linking to a download

When you are linking to a resource that's to be downloaded rather than opened in the browser, you can use the download attribute to provide a default save filename. Here's an example with a download link to the latest Windows version of Firefox:

<a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=en-US"
   download="firefox-latest-64bit-installer.exe">
  Download Latest Firefox for Windows (64-bit) (English, US)
</a>

<a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=en-US"
   download="firefox-latest-64bit-installer.exe">
  Download Latest Firefox for Windows (64-bit) (English, US)
</a>

## Creating a navigation menu

This is one common way in which a website is created — the same page structure is used on every page, including the same navigation menu, so when links are clicked it gives the impression that you are staying in the same place, and different content is being brought up.

You'll need to make local copies of the following four pages, all in the same directory. For a complete file list, see the navigation-menu-start directory:

index.html
projects.html
pictures.html
social.html

Add an unordered list in the indicated place on one page that includes the names of the pages to link to. A navigation menu is usually just a list of links, so this is semantically OK.
Change each page name into a link to that page.
Copy the navigation menu across to each page.
On each page, remove just the link to that same page — it's confusing and unnecessary for a page to include a link to itself. And, the lack of a link acts a good visual reminder of which page you are currently on.

## E-mail links

<a href="mailto:nowhere@mozilla.org">Send email to nowhere</a>

### Specifying details

<a href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&subject=The%20subject%20of%20the%20email&body=The%20body%20of%20the%20email">
  Send mail with cc, bcc, subject and body
</a>

To create a basic link, we wrap text or other content inside what element? <a>
The href attribute contains what information? Using the href attribute, also known as a Hypertext Reference, or target, that contains the web address.
What are some ways we can ensure links on our pages are accessible to all readers? To leave an attribute link

# CSS Layout

What is meant by “normal flow”?

Content fills the available inline space of the parent element containing it and grows along the block dimension to accommodate its content. It is the default set up.

What are a few differences between block-level and inline elements?

 *block level element's* content fills the available inline space of the parent element containing it and grows along the block dimension to accommodate its content. The size of Inline elements is just the size of their content. You can't set width or height on *inline elements*— they just sit inside the content of block level elements. If you want to control the size of an inline element in this manner, you need to set it to behave like a block level element (e.g., with display: block; or display: inline-block;, which mixes characteristics from both).
___ positioning is the default for every html element.
Name a few advantages to using absolute positioning on an element.

 git
What is a key difference between fixed positioning and absolute positioning?