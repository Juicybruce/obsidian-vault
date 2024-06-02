This concept comes from electrical engineering, where essentially a component will 'coalesce several temporally close signals into one'. see [original debounce blog post](http://unscriptable.com/2009/03/20/debouncing-javascript-methods/).

Debouncing is similar to throttling in that we are reducing the number of signals sent over time, but is very precise in ensuring a **single signal** is sent for an event which might happen **many times in a detection period**

A critical point is that if the event is happening often enough that it occurs at least once in every detection period, **the signal will never be sent**. The 'bouncing' hasn't stopped.


> [!NOTE] Trailing vs Leading edge
> A debounced event will usually *wait* before sending its signal (hence why it will not send if the event fires enough). This is called trailing edge invocation, where the signal will be sent after the requested delay has been reached without an event
> 
> However, **leading edge** invocation is usually an option in implementations, which will trigger on the first signal, then no more until after the delay has elapsed without signals. 
> 
> Some implementations do allow **both options to be true**, which will invoke at both the beginning and end of the delay (if multiple signals are debounced). 
> 
> Neither method guarantees the invocation will happen regularly (assuming continuous input during delay), but leading edge will at least fire once

##### Use Cases

###### Resize/scroll Events
- These events will trigger hundreds of times during user interaction and we want the function to handle this event to be invoked when they are **finished with their interaction** and not too often. 
###### Ajax or other calls on a search input
We want to fetch from the DB for responsive search functionality, but we want to limit calls. Best to wait until the **user has stopped typing**

###### Batching updates for a server
If many update calls are being fired, we can use debounce to group them into a single update to send to the server