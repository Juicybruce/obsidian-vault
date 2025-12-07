Pages templates:
- Home - Fields
	- Banner (image/video - animation/logo)
	- Introduction (color, style, content and links)
	- Feature section (feature item + other items)
	- Sliders (pull in a specific event type)
	- Gallery section (can be single or multiple)
	- CTA
	- More Events section 
- [Landing Page ](https://rosnyfarm.com.au/wp/wp-admin/post.php?post=157&action=edit)
	- Repeating sections (title, image, content, buttons)
- Events (landing page for all events)
	- preselected type (for the search / filter section) - see other pages using the same template with another type
		- all events page shows these types in the filter
	- featured section as on homepage
	- Archiving of events is done of the date fields on a schedule and on save
- [Festival](https://rosnyfarm.com.au/cjf-presents/)
	- This template links closely with events and should be used as the overarching 'super-event' page, eg, you don't have a CJF Presents **event**, you have page with the template festival, all linked via the 'Festival' taxonomy on events
	- The sections are the same as home otherwise

Venue
- content (custom gutenburg blocks)
- Fields
	- Pretty Self-Explanatory (but they do feed into the events that are linked to them)
- Taxonomy
	- Accessibility (this also feeds into events linked to this )

Event Post Type
- The content blocks (custom gutenburg blocks)
	- gallery (images will show a caption if they are added to the media itself)
	- wide content - breaks to full width, you can put other blocks in it. DO NOT NEST THESE. Note how they interact with sidebars
		- use the parent select option to grab the parent block to edit that
  
- Fields
	- Display Title
	- featured video - shows on hover on preview
	- Banner
	- Date & Times - note the repeater and WHY we have the repeater (custom date filtering). Also note that events with a properly set up repeater will show EACH instance within a custom date range that is searched
	- Connect - These fields connect this event with the venue it is hosted at. You can either inherit the contact details and accessibility from your venue selected, or override them
	- Downloads - links that will appear in the sidebar
	- Additional info - extra sidebar content wherever it is needed (via the priority field)
	- CTA
	- custom mouse follower - for the preview
- Taxonomies
	- Type - Core top-level category, the one that is used to populate sliders on the home page etc
	- Category - more specific category, used in filtering by the end user etc
	- Festival - This attaches an event to a festival that has been made
	- Accessibility - similar to venues, but not inherently attached to it