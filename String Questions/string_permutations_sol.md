# String Permutations Solution

Both iteratively and recursively, generating all permutations of a given String size will
result in O(n!) time.

Let's think about the string "abc"
The first character 'a' can be placed in 3 slots (first second and third)
'b' can be placed in two slots after 'a' has taken a slot. And 'c' can only end up
in the remaining slot.
Then, the total permutations are
3 * 2 * 1 = 6 = 3!
There 6 permutation are
"abc", "acb", "bac", "bca", "cab", "cba"

Here is the iterative solution:
```
public static void main(String[] args) {  
     List<String> listOfAllPermutatuons=getPerms("abc");  
     for(String s:listOfAllPermutatuons)  
     {  
          System.out.println(s);  
     }  
}  
public static ArrayList<String> getPerms(String s) {  
     ArrayList<String> permutations = new ArrayList<String>();  
     if (s == null) {   
          return null;  
     } else if (s.length() == 0) {   
          permutations.add("");  
          return permutations;  
     }  
     char first = s.charAt(0); // get the first character  
     String remainder = s.substring(1); // remove the first character  
     ArrayList<String> words = getPerms(remainder);  
     for (String word : words) {  
          for (int j = 0; j <= word.length(); j++) {  
               permutations.add(insertCharAt(word, first, j));  
          }  
     }  
     return permutations;  
}  
public static String insertCharAt(String word, char c, int i) {  
     String start = word.substring(0, i);  
     String end = word.substring(i);  
     return start + c + end;  
}  
```

However, you should implement a recursive solution since it is more elegant and easier
to understand.

```
public static void permutate(String str) {
  permutation("", str);
}

private static void permutation(String ans, String remain) {
  int n = remain.length();
  // ans serves as an accumulator variable
  // base case: we print out ans since there are no more letters to be added
  if (n == 0) {
    System.out.println(ans);
  }
  // recursive case
  else {
    for (int i = 0; i < n; i++) {
      // we call permutation, each time combining prefix with the individual letters in str
      // we also remove these letters from str
      permutation(ans + remain.charAt(i), remain.substring(0,i) + remain.substring(i+1, n));
    }
  }
}
```
