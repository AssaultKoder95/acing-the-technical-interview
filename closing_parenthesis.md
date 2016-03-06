# Find Closing Parenthesis
You are given two parameters. The first parameter is a string, string. string is filled with opened and closed parenthesis. The second parameter is a number, n. n specifies the index of an opened parenthesis. Your method must return the index of a matching closed parenthesis.
### Example
```
method_name("()", 0) --> 1
method_name("((()()))", 4) --> 5
method_name("(a()(b((j))())3)", 2) --> 3
```

## Challenge
Validate that the index passed has a matching closed parenthesis. If it does not have a matching closed parenthesis, return -1.
### Example
```
method_name("(()", 0) --> -1
method_name("a(d((()k))", 3) --> -1
```
