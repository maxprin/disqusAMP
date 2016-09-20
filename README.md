# disqusAMP
Disqus comments for AMP

Based on Disqus AMP Install instruction: https://github.com/disqus/disqus-install-examples/blob/master/google-amp/README.md

<h2>How to install:</h2>

1. Refer to the `amp-frame` [documentation](https://www.ampproject.org/docs/reference/extended/amp-iframe.html) and add the required `amp-iframe` script to your document's `<head>`. :
    
    ```html
    <script async custom-element="amp-iframe" src="https://cdn.ampproject.org/v0/amp-iframe-0.1.js"></script>

    ```

2. Place the following `<amp-iframe>` element anywhere within the <body> of your AMP page. It will likely make sense to place it at the end of your article content, where ever you would your audience should engage further after reading.

    ```html
    <amp-iframe width=600 height=140
                layout="responsive"
                sandbox="allow-scripts allow-same-origin allow-modals allow-popups"
                resizable
                src="https://cdn.rawgit.com/maxxeight/disqusAMP/master/disqus-amp.html?shortname=[disqus_shortname]&url=[canonical_url]">
    <div overflow tabindex=0 role=button aria-label="Disqus Comments">Disqus Comments</div>            
    </amp-iframe>
    ```
3. Replace `[disqus_shortname]` by your Disqus shortname and `[canonical_url]` by the canonical/non-AMP URL.    
