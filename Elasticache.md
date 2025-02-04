This is an memory database for applications that require extremely high performance
- this data is temporary (as memory is ephemeral)

You can use Redis or Memcached as a service

>[!error] Exam
>Read heavy workloads with low latency requirements suit this
>Reduces data base workloads
>Can we used to store session data (serverless servers)
>
>THIS REQUIRES APPLICATION CHANGES TO IMPLEMENT, it isn't just drop in

![[Pasted image 20250130150918.webp]]

![[Pasted image 20250130151002.webp]]
- this allows you to move toward fault tolerant applications


![[Pasted image 20250130151201.webp]]
- note the Multi-AZ ability of Redis
- backups are also available in Redis