# Find Closing Parenthesis
You are two parameters. The first parameter is a string. The string is filled with opened and closed parenthesis. The second parameter is a number. The number specifies the index of an opened parenthesis. Your method must return the index of a matching closed parenthesis.
### Example
```
method_name("()", 0) --> 1
method_name("((()))", 1) --> 4
method_name("(a(b((j)))3)", 2) --> 9
```

## Challenge
Validate that the index passed has a matching closed parenthesis. If it does not have a matching closed parenthesis, return -1.
### Example
```
method_name("(()", 0) --> -1
method_name("a(d((()k))", 3) --> -1
```
