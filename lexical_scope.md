## Lexical Scope

Lexical scope, also known as static scope, refers to the region in a program's source code where a variable is accessible or visible. Unlike dynamic scope, where the scope is determined at runtime, lexical scope is determined at compile-time based on the layout of the code.

In languages that employ lexical scoping, you can determine the scope of a variable by examining the program's source code without having to understand the flow of program execution. This makes it easier to reason about code because you can see directly where variables are accessible.

Here are some key aspects:

### Block Scope
In many programming languages like C, C++, and Java, variables declared within a block `{...}` are only accessible within that block.

```c
void someFunction() {
  int x = 10;  // x is accessible here

  {
    int y = 20;  // y is accessible here
    // x is also accessible here
  }

  // y is NOT accessible here
}
```

### Function Scope
In languages like JavaScript (prior to ES6 for variables declared with `var`), the scope of a variable is limited to the function in which it is declared.

```javascript
function someFunction() {
  var x = 10;
  if (true) {
    var y = 20;
  }
  // Both x and y are accessible here
}
// Neither x nor y is accessible here
```

### Nested Scope
In many languages, you can have nested scopes, where an inner scope has access to variables declared in its containing (outer) scopes.

```python
x = 10  # Global scope

def outer_function():
    y = 20  # Enclosing scope relative to inner_function

    def inner_function():
        z = 30  # Local scope
        print(x, y, z)  # Can access x, y, and z

    inner_function()

outer_function()
```

### Shadowing
In lexical scope, it is often possible to "shadow" a variable in an inner scope by declaring a new variable with the same name.

```java
int x = 10;  // Global scope

void someFunction() {
    int x = 20;  // This x shadows the global x
}
```

### Lexical Closure
In languages that support first-class functions, lexical scope leads to the concept of closures, where a function can capture variables from its surrounding scope.

```javascript
function outer() {
  let x = 10;
  function inner() {
    console.log(x);  // inner has access to x from outer
  }
  return inner;
}

const myInner = outer();
myInner();  // Outputs 10
```

Lexical scope is foundational to many modern programming languages and aids in readability, maintainability, and predictability of code.