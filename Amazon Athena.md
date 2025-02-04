This is a service that provides severless interactive querying service 
- you can do ad-hoc queries against data stored in s3 etc

It uses **schema-on-read**, which translates unmodified source data into a schema that makes it relational-like when read.
- the **original data** does not change

![[Pasted image 20250130145907.webp]]

>[!error] Exam
>This service has **no infrastructure** and the schema is ad-hoc
>
>This is really useful for data where you **don't want to transform the data being read**
>
>Very cost-effective 
>
>Very useful for querying **AWS logs**, **Glue Data Catalog** and **Web Server Logs**

