This allows you to retrieve parts of objects instead of the whole object

Most of the time, you want to retrieve the whole object, but not always:
- even if you filter an object at the client side, the whole object is retrieved.
- This service allows you to craft a **SQL-like statment to retrieve a portion of an object**, pre-filtered by s3
- this way you are only consuming the filtered portion

The architecture: 
![[Pasted image 20250116151307.webp]]
- in the normal, you are billed for all retrieval, even if the client is only using some
- in the select example, you are only ever sending what you need