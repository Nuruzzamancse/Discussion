## Lexical scope
<i>Lexical scope means that in a nested group of functions, <b>the inner functions have access to the variables and other resources of their parent scope.</b>

This means that the child's functions are lexically bound to the execution context of their parents.

Lexical scope is sometimes also referred to as static scope.
```javascript
function grandfather() {
    var name = 'Hammad';
    // 'likes' is not accessible here
    function parent() {
        // 'name' is accessible here
        // 'likes' is not accessible here
        function child() {
            // Innermost level of the scope chain
            // 'name' is also accessible here
            var likes = 'Coding';
        }
    }
}
```
The thing you will notice about lexical scope is that it works forward, meaning the name can be accessed by its children's execution contexts.

But it doesn't work backward to its parents, meaning that the variable likes cannot be accessed by its parents.

This also tells us that variables having the same name in different execution contexts gain precedence from top to bottom of the execution stack.

A variable, having a name similar to another variable, in the innermost function (topmost context of the execution stack) will have higher precedence.
</i>