[&laquo; Back to README](https://github.com/dtrenz/style-guides/blob/master/README.md)<a name="top"></a>
## Table of contents

1. [General principles](#general-principles)
2. [Beautiful Syntax](#syntax)
3. [Naming](#naming)
4. [Whitespace](#whitespace)
5. [Comments](#comments)
6. [Misc](#misc)

--------------------------------------------

<a name="general-principles"></a>
## 1. General principles

* Files that contain only PHP MUST use only <?php; the closing ?> tag MUST be omitted from files containing only PHP.
* Views or templates that mix markup w/ PHP should only use short-hand syntax (e.g. <?, <?=, if () :, etc)
* Files MUST use only UTF-8 without BOM for PHP code.


[top](#top)


<a name="syntax"></a>
## 2. Beautiful Syntax

### A. Parens, Braces, Linebreaks

* Lines SHOULD be 80 characters or less.

```php

// if/else/for/while/try always have spaces, braces and span multiple lines
// this encourages readability


// BAD - Don't do this:

if($condition) doSomething();

while($condition) iterating++;

for($i=0;$i<100;$i++) someIterativeFn();


// Better - Use whitespace to promote readability:

if ( $condition ) {
    // statements
}

while ( $condition ) {
    // statements
}

for ( $i = 0; $i < 100; $i++ ) {
     // statements
}


// Use "elseif", not "else if"
if ( $condition ) {
     // statements
} elseif ( $another_condition ) {
     // statements
} else {
     // statements
}


// Opening braces for classes MUST go on the next line, and closing braces MUST go on the next line after the body.
// Opening braces for methods MUST go on the next line, and closing braces MUST go on the next line after the body.
// Visibility MUST be declared on all properties and methods; abstract and final MUST be declared before the visibility; static MUST be declared after the visibility.


class MyClass
{
    public $prop;
    private $_prop;

    public function myMethod( $param1, $param2 )
    {
        // do some junk
    }

}

```


### B. Assignments, Declarations, Functions ( Named, Expression, Constructor )

```php

// Variables
$foo = 'bar';
$num = 1;

// Literal notations:
$array = array();
$object = new stdClass;


// Named Function Declaration
function foo( $arg1, $argN ) {

}

// Usage
foo( $arg1, $argN );
```


### C. Exceptions, Slight Deviations

```php

// Function accepting an array, no space
foo(array( 'alpha', 'beta' ));
```


### D. Quotes

Always use single quotes unless interpolation is needed.

```php

$str = 'this is a string';

echo($str);
// output: "And this is a string that requires interpolation."

$interpolated = "and $str that requires interpolation."

echo($interpolated);
// output: "And this is a string that requires interpolation."
```

[top](#top)


<a name="naming"></a>
## 3. Naming

### You are not a human code compiler/compressor, so don't try to be one.

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

[top](#top)


<a name="naming"></a>
## 3. Naming

* Class names MUST be declared in StudlyCaps - exception: unless following CodeIgniter naming rules (e.g. Album_model).
* Class constants MUST be declared in all upper case with underscore separators.
* Method names should be declared in camelCase, unless inside of a CI controller, model, etc - in which case, use all lowercase w/ underscores.
* Property & method names SHOULD be prefixed with a single underscore to indicate protected or private visibility. 
* File names MUST be all lowercase, and use underscores - as opposed to hyphens - to separate words. NEVER use spaces.
* View filenames should omit "_view" 

[top](#top)


<a name="whitespace"></a>
## 4. Whitespace

* Code MUST use 4 spaces for indenting, not tabs.
* Control structure keywords MUST have one space after them; method and function calls MUST NOT.
* Opening parentheses for control structures MUST have a space after them, and closing parentheses for control structures MUST have a space before.

[top](#top)


<a name="comments"></a>
## 5. Comments

* Comments should follow PHPDoc format.

[top](#top)


<a name="misc"></a>
## 6. Misc

* There MUST NOT be more than one statement per line.
* The PHP constants true, false, and null MUST be in lower case.
* Argument lists MAY be split across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list MUST be on the next line, and there MUST be only one argument per line.
* When the argument list is split across multiple lines, the closing parenthesis and opening brace MUST be placed together on their own line with one space between them.
* Closures & anon functions: The opening brace MUST go on the same line, and the closing brace MUST go on the next line following the body.

[top](#top)

