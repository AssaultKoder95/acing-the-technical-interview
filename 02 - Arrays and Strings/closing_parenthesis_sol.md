# Find Closing Parenthesis (Solution)
```
int open_paren_count
int closed_paren_count
int found_closed_paren
for i from [0,string.length + 1]
  if i == "(" AND open_paren_count != closed_paren_count:
    open_paren_count += 1
  if i == ")" AND open_parent_count != closed_paren_count:
    closed_paren_count += 1
  if open_paren_count == closed_paren_count:
    found_closed_paren = 1
    break
return found_closed_paren
```
Runtime: O(n)
