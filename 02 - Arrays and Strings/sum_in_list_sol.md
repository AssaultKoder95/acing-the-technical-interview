# Sum in List

#### Naive Solution
Check every possible combination - Runtime O(n^2)

```
function sum_in_list(arr, num){
  var ans = false;
  var check = arr;

  // Use a nested loop to compare all the element combos
  for (var i = 0; i < arr.length; i++){
    for (var j = 0; j < check.length; j++) {
      // If sum equals number, set answer to true
      if (arr[i] + check[j] === num){
        ans = true;
        break;
      }
    }
  }
  console.log(ans);
}
```

### Most optimal
Hash every element, check for difference - Runtime O(n)

```
function sum_in_list(arr, num){
  // Create a hash table with array elements as keys
  // O(n) runtime
  var hash = new Object();
  for (var i = 0; i < arr.length; i++) {
    hash[arr[i]] = i;
  }

  // Lookup difference in hash table, O(1) runtime
  for (var i = 0; i< arr.length; i++) {
    // Calculate difference from sum
    var check = num-arr[i];
    // If in hash, we've found the sum!
    if (check in hash){
      ans =  true;
      console.log(ans);
      return;
    }
  }
  console.log(ans);
}
```
