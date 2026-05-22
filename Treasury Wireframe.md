
### Tim notes 21/05

- document library
	- document post type (title, description, file upload, publication date)
	- taxonomies (types and categories)
	- document block (essentially a download link to document) - look to ssttas 'related documents'
	- 
### Meeting notes
- where to login
- go through home + Landing page
- go through flexible content
- banner fields
- default page template (blocks etc)
- page navigation and structure (page sidebar)
- menus, how they work
- site options
- users, how to add (network AND per site)
	- roles necessary and their 'capabilities'
		-


content + image position styling
toggle for the page nav (h2's)
SSO implementation
admins for creating and editing
- editors for editing only
- extra role for 'reviewing', optionally the editor can submit a 'review' 
	- can this be set by the editor themselves (a pull request vs unreviewed publication vs a page that is ALWAYS reviewed)
	- the details of this (notifications of review requests, whether reviewers make edits or reject etc are TBD)
Can we have a log of recently edited pages
Can we restrict to logged in users only while in staging
how are non-breaking dash and spaces handled in wysiwygs AND text boxes (VERY important to treasury people haha)


Willameena.Kincaid@treasury.tas.gov.au
sebastian.roberts@treasury.tas.gov.au

### Build notes
muti site - chat with Benjamin
- the sub sites are a little big for their boots (they want to be distinctive)
- Roles, they want specific roles, they want SSO 

header
- icon on all
- title on multi sites 

Banner
- CTA with image
- rbeadcrumb added on landing page
- hasa boxed image to sidebar width match

Whole bunch of flex content layouts
- 2/3 column section
- cards with links
- preview section  / preview card
- content + links
- image + content

alternating grey/white backgrounds

'economic snapshot' save til last, the 'images' could be stat snap show tiles somehow

Single page template
- in page nav at the top (toggleable via field)
- side nav
	- top level is ancestor without parent
	- singlings/ aunts uncles children

Menu nav
- dropdown primary menu item is NOT a link, it just opens the fold out menu
	- top level title is a link

Make sure accessibility (focus style)

### Variables etc (Tim Chat)

the theme colour, will it just be a single primary? I'll start with just declaring a 'Theme color' variable we can use around the place, but we will have to consider if we want it hooking into bootstrap etc

Mitchell had mentioned making some new css variables, named for their actual use:
- content section padding
- banner padding
- grid gap
- etc
This would be rather than relying on the various ones we have at the moment (gap-xs/xl)
