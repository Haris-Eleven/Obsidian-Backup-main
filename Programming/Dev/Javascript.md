> A language designed to add interactivity, dynamic behavior to webpages 
  Just-In-Time **(JIT)** compiled language 
# Promises
# Async/ Await
Async function always returns a promise, the final returned value is passed in the resolved value of the object
Await pauses the execution of the function until the Promise **resolves (or rejects)**.
```js
async function hello(){
console.log("hello");
}
```
# Reducer :
1. The `.reduce()` method in JavaScript is used to **reduce an array to a single value** by applying a **callback function** repeatedly to each element in the array

# CDN: (Content Delivery Network):
> A network of computers which deliver static assets like js, css, images, etc. 
> - CDN based module loading: Modules are hosted on a cdn 

# Import Maps:
> It is a map literally a map to specify where a particular import is 
```javascript
<script type="importmap">
{
  "imports": {
    "@excalidraw/excalidraw": "https://cdn.skypack.dev/@excalidraw/excalidraw"
  }
}
</script>

```