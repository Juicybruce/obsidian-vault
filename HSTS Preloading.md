You can [submit your domain ](https://hstspreload.org) to a list which is then incorporated into the browsers directly. 

This means when accessing your server, the client browser *already knows* that the server should be accessed only via HTTPS, and not to attempt a non-secure connection

Usually, the initial connection to the server would first be over HTTP, only excluding this once the [[Strict Transport Security]] headers were received