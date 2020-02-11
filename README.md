# JavaScript-concepts

## this
- Inside function: Window
- Inside method: Owner object
- Alone: Global Object
- In strict mode: undefined
- call, apply, bind - refers to any object
- In an event, this will point to the html element that received event


## Arrow function
- Syntactically compact alternative to regular function expression
- ```javascript params => ({foo: bar})```
- Reason for arrow function is need of shorter function and this

## Call, Apply and Bind (call() OR Function.prpototype.call())
- Call and apply invokes method while bind will return function.

Ex:
```javascript
var fun = function(name){
    console.log(this.greet +' '+ name)
}

var greetEng = {greet: 'Hello!'}

call - fun.call(fun, 'sree') // executes
apply - fun.apply(fun, ['sree']) // executes
bind - fun.bind(fun) // returns a function
```

## Event Deligation
- Instead of adding handler to all the elements, we will listen to the top most element we will target element by `event.target`

## Function expression and funcction declaration

## Data types
- Number
- BigInt
- String
- Boolean
- Null
- Undefined

- Object
- Function
- Array


## Throttling, debounce, polyfill for bind

## flattening object

## DeepClone 
```javascript
function deepClone(obj){
    let clonedObj;
    // To handle array
    if(obj && Array.isArray(obj)){
        clonedObj = [];
        obj.forEach(x => {
           clonedObj.push(typeof(x)==='object' ? deepClone(x) : x)
         })
    }
    // For objects
    else if(obj && typeof(obj)==='object') {
        clonedObj = {};
        Object.keys(obj).forEach(x => {
              clonedObj[x] = typeof(obj[x])=== 'object' ? deepClone(obj[x]): obj[x];
        })
    } else {
        // For prmitive types
       clonedObj = obj;
    }

return clonedObj;
}
```






