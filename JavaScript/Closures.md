## Closure
<i>A function along with it's lexical scope forms closure</i>

From MDN docs: 
- A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment)
- In other words, a closure gives you access to an outer function’s scope from an inner function
- In JavaScript, closures are created every time a function is created, at function creation time.

### Examples

Example -1 #

```javascript
    function x(){
        var a = 7;
        function k(){
            
        }
        function y(){
            var c = 9;
            console.log(a) // a is closure of x
            function z(){
                console.log(c); // c is closure of y
            }
            z();
        }
        return y;
    }

    var fnHolder = x();
    //......
    fnHolder();
```
Example -2 #

``` javascript
function x(){
    for(var i=1; i<=5; i++){
        function cb() {
            console.log(i); // i is closure of x function
        }
        setTimeout(cb, 300);
    }
}
x();
```

Example - 3 #

``` javascript
function x(){
    for(let i=1; i<=5; i++){
        function cb() {
            console.log(i); // but here i is not closure of x function
        }
        setTimeout(cb, 300);
    }
}

x();
```

Example - 4 #
```javascript
function x() {
  for (var i = 1; i <= 5; i++) {
    function close(x) {
      function cb() {
        console.log(x); // x is closure of close function
      }
      setTimeout(cb, 300);
    }
    close(i);
  }
}
x();
```