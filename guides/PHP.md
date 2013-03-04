--------------------------------------------

<a name="general-principles"></a>
## 1. General principles

- Files that contain only PHP MUST use only <?php.

- Views or templates that mix markup w/ PHP should only use short-hand syntax (e.g. <?, <?=, if () :, etc)

- Files MUST use only UTF-8 without BOM for PHP code.

- Class names MUST be declared in StudlyCaps - exception: unless following CodeIgniter naming rules (e.g. Album_model).

- Class constants MUST be declared in all upper case with underscore separators.

- Method names should be declared in camelCase, unless inside of a CI controller, model, etc - in which case, use all lowercase w/ underscores.

- The closing ?> tag MUST be omitted from files containing only PHP.

- Code MUST use 4 spaces for indenting, not tabs.

- Lines SHOULD be 80 characters or less.

- Opening braces for classes MUST go on the next line, and closing braces MUST go on the next line after the body.

- Opening braces for methods MUST go on the next line, and closing braces MUST go on the next line after the body.

- Visibility MUST be declared on all properties and methods; abstract and final MUST be declared before the visibility; static MUST be declared after the visibility.

- Control structure keywords MUST have one space after them; method and function calls MUST NOT.

- Opening braces for control structures MUST go on the same line, and closing braces MUST go on the next line after the body.

- Opening parentheses for control structures MUST have a space after them, and closing parentheses for control structures MUST have a space before.

- There MUST NOT be more than one statement per line.

- The PHP constants true, false, and null MUST be in lower case.

- Property & method names SHOULD be prefixed with a single underscore to indicate protected or private visibility. 

- Argument lists MAY be split across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list MUST be on the next line, and there MUST be only one argument per line.

- When the argument list is split across multiple lines, the closing parenthesis and opening brace MUST be placed together on their own line with one space between them.

- Argument lists MAY be split across multiple lines, where each subsequent line is indented once. When doing so, the first item in the list MUST be on the next line, and there MUST be only one argument per line.

- When the argument list is split across multiple lines, the closing parenthesis and opening brace MUST be placed together on their own line with one space between them.

- Use "elseif", not "else if"
 
- Closures & anon functions: The opening brace MUST go on the same line, and the closing brace MUST go on the next line following the body.

- Comments should follow PHPDoc format.
  
- File names MUST be all lowercase, and use underscores - as opposed to hyphens - to separate words. NEVER use spaces.

- View filenames should omit "_view" 
