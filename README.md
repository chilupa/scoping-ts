# scoping-ts
Demonstration of var-scoping and block scoping 

## var-scoping / function scoping: 
Here variable _x_ can be accessed within their containing function. Hence, leakage of scope within the function. 

    function foo(input: boolean) {
      if (input) {
        var x = 10;
      }
      return x; // var declarations accessible within the function
    }
    foo(true); // returns '10'
    foo(false); // returns 'undefined'

## block scoping / lexical scoping: 
Unlike variables declared with _var_ whose scopes leak out to their containing function, block-scoped variables are not visible outside of their nearest containing block or for-loop.

    function f(input: boolean) {
        let a = 100;

        if (input) {
            // Still okay to reference 'a'
            let b = a + 1;
            return b;
        }

        // Error: 'b' doesn't exist here
        return b;
    }
