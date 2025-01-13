>[!error] This will almost certainly be on the exam

Versioning is disabled by default
- you can **enable it**
- you CANNOT **disable it once enabled**
- You can, however, **suspend versioning**, and reenable it later
![[Pasted image 20250110114928.webp|498]]
>[!error] this state changing will often have trick questions on the exam

Versioning allows you to store multiple versions of the same object. 

When you enable versioning, objects will gain an **ID** as well as their unique **KEY**. The key is the identifier of the object itself. the ID identifies the version of the object
- if changes occur to an object, a new version will be generate with a new ID

The latest or current version is always retrieved for an object if the object is requested, but you can **specify** the ID to get an older version 

>[!tip] Deletion 
>When you **delete** a version controlled object, AWS will simply add a 'delete marker' for that object.
>
>If you specify a specific object version, that object version WILL BE DELETED
>![[Pasted image 20250110115531.webp]]

>[!note] Important notes
>- Versioning cannot be switched off, only suspended
>- All object versions take up an enormous amount of space, and you are billed for all the extra versions
>- suspending does not removed any versions that were made while the versioning was enabled 


### MFA Delete

This setting makes a MFA token required to change **versioning state** (enabled/suspended) AND to delete versions

The way this is handled is to pass the Serial Number of your MFA + the code it generates with the API call



