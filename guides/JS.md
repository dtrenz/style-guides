## Table of Contents

 * [Whitespace](#whitespace)
 * [Beautiful Syntax](#spacing)
 * [Type Checking (Courtesy jQuery Core Style Guidelines)](#type)
 * [Conditional Evaluation](#cond)
 * [Practical Style](#practical)
 * [Naming](#naming)
 * [Misc](#misc)
 * [Native & Host Objects](#native)
 * [Comments](#comments)
 * [One Language Code](#language)



------------------------------------------------

## Idiomatic Style Manifesto


1. <a name="whitespace">Whitespace</a>
  - Always use 4 spaces (soft-tab) for indentation, never use tabs.


2. <a name="spacing">Beautiful Syntax</a>

    A. Parens, Braces, Linebreaks

    ```javascript

    // if/else/for/while/try always have spaces, braces and span multiple lines
    // this encourages readability


    // BAD - Don't do this:

    if(condition) doSomething();

    while(condition) iterating++;

    for(var i=0;i<100;i++) someIterativeFn();


    // Better - Use whitespace to promote readability:

    if ( condition ) {
        // statements
    }

    while ( condition ) {
      // statements
    }

    for ( var i = 0; i < 100; i++ ) {
        // statements
    }


    // Even better:

    var i,
          length = 100;

    for ( i = 0; i < length; i++ ) {
        // statements
    }

    // Or...

    var i = 0,
          length = 100;

    for ( ; i < length; i++ ) {
        // statements
    }

    var prop;

    for ( prop in object ) {
        // statements
    }


    if ( true ) {
        // statements
    } else {
        // statements
    }
    ```


    B. Assignments, Declarations, Functions ( Named, Expression, Constructor )

    ```javascript

    // Variables
    var foo = "bar",
          num = 1,
          undef;

    // Literal notations:
    var array = [],
          object = {};


    // Using only one `var` per scope (function) promotes readability
    // and keeps your declaration list free of clutter (also saves a few keystrokes)

    // Bad
    var foo = "";
    var bar = "";
    var qux;

    // Good
    var foo = "",
        bar = "",
        quux;

    // Even Better
    var foo = "",
          bar = "",
          quux;

    
    // var statements should always be in the beginning of their respective scope (function).
    // Same goes for const and let from ECMAScript 6.

    // Bad
    function foo() {

        // some statements here

        var bar = "",
              qux;
    }

    // Good
    function foo() {
        var bar = "",
              qux;

        // all statements after the variables declarations.
    }
    ```

    ```javascript

    // Named Function Declaration
    function foo( arg1, argN ) {

    }

    // Usage
    foo( arg1, argN );


    // Named Function Declaration
    function square( number ) {
        return number * number;
    }

    // Usage
    square( 10 );

    // Really contrived continuation passing style
    function square( number, callback ) {
        callback( number * number );
    }

    square( 10, function( square ) {
        // callback statements
    });


    // Function Expression
    var square = function( number ) {
        // Return something valuable and relevant
        return number * number;
    };

    // Function Expression with Identifier
    // This preferred form has the added value of being
    // able to call itself and have an identity in stack traces:
    var factorial = function factorial( number ) {
        if ( number < 2 ) {
            return 1;
        }

        return number * factorial( number - 1 );
    };
    ```


    C. Exceptions, Slight Deviations

    ```javascript

    // Functions with callbacks
    foo(function() {
        // Note there is no extra space between the first paren
        // of the executing function call and the word "function"
    });

    // Function accepting an array, no space
    foo([ "alpha", "beta" ]);

    // Function accepting an object, no space
    foo({
        a: "alpha",
        b: "beta"
    });

    // Inner grouping parens, no space
    if ( ! ("foo" in obj) ) {

    }

    ```


    D. Quotes

    Always use single quotes.  Simple, eh?



6. <a name="naming">Naming</a>

    A. You are not a human code compiler/compressor, so don't try to be one.

    The following code is an example of egregious naming:

    ```javascript

    // Example of code with poor names

    function q(s) {
      return document.querySelectorAll(s);
    }
    var i,a=[],els=q("#foo");
    for(i=0;i<els.length;i++){a.push(els[i]);}
    ```

    Without a doubt, you've written code like this - hopefully that ends today.

    Here's the same piece of logic, but with kinder, more thoughtful naming (and a readable structure):

    ```javascript

    // Example of code with improved names

    function query( selector ) {
        return document.querySelectorAll( selector );
    }

    var idx = 0,
          elements = [],
          matches = query("#foo"),
          length = matches.length;

    for ( ; idx < length; idx++ ) {
        elements.push( matches[ idx ] );
    }

    ```

    A few additional naming pointers:

    ```javascript

    // Naming strings

    `dog` is a string


    // Naming arrays

    `dogs` is an array of `dog` strings


    // Naming functions, objects, instances, etc

    camelCase; function and var declarations


    // Naming constructors, prototypes, etc.

    PascalCase; constructor function


    // From the Google Closure Library Style Guide

    functionNamesLikeThis;
    variableNamesLikeThis;
    ConstructorNamesLikeThis;
    EnumNamesLikeThis;
    methodNamesLikeThis;
    SYMBOLIC_CONSTANTS_LIKE_THIS;

    ```

7. <a name="misc">Misc</a>

    This section will serve to illustrate ideas and concepts that should not be considered dogma, but instead exists to encourage questioning practices in an attempt to find better ways to do common JavaScript programming tasks.

    A. Do not use multiple returns.  A function or method should only have a single return or point of exit.

    ```javascript

    // Bad:
    function multiReturn( foo ) {
        if ( foo ) {
            return "foo";
        }
        
        return "quux";
    }

    // Good
    function returnLate( foo ) {
        var ret;

        if ( foo ) {
            ret = "foo";
        } else {
            ret = "quux";
        }

        return ret;
    }
    ```


<a name="comments"></a>
8. Comments

    #### Single line above the code that is subject
    #### Multiline is good
    #### End of line comments are prohibited!


<a name="jquery"></a>
9. jQuery Usage

    A. jQuery Object Caching

        TBD


    B. jQuery Plug-ins & Widgets

        TBD


    C. Misc

        * Use $.on() as opposed to $.bind(), $.live(), or $.delegate() for generic event binding, whether direct or delegated.



----------

Based on a work at <a xmlns:dct="http://purl.org/dc/terms/" href="https://github.com/rwldrn/idiomatic.js" rel="dct:source">github.com/rwldrn/idiomatic.js</a>.
