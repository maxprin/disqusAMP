Hi there,

Thanks for your work on making Disqus AMP-friendly. I implemented it on technicalseo.com and here are the issues/suggestions that I have:

1-- I couldn't make it work without adding an overflow child element. It seems to be required as a fall back if AMP can't automatically load the iframe: https://github.com/ampproject/amphtml/blob/master/extensions/amp-iframe/amp-iframe.md#iframe-resizing
I also added frameborder=0 for design purposes.
My working code looks as follow:

```html
<amp-iframe width=600 height=140
            layout="responsive"
            sandbox="allow-scripts allow-same-origin allow-modals allow-popups"
            resizable
            frameborder="0"
            src="external_html_file">
<div overflow tabindex=0 role=button aria-label="Disqus Comments">Disqus Comments</div>
</amp-iframe>
```

2-- As specified in your instructions, the "external_html_file" MUST be hosted on a different domain, but it also MUST be hosted on a secure (HTTPS) domain. This might be challenging for most (having access to another secure domain, buying another SLL certificate, etc.). 
I am hosting the file on Github secure CDN: https://cdn.rawgit.com/maxxeight/disqusAMP/master/disqus-amp.html

3-- I tweaked the scripts within this file (also attached as a .txt) so all variables (shortname and canonical URL - where the comments live) can be passed through parameters in the iframe src URL 
src="https://cdn.rawgit.com/maxxeight/disqusAMP/master/disqus-amp.html?shortname=[disqus_shortname]&url=[canonical_url]"

=> this way, the external html file can be the same ALL Disqus users. This leads to my last suggestion: could you guys host the file for all users? :) So nobody is dependant of my Github account?

Note: I did not have to "Add the new domain [cdn.rawgit.com] as a Trusted Domain" in my Disqus settings for this implementation to work.

Here is a working AMP URL with all of the above in place: https://technicalseo.com/rank-serp/duplicate-content/amp.html

Thanks again and please let me know if you have any questions!

Max

disqus-amp.txt
