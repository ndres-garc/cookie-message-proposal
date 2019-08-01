# cookie-message (Proposal)
A description of how EU cookie law message should have been implemented (IMHO)


## Current status

- Cookie policy messages are implemented using Popups, toasts, alerts and other UI elements.


## Proposal

Cookie policy notice should be implemented using HMTL head meta tags.
These meta tags would be interpreted by the browser, which would be the responsible in developing the showing the appropiate UI.

### What are HTML meta tags?

> Meta elements are tags used in HTML and XHTML documents to provide structured metadata about a Web page. They are part of a web page's head section. Multiple Meta elements with different attributes can be used on the same page. Meta elements can be used to specify page description, keywords and any other metadata not provided through the other head elements and attributes.

> The meta element has two uses: either to emulate the use of an HTTP response header field, or to embed additional metadata within the HTML document. 

From: (https://en.wikipedia.org/wiki/Meta_element)

### How would look like the Cookie Policy meta tag?

Notify the browser about the intention of used cookies:

```
<meta privacy-policy="third-party">
```

Notify the browser about privacy policy document:

```
<meta privacy-clause="http://mydomain.com/about-cookies">
```

### Why a meta tag?
- Is programmatically testable
- It can be added programmatically
- You can easily add it depending on IP address only for EU (you can do that with UI too but not that easy)
- Some users (like me) can deactivate all cookie messages by a browser setting
- It doesn't depend on Website style to be effective (as I'm trying to show in (https://cookiemessagemonster.tumblr.com/))

As shown in cookiemessagemonster.tumblr.com, some messages are more effective than others. Legally, you can't be sure the user has read the warning if you use a wrong UI, which could lead to claims and sues. Moreover, using a different UI for each website in the world just confuses the user, misinforming instead of informing, the opposite of the objetive of the measure.

Do you know how websites know you have accepted the cookie warning?
Using cookies! The solution is contributing to the problem.

### Why depending on browser?
Browser could remember the cookie accepted list or don't remember at all if you choose to avoid messages.

I'm quite sure a vast majority users click on cookie notice messages automatically without reading them like me (and you).

Using this approach, you could configure your browser to allow only "third-party" cookies and don't be asked anymore about those, for example.
