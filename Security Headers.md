Topic of talk at #web-directions-code-2024 by Stephen Rees-Carter from [[Valorin Security]]

[Security Header Testing Tool](https://securityheaders.com/) - Grading according to what security headers are enabled and correctly configured

Each of these is a browser-level security measure to prevent one or several types of attack vectors:
- [[Strict Transport Security]] - to prevent downgrade attacks (intercepting and leveraging non-SSL connections)
	- Optionally can include all subdomains
	- max-age sets the expiry for the browser requiring HTTPS 
	- [[HSTS Preloading]] can solve the problem with the initial connection needing to occur before this header is sent by the server (and thus having a single handshake maybe occurring over HTTP)
- [[X-Frame Options]] - dictates whether your site can be rendered within a frame, either outright **deny** or can restrict to **same origin**
- [[Content Type Options]] - sets how the browser will treat files from this source. Can configure to ensure anything labelled as a certain type is only used as that type
- [[Referrer Policy]] - controls what data is sent when an external link is followed, highly configurable
- [[Permissions Policy]] - dictates what API permissions (location, microphone/camera etc) will be allowed to be sought by the page (can disable any or all)
- [[Content Security Policy]] - dictates what will be loaded
- [[Sub-resource Integrity ]] - can use a hash to ensure a third-party resource has not been altered 
- [[Cookies]] - security options can be altered to change the way the broswer treats them:
	- Secure Flag - ensures the cookies are only transferred over HTTPS
	- HttpOnly - prevents access of the cookies by any JS on the page
	- SameSite - controls the behaviour of cookies when going between sites (can help prevent [[Cross-Site Forgery Attacks]])