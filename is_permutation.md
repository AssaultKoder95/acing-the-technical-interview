# Determine If One String is A Permutation of Another

### Brute force method
The brute-force method:
Compute and store all possible string permutations in an array, and check if there are any matching permutations.
However, this results in O(n!) time because of the time it takes to generate all the permutations

Code for generating permutations:
```
/**
 * Permutations
 *
 * @param str
 */
public static void permutation(String str) {
  permutation("", str);
}

/**
 * Permutations
 *
 * @param prefix
 * @param str
 */
private static void permutation(String prefix, String str) {
  int n = str.length();
  if (n == 0) {
    System.out.println(prefix);
  }
  else {
    for (int i = 0; i < n; i++) {
      permutation(prefix + str.charAt(i),
          str.substring(0, i) + str.substring(i + 1, n));
    }
  }
```

Use:
```
permutation("hi")

\\ prints out hi and ih
```

### Using sorting

Sort both strings's characters comparing each entry of the sorted strings. Since the permutations have to have the same number of characters, the sorted strings must be identical.

O(n*log(n))

```
public boolean isPermutation(String str1, String str2) {

    if (str1.length() != str2.length())
      return false;

    char[] a = str1.toCharArray();
    char[] b = str2.toCharArray();

    Arrays.sort(a);
    Arrays.sort(b);

    return Arrays.equals(a, b);
}
```
### Counting characters
The most optimal approach here is to realize that all permutations of a given string have the same number of characters as the original string. We can solve this problem by counting characters.

Comparing length and counting operations both take O(n), since both are completed in one pass.

Time complexity O(n), with O(n) extra space for the arrays.

```
public static boolean isPermutation (String str1, String str2) {
  // Check if both strings are the same length, if not then return false
  if (str1.length() != str2.length()) {
    return false;
  }
  // Change str1's to a character count
  char[] str1array = str1.toCharArray();
  // initialize an array as a counter
  int[] count = new int[128];
  // then we count str1's characters
  for (char character : str1array) {
    count[character]++;
  }
  // match str1's count with str2
  char[] str2array = str2.toCharArray();
  for (char character : str2array) {
    if(--count[character] < 0) {
      return false;
    }
  }
  return true;
}
```
