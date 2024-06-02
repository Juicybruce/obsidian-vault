These are two different techniques for controlling how often we allow a function to be called over time


> [!warning] DOM Events
> Given how often events are able to be triggered, tying them directly to a function call can be inefficient or resource intensive
> 
> For example in 2014, Twitter has massive slowdown for some users, investigation revealed that a scroll event callback was responsible, as scroll events can trigger as much as 100 times a second. See John Resig's [blog post about the issue here](https://johnresig.com/blog/learning-from-twitter/)

#### [[Debouncing]]
#### [[Throttling]]

When to use each?

Use **debounce** when you want to *eventually* react to a frequent event, but don't necessarily need to invoke immediately, but rather want to react to the end state of the interaction
- just always need to keep in mind the delay

Use throttling when you *consistently*  want to react to a frequent event, but still limit for resource reasons 

### Example libraries

[[VueUse]] has several uses of both throttle and debounce for use within the [[Vue]] framework (such as [refDebounced](https://vueuse.org/shared/refDebounced/#refdebounced) or [watchThrottled](https://vueuse.org/shared/watchThrottled/#watchthrottled))

[[Lodash]] also has both the [\_.debounce](https://lodash.com/docs/4.17.15#debounce) and the [\_.throttle](https://lodash.com/docs/4.17.15#throttle) method
### Common Problems

The most common issue for either of these techniques is misuse. It is important to note that when you debounce or throttle a function call, you must then **reference the returned debounced/throttled** method in your event handler.

A common mistake is to simply wrap your function callback in a debounce method:
```js
button.addEventListener('click', function handleButtonClick() {
  return debounce(throwBall, 500)
})
```
This might *look* correct, but you are actually redeclaring the debounced method each click. The **correct** approach is to debounce the handler function
```js
button.addEventListener(
  'click',
  debounce(function handleButtonClick() {
    return throwBall()
  }, 500)
)
```


