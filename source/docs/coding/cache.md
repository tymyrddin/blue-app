# Use cache securely

Web cache poisoning vulnerabilities come into play due to general flaws in the design of caches and/or its implementation in an application.

* Turn caching off (OR)
* If you *have* to use it (big site, many visitors)
  * Understand and restrict where caching is done. Cache static response, such as `.js`, `.css`, `.png` files, blog posts, or any page that is always identical. Make sure that an adversary can not trick the back-end server into retrieving their malicious version of a static resource.
  * Disable all headers which are not necessary for the website's functionality. Especially the Host header. Double-check whether which urls really need to be absolute. Instead use relative urls.
  * Do not exclude something from the cache key, rewrite the request. Avoid using user inputs (HTTP Headers) to be used as the cache key.
  * Do not accept fat GET requests. 
  * Some third-party technologies permit such fat GET requests by default. In general, disable caching by third party frameworks. Do caching at one point.
  * Patch client-side XSS vulnerabilities. Including those that seem not exploitable. They can become exploitable due to strange behaviours of the cache, so that even in the event of such a vulnerability, the user’s browser can’t be exploited.

## Related attack trees

* [Cache poisoning](attack-trees:docs/server/poison-cache)
* [HTTP Response splitting](attack-trees:docs/server/response-splitting)
* [Cross-site scripting (XSS)](attack-trees:docs/application/XSS)