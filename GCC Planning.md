
## Meeting Notes

- Just going over what has been implemented so far
- Next steps are Ionata moving into content, as well as polish and starting the feedback cycle with your team
- This stage is focused on functionality, there will be another designer-led pass for polishing (animations etc)
  
- I'll send the full list of these pages so you can take a look and see how it feels, and we can also start getting feedback on your workflow for the various post types etc
#### Pages / Post Types

- [Home page ](https://gcc.clients.ionata.com.au/)
  
- [Landing page example](https://gcc.clients.ionata.com.au/your-council/)
  
- [Standard Page Example](https://gcc.clients.ionata.com.au/for-residents/emergencies/stormwater-floods/)
- [Standard Page Example 2 (no banner image - waste collection block)](https://gcc.clients.ionata.com.au/for-residents/waste-management/)
- [Standard Page Example 3 (form block)](https://gcc.clients.ionata.com.au/for-residents/animals-pets/register-a-dog/)

- [Posts (News) Index Page](https://gcc.clients.ionata.com.au/for-residents/news/)
- [Example Post](https://gcc.clients.ionata.com.au/2026/03/have-your-say-in-glenorchys-future/)

- [Events Page](https://gcc.clients.ionata.com.au/our-city/events/)
- [Example Event](https://gcc.clients.ionata.com.au/event/variety-carols-by-candlelight-2025/)

- [Councilors Page](https://gcc.clients.ionata.com.au/your-council/currently-elected/elected-members/)

- [Jobs Page](https://gcc.clients.ionata.com.au/your-council/careers/careers-with-council/)

- [Documents & Publications](https://gcc.clients.ionata.com.au/your-council/documents-publications/)

- [Meetings Page](https://gcc.clients.ionata.com.au/your-council/meetings/)

- [Facilities Page](https://gcc.clients.ionata.com.au/our-services/facilities/)
- [Single Facility Example](https://gcc.clients.ionata.com.au/facility/moonah-arts-centre/)

- [Works and Projects](https://gcc.clients.ionata.com.au/for-business/works/)
- [Single Work Example](https://gcc.clients.ionata.com.au/works/stormwater-improvement-works/)

- [Plans Page](https://gcc.clients.ionata.com.au/for-business/planning/advertised-plans)
- [Single Plan](https://gcc.clients.ionata.com.au/plan/planning-scheme-amendment-and-combined-planning-permit-plam-24-02/)

- [Glossary Page](https://gcc.clients.ionata.com.au/a-z-glossary)


#### To check:
- We are waiting on some comms from the finance team on how we are handling payments via forms. Currently that is via Bpoint / Bpay, but my understanding was some thought of expanding this
- Also I have not yet implemented the 'History' template, I believe we are just waiting on the go ahead, so let us know


### TO DO

- More complex form handling
	- Gravity forms repeaters (say for adding multiple dogs to a register dog form). Couple of different solutions here, could use the [Repeater API](https://docs.gravityforms.com/repeater-fields/), or the [Nested Forms Addon](https://gravitywiz.com/documentation/gravity-forms-nested-forms/) from Gravity wiz
	- Finance approvals?
- mobile styles need a pass
- contact us page has a card block that needs looking at
- make sure SEO primary type is being used everywhere
- Do search replace on database for ddev links -> staging links
- handle facility external link
- quick exit on sensitive pages
- CURRENTLY CLOSED banner on facilities
- accessibility key focus because we will not use UserWay (do a check on all accessibility - claude skill perhaps?)

katya.moss@gcc.tas.gov.au
andrea.marquardt@gcc.tas.gov.au
bonnie.millington@gcc.tas.gov.au
natasha.barber@gcc.tas.gov.au