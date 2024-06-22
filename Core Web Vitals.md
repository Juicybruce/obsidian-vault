Key metrics for #web-directions-code-2024 talk by Ben Schwarz from [[Calibre]] (a toolset to monitor and improve web performance)

The key 3 metrics are:
- Largest Contentful Paint (LCP) - which is the time taken to render the largest piece of content on the page from first load
- Interaction to Next Paint (INP) - how long interactions on the page block the main JS thread (preventing further interaction and causing degraded user experiences)
- Layout Shifts - how much the content shifts as elements are loaded in

Google uses chrome to gather this data from its users on the the fly and will report the scores of any 'public' and 'reasonably popular' sites - CrUX data

Several ways to improve each metrics score, eg:
- LCP
	- Better compression - [[zstandard]] / [[brotli]] over [[gzip]]
	- more modern and optimised image formats: AVIF / Webp over JPEG
	- Utilising CDNs to reduce network latency costs
- INP
	- break up event handlers
	- don't wait on network requests and block the thread
	- utilise web-vitals-js package to audit
- Layout Shift
	- Audit using the  Layout Shift Regions in the Chrome tools
	- utilise font-display: optional to abort slow fetches of web-fonts
	- utilise [[Web Fonts]] fallback techniques to ensure the system font closely matches the loaded font so there isnt a shift when the load completes
	- preload fonts

[HTTP Archive - Core Web Vitals Technology Report](https://lookerstudio.google.com/reporting/55bc8fad-44c2-4280-aa0b-5f3f0cd3d2be/page/M6ZPC) - Check the performance of various web technologies by querying CrUX results 


#learning/to-explore 
