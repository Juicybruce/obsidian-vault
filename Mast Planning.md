### Handover instructions

- organise and update nav menus + page IA (landing page children are being pulled in automatically)
  
- Landing page content should be moved into another child page, the template should only have brief intro at most
  
- update post type guides and delete the pages that are guides
  
- Facility type region taxonomy is currently hierarchical, we suggest scraping that moving all children into their parent region
  
- Test all existing forms etc, making sure the workflow has not changed (Is notices subscription handled manually?)
  
- The RSS/atom feed work has been done, but worth double checking all the geodata required is still coming through correctly
  
- The 'Region' post type, its being used in the geo json. Just double checking that is still intended to be in use

- show vestigial ACF fields in contact us page, explain how we will be removing that

- lets talk about getting a checklist of website functionality 



Meeting Notes
- title in ai search box to guide users
- look at the landing page scroll menu, it looks like the highlighted menu item in n + 1
- search box in page needs to be background white
- Sibling 'See also' is showing the current page
- pontoons come under marinas? Facilities taxonomies might need some tweaking 
- notices need the auto numbering to be applied
- add image field to each news item preview card
- related posts is showing the current post
- chrome bug on modals, images are not being constrained properly
- delete templates 'Centered' and 'Subscribe'
- style the existing blocks (fee's and forms specifically needs a look over)
  
- focal point plugin 
- I'd like the excerpts on landing page children preview
- get youtube videos embedded in facility preveiws
- mailoptin is being used
- look into culling images and media, there is a lot of stuff not being used](mast)
### External System Audit Meeting

**Notice to Mariners:**
- Campaign Monitor holds the templates for the email notifications that get sent out
- MailoptIn (WordPress plugin) triggers the sending of those emails to the subscriber lists

- subscription form on website covers:
	- list to notices to mariners all regions
	- normal newsletter
	- PWC Newsletter
NEED TO DO THE FORM ON THE NOTICES PAGE AND THE /subscribe form page

The lists otherwise come from
- service tas sign ups
- mast portal for masst clients

Request for notice to mariners form feeds into the notices post type creates a pending forms
- note that I've added the auto-numbering, check it works

Facebook syndication is somewhat deprecated, leave it but it isn't going to be used

**CCTV**

- There is an image link for the latest screenshot from the timelapsed CCTV from Sullivans cove
	- There isn't currently a page to put that image on, once there is I can populate it

- Is there any other CCTV stuff that needs to be ported over?

- there is a bunch of them (8 or so) not really provided to the public, but that could be something in the future 

**RSS/Atom Feeds**
- my understanding is that these feeds are consumed by another system that provides mariners very specific details on notices and warnings

Decky consumes these feeds and that is what is used by mariners
- Bill is going to check the feed and make sure it is working and is not malformed



Links in Circulation
- Bitly links etc
- this is part of standard redirects but I wanted to cover it

- service tas etc, their staff have online helpfiles that have links to our websites

provide documentation on how to do redirects


Quiz - Boating Practice Test

Always available at mast.tas.gov.au/services/
- served statically from an s3 bucket




BILL THINGS

- Rego check is reaching to MAST systems to check rego and mooring status
- Where is each of the SPA things? Calcs and mooring and rego
- might need to update the calculator systems in wordpress for launch
- there was a fee change to the calculator, make sure that is being used
- Make sure the quiz questions can be fetched in the same way as is currently done


### Final step checklist

- added Sullivans cove image to the top of the facility content
- Confirmed MailOptIn plugin handles subscription to campaign monitor lists when users submit either subscription form
- Confirm various other forms are functioning with their integrations

- Made an updated "Request a notice to Mariners" form. Important to note that we haven't changed the notice post type itself, so the form simply collects more data (and creates a pending notice as before). Please see my notes on the departures I had to make from the list of fields provided - see [[Notes on notice form submission fields]]

- I've made sure the banner content wysiwyg field properly visually splits paragraphs
- I've ensured the news page banner doesn't reference the first news item

- Gone through spreadsheet and made notes on those point that are content specific (i.e., the change can be made by your team when instructions are provided). Like how to add an accordion block, or change what order the cards appear