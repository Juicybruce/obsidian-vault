- prepend /wp/ to the admin paths
- Isn't using posts
- pages are largely just the default template which has:
	- banner
	- flexible content blocks
- The other two templates are used on single pages:
	- fire danger rating maps - https://www-test.fire.tas.gov.au/fire-danger-rating/summary/. For the lists, maps and detailed tables etc
	- Permit map - for the fire bans and permits map page
- Flexible content is used for all content, each block provides a different layout and data scheme for filling it out.
	- All of them should use the consistent animations etc
	- Their placement order is the order in which they are rendered on the page
- Menus are mostly handed in the site options section
	- some of them are handled in the usual menu place (the footer menus are both here)

>[!error] There are routing problems for new pages
>If you add a new page:
>- Ionata needs to add the url to our CDN routing or the **public** wont see it
>- TFS needs to add the url to their internal F5 router or you wont **internally** see it

Ruth - ruth.tauti@fire.tas.gov.au
Esther - esther.fletcherjones@fire.tas.gov.au
Jayne - jayne.dobie@fire.tas.gov.au