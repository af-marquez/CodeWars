# Count by X
## Instructions

Create a function with two arguments that will return an array of the first n multiples of x.

Assume both the given number and the number of times to count will be positive numbers greater than 0.

Return the results as an array or list ( depending on language ).

Examples
```
countBy(1,10)  // should return  {1,2,3,4,5,6,7,8,9,10}
countBy(2,5)  // should return {2,4,6,8,10}
```
## My thought process
Steps:
  1. Take arguments x and n
  2. Iterate until n while multiplying
  3. Return Array

## My answer

<details> 
  <summary>Click here to see my answer</summary>

    public class Kata{
      public static int[] countBy(int x, int n){
        int[] arr = new int[n];
        int j = 1;
        for(int i = 0; i < n; i++){
          arr[i]= x * j;
          j++;
        }
        return arr;
      }
    }

</details>