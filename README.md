# javascript-core-concepts

## Closure
Many JavaScript concepts, like Closure, Event loops and Generators etc., are not one-line concepts for any beginner. I suggest watching videos to see each step in action to understand them.

Understanding Closure is multi-step activity:
1. Know the definition of it.
2. See Closure in the browser console
3. know the use cases of it.


### 1. Definition:
In Simple words, Closure gives you access to the parent function's scope from an inner function. Closures are created at the time of the creation of the function.


### 2. Closure in Browser console:
Refer screenshot attached.
![Closure](https://media-exp1.licdn.com/dms/image/D562CAQGsJlkbkzLatQ/comment-image-shrink_8192_1280/0/1661308500573?e=1661914800&v=beta&t=zY5IBaMdBq-hL0Lee2rcHnOExUytNsxemZUkQs8uHKI)


### 3. Usecases:
- suppose you want to count no of times a button is clicked; closure is the best choice.
- Implement Throttling and Debounce.
- Currying
- Memorize
- Maintaining state in the async world
- Functions like once
- setTimeouts
- Iterators
- Carousel


### References:
 https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures by MDN \
 https://www.youtube.com/watch?v=qikxEIxsXco&t=1102s by Akshay Saini \
 https://stackoverflow.com/a/50655259/1708333 \
 https://stackoverflow.com/a/39045098/1708333 




## Virtual DOM 

It is more expensive to find a node in DOM and manipulate it in SPA websites. Therefore React was introduced with the concept of Virtual DOM.

Although this concept of Virtual DOM is not new: https://github.com/Matt-Esch/virtual-dom.


VDOM strategically updates DOM without redrawing all the nodes in a single-page application. Finding a node in a tree structure is easy, but the DOM tree for a SPA app can be drastically huge. Finding and updating a node in case of an event is not time efficient.

VDOM solves this problem by creating a high-level abstraction of actual dom. The VDOM is a high-level lightweight in-memory tree representation of the virtual DOM.



## Event Loop
we can't discuss event loop in separation from the stack, so:

JS has three "stacks":

1. standard stack for all synchronous calls (one function calls another, etc)
2. microtask queue (or job queue or microtask stack) for all async operations with higher priority (process.nextTick, Promises, Object.observe, MutationObserver). When CPU is working on finishing up some operation like Promise or mutation observer and not sleeping.
3. macrotask queue (or event queue, task queue, macrotask queue) for all async operations with lower priority (setTimeout, setInterval, setImmediate, requestAnimationFrame, I/O, UI rendering).  When CPU is sleeping and not finishing up some operation like Promise or mutation observer.

### Question:

console.log(1);

setTimeout(() => console.log(2));

Promise.resolve().then(() => console.log(3));

Promise.resolve().then(() => setTimeout(() => console.log(4)));

Promise.resolve().then(() => console.log(5));

setTimeout(() => console.log(6));

console.log(7);

### Answer:
1, 7, 3, 5, 2, 6, 4

### References: 
https://javascript.info/event-loop
https://stackoverflow.com/a/60210808/1708333
