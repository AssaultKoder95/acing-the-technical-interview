# Fizz Buzz Solution

General idea:
```
if (theNumber is divisible by 3) and (theNumber is divisible by 5) then
print "FizzBuzz"
else if (theNumber is divisible by 3) then
print "Fizz"
else if (theNumber is divisible by 5) then
print "Buzz"
else /* theNumber is not divisible by 3 or 5 */
print theNumber
end if
```
Solution iterating through the array in Python:
```
for i in [0,n+1]:
  if i % 3 and i % 5:
    print "FizzBuzz"
  else if i % 5:
    print "Buzz"
  else if i % 3:
    print "Fizz"
  else:
    print i
```

Short Java Solution:
```
public static void main(String[] args){		
		for(int i = 1; i <= n; i++){
			String test = "";
			test += (i % 3) == 0 ? "fizz" : "";
			test += (i % 5) == 0 ? "buzz" : "";
			System.out.println(!test.isEmpty() ? test : i);
		}
	}
}
```
Runtime: O(N)
