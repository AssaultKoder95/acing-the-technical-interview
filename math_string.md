# Parse Mathematical String
You're given a mathematical string as a parameter. Your method must parse it so that it calculates and returns the expected math output.
### Example:
```
method_name("2 + 3") --> 5
method_name("2 + 3 / 5") --> 1
method_name("4 * 4 + 2 / 3") --> 6
```
Assume the string does not contain any parenthesis, brackets, or curly braces. Assume all numbers and math symbols are separated by a space.

## Challenge
Assume the string contains parenthesis, brackets, and/or curly braces.
Example:
```
"( ( 4 + 5 ) / 3 ) * 2" --> 6
"( ( 7 + 3 ) * 2 ) + 8" --> 28
```
Assume all numbers and math symbols are separated by a space.
